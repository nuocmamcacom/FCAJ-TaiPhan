---
title : "Mô phỏng DNS on-premises"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4.4 </b> "
---

AWS PrivateLink endpoints có địa chỉ IP cố định trong mỗi Availability Zone nơi chúng được triển khai, trong suốt vòng đời của endpoint cho đến khi nó bị xóa. Các địa chỉ IP này được gắn vào Elastic Network Interfaces (ENIs). AWS khuyến nghị dùng DNS để phân giải địa chỉ IP của endpoint, ताकि ứng dụng phía sau luôn dùng được địa chỉ IP mới nhất khi ENI được thêm vào AZ mới hoặc thay đổi theo thời gian.

Trong phần này, bạn sẽ tạo một forwarding rule để gửi yêu cầu DNS resolution từ môi trường on-premises mô phỏng đến Route 53 Private Hosted Zone. Phần này tận dụng hạ tầng đã được CloudFormation triển khai ở mục chuẩn bị môi trường.

#### Tạo DNS Alias Records cho Interface endpoint
1. Truy cập [Route 53 management console](https://us-east-1.console.aws.amazon.com/route53/v2/hostedzones?region=us-east-1#) ở phần Hosted Zones. CloudFormation template bạn triển khai ở phần chuẩn bị đã tạo sẵn Private Hosted Zone này. Nhấp vào tên Private Hosted Zone `s3.us-east-1.amazonaws.com`:

![hosted zone](/images/5-Workshop/5.4-S3-onprem/hosted-zone.png)

2. Tạo một record mới trong Private Hosted Zone:

![Create record](/images/5-Workshop/5.4-S3-onprem/create-record1.png)

- Record name và record type giữ mặc định
- Alias Button: bật
- Route traffic to: Alias to VPC Endpoint
- Region: US East (N. Virginia) [us-east-1]
- Choose endpoint: Dán Regional VPC Endpoint DNS name từ trình soạn thảo của bạn

![record1](/images/5-Workshop/5.4-S3-onprem/record1.png)

3. Nhấp Add another record và thêm record thứ hai với giá trị sau. Khi xong, nhấp Create records để tạo cả hai record.
- Record name: *.
- Record type: giữ mặc định (type A)
- Alias Button: bật
- Route traffic to: Alias to VPC Endpoint
- Region: US East (N. Virginia) [us-east-1]
- Choose endpoint: Dán Regional VPC Endpoint DNS name từ trình soạn thảo

![record 2](/images/5-Workshop/5.4-S3-onprem/record2.png)

Các record mới sẽ xuất hiện trong Route 53 console:

![result](/images/5-Workshop/5.4-S3-onprem/result.png)

#### Tạo Resolver Forwarding Rule

Route 53 Resolver Forwarding Rules cho phép bạn chuyển tiếp DNS queries từ VPC đến nguồn khác để phân giải tên. Ngoài môi trường workshop, bạn có thể dùng tính năng này để chuyển tiếp DNS queries từ VPC đến DNS server on-premises. Trong phần này, bạn sẽ mô phỏng conditional forwarder on-premises bằng cách tạo forwarding rule chuyển DNS queries cho Amazon S3 đến Private Hosted Zone chạy trong "VPC Cloud" để phân giải PrivateLink interface endpoint regional DNS name.

1. Từ Route 53 management console, nhấp **Inbound endpoints** ở thanh bên trái
2. Trong màn hình Inbound endpoints, nhấp ID của inbound endpoint

![Inbound endpoint](/images/5-Workshop/5.4-S3-onprem/route53-1.png)

3. Sao chép hai địa chỉ IP hiển thị vào trình soạn thảo

![Ip addresses](/images/5-Workshop/5.4-S3-onprem/route53-2.png)

4. Từ menu Route 53, chọn **Resolver** > **Rules**, rồi nhấp **Create rule**:

![Ip addresses](/images/5-Workshop/5.4-S3-onprem/route53-3.png)

5. Trong màn hình Create rule:
- Name: `myS3Rule`
- Rule type: `Forward`
- Domain name: `s3.us-east-1.amazonaws.com`

![create rule](/images/5-Workshop/5.4-S3-onprem/route53-4.png)

- VPC: `VPC On-prem`
- Outbound endpoint: `VPCOnpremOutboundEndpoint`

![create rule](/images/5-Workshop/5.4-S3-onprem/route53-5.png)

- Target IP Addresses: nhập cả hai địa chỉ IP từ trình soạn thảo của bạn rồi nhấp Submit

![create rule](/images/5-Workshop/5.4-S3-onprem/route53-6.png)
Bạn đã tạo thành công resolver forwarding rule.

![create rule](/images/5-Workshop/5.4-S3-onprem/route53-7.png)

#### Kiểm tra mô phỏng DNS on-premises

1. Kết nối đến **Test-Interface-Endpoint EC2 instance** bằng **Session Manager**

![create rule](/images/5-Workshop/5.4-S3-onprem/test1.png)

2. Kiểm tra DNS resolution. Lệnh `dig` sẽ trả về các địa chỉ IP gán cho VPC Interface endpoint đang chạy trong VPC Cloud (IP của bạn sẽ khác): `dig +short s3.us-east-1.amazonaws.com`

{{% notice note %}}
Các địa chỉ IP trả về là IP của VPC endpoint, KHÔNG phải IP của Resolver mà bạn dán từ trình soạn thảo. IP của Resolver endpoint và VPC endpoint trông giống nhau vì chúng đều lấy từ khối CIDR của VPC Cloud.
{{% /notice %}}

![create rule](/images/5-Workshop/5.4-S3-onprem/dig.png)

3. Truy cập menu VPC (phần Endpoints), chọn S3 Interface endpoint. Nhấp tab Subnets và xác nhận các địa chỉ IP do `dig` trả về khớp với VPC endpoint:

![create rule](/images/5-Workshop/5.4-S3-onprem/subnet.png)

4. Quay lại shell và dùng AWS CLI để kiểm tra danh sách S3 bucket:

```
aws s3 ls --endpoint-url https://s3.us-east-1.amazonaws.com
```

![create rule](/images/5-Workshop/5.4-S3-onprem/endpoint.png)

5. Kết thúc phiên Session Manager của bạn:

![create rule](/images/5-Workshop/5.4-S3-onprem/terminal.png)

Trong phần này, bạn đã tạo Interface endpoint cho Amazon S3. Endpoint này có thể được truy cập từ on-premises thông qua Site-to-Site VPN hoặc AWS Direct Connect. Route 53 Resolver outbound endpoints mô phỏng việc chuyển tiếp DNS requests từ on-premises đến Private Hosted Zone đang chạy trên cloud. Route 53 inbound endpoints nhận yêu cầu phân giải và trả về phản hồi chứa các địa chỉ IP của VPC interface endpoint. Dùng DNS để phân giải địa chỉ IP của endpoint giúp tăng tính sẵn sàng khi một Availability Zone gặp sự cố.
