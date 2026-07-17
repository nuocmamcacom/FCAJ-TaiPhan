---
title : "Chính sách VPC Endpoint"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

Khi bạn tạo một interface hoặc gateway endpoint, bạn có thể gắn một endpoint policy để kiểm soát quyền truy cập đến service mà bạn đang kết nối. VPC endpoint policy là một IAM resource policy được gắn vào endpoint. Nếu bạn không gắn policy khi tạo endpoint, AWS sẽ gắn policy mặc định cho bạn, cho phép truy cập đầy đủ đến service thông qua endpoint.

Bạn có thể tạo policy chỉ cho phép truy cập một số S3 bucket cụ thể. Điều này hữu ích nếu bạn chỉ muốn một số bucket nhất định có thể truy cập qua endpoint.

Trong phần này, bạn sẽ tạo VPC endpoint policy để giới hạn truy cập đến S3 bucket được chỉ định trong policy.

![endpoint diagram](/images/5-Workshop/5.5-Policy/s3-bucket-policy.png)

#### Kết nối đến EC2 instance và xác minh truy cập S3

1. Khởi động một phiên AWS Session Manager mới trên instance tên `Test-Gateway-Endpoint`. Từ phiên này, xác minh rằng bạn có thể liệt kê nội dung của bucket đã tạo ở Phần 1: Truy cập S3 từ VPC:

```
aws s3 ls s3://\<your-bucket-name\>
```
![test](/images/5-Workshop/5.5-Policy/test1.png)

Nội dung bucket bao gồm hai file 1 GB đã được tải lên trước đó.

2. Tạo một S3 bucket mới; làm theo mẫu đặt tên bạn đã dùng ở Phần 1, nhưng thêm hậu tố `-2` vào tên. Giữ các trường khác mặc định và nhấp create.

![create bucket](/images/5-Workshop/5.5-Policy/create-bucket.png)

Tạo bucket thành công.

![Success](/images/5-Workshop/5.5-Policy/create-bucket-success.png)

3. Đi tới: Services > VPC > Endpoints, sau đó chọn Gateway VPC endpoint đã tạo trước đó. Nhấp tab Policy. Chọn Edit policy.

![policy](/images/5-Workshop/5.5-Policy/policy1.png)

Policy mặc định cho phép truy cập tất cả S3 Buckets thông qua VPC endpoint.

4. Trong màn hình Edit Policy, sao chép và dán policy sau, rồi thay `yourbucketname-2` bằng tên bucket thứ hai của bạn. Policy này sẽ cho phép truy cập bucket mới thông qua VPC endpoint, nhưng không cho phép bucket nào khác trong Amazon S3. Nhấp Save để áp dụng policy.

```
{
  "Id": "Policy1631305502445",
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1631305501021",
      "Action": "s3:*",
      "Effect": "Allow",
      "Resource": [
      				"arn:aws:s3:::yourbucketname-2",
       				"arn:aws:s3:::yourbucketname-2/*"
       ],
      "Principal": "*"
    }
  ]
}
```

![custom policy](/images/5-Workshop/5.5-Policy/policy2.png)

Tùy chỉnh policy thành công.

![success](/static/images/5-Workshop/5.5-Policy/success.png)

5. Từ phiên trên instance `Test-Gateway-Endpoint`, kiểm tra truy cập bucket đã tạo ở Phần 1: Truy cập S3 từ VPC
```
aws s3 ls s3://<yourbucketname>
```

Lệnh này sẽ trả về lỗi vì truy cập bucket này không được phép bởi VPC endpoint policy mới:

![error](/static/images/5-Workshop/5.5-Policy/error.png)

6. Quay về thư mục home trên EC2 instance bằng `cd ~`

- Tạo file `fallocate -l 1G test-bucket2.xyz`
- Copy file lên bucket thứ hai `aws s3 cp test-bucket2.xyz s3://<your-2nd-bucket-name>`

![success](/static/images/5-Workshop/5.5-Policy/test2.png)

Thao tác này thành công vì được phép bởi VPC endpoint policy.

![success](/static/images/5-Workshop/5.5-Policy/test2-success.png)

- Sau đó kiểm tra truy cập bucket đầu tiên bằng cách copy file lên bucket đầu tiên `aws s3 cp test-bucket2.xyz s3://<your-1st-bucket-name>`

![fail](/static/images/5-Workshop/5.5-Policy/test2-fail.png)

Lệnh này sẽ trả về lỗi vì truy cập bucket này không được phép bởi policy mới.

#### Tóm tắt phần này

Trong phần này, bạn đã tạo VPC endpoint policy cho Amazon S3 và dùng AWS CLI để kiểm tra policy. Các thao tác AWS CLI nhắm vào bucket gốc của bạn thất bại vì policy chỉ cho phép truy cập bucket thứ hai. Các thao tác nhắm vào bucket thứ hai thành công vì policy cho phép. Những policy này hữu ích khi bạn cần kiểm soát truy cập tài nguyên qua VPC endpoints.
