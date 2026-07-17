---
title : "Dọn dẹp"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

Chúc mừng bạn đã hoàn thành workshop này!

Trong workshop này, bạn đã học các mẫu kiến trúc để truy cập Amazon S3 mà không cần dùng Public Internet.
- Bằng cách tạo gateway endpoint, bạn cho phép giao tiếp trực tiếp giữa tài nguyên EC2 và Amazon S3 mà không cần đi qua Internet Gateway.
- Bằng cách tạo interface endpoint, bạn mở rộng kết nối S3 đến tài nguyên chạy trong trung tâm dữ liệu on-premises thông qua AWS Site-to-Site VPN hoặc Direct Connect.

#### Dọn dẹp
1. Truy cập Hosted Zones ở thanh bên trái của Route 53 console. Nhấp tên zone *s3.us-east-1.amazonaws.com*. Nhấp Delete và xác nhận xóa bằng cách nhập `delete`.

![hosted zone](/images/5-Workshop/5.6-Cleanup/delete-zone.png)

2. Gỡ liên kết Route 53 Resolver Rule - `myS3Rule` khỏi "VPC Onprem" và xóa nó.

![hosted zone](/images/5-Workshop/5.6-Cleanup/vpc.png)

4. Mở CloudFormation console và xóa hai CloudFormation Stacks bạn đã tạo cho lab này:
- PLOnpremSetup
- PLCloudSetup

![delete stack](/images/5-Workshop/5.6-Cleanup/delete-stack.png)

5. Xóa S3 buckets
- Mở S3 console
- Chọn bucket bạn đã tạo cho lab, xác nhận empty, sau đó nhấp Delete và xác nhận xóa

![delete s3](/images/5-Workshop/5.6-Cleanup/delete-s3.png)
