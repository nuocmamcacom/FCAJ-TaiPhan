---
title : "Kiểm tra Interface endpoint"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.4.3 </b> "
---

#### Lấy regional DNS name của S3 interface endpoint
1. Từ menu Amazon VPC, chọn Endpoints.

2. Nhấp vào endpoint vừa tạo: `s3-interface-endpoint`. Mở details và lưu regional DNS name đầu tiên của endpoint vào trình soạn thảo để dùng sau.

![dns name](/images/5-Workshop/5.4-S3-onprem/dns.png)

#### Kết nối EC2 instance trong "VPC On-prem"

1. Mở **Session manager** bằng cách gõ "session manager" vào ô tìm kiếm.

2. Nhấp **Start Session** và chọn EC2 instance tên **Test-Interface-Endpoint**. Instance này đang chạy trong "VPC On-prem" và sẽ được dùng để kiểm tra kết nối đến Amazon S3 thông qua Interface endpoint vừa tạo. Session Manager sẽ mở một tab trình duyệt mới với shell prompt: **sh-4.2 $**

![Start session](/images/5-Workshop/5.4-S3-onprem/start-session.png)

3. Chuyển về home directory của `ssm-user` bằng lệnh `cd ~`

4. Tạo file tên `testfile2.xyz`
```
fallocate -l 1G testfile2.xyz
```

![user](/images/5-Workshop/5.4-S3-onprem/cli1.png)

5. Copy file vào cùng S3 bucket đã tạo ở phần 3.2

```
aws s3 cp --endpoint-url https://bucket.<Regional-DNS-Name> testfile2.xyz s3://<your-bucket-name>
```

- Lệnh này cần tham số `--endpoint-url` vì bạn phải dùng DNS name riêng của endpoint để truy cập S3 qua Interface endpoint.
- Đừng giữ ký tự `*` đầu dòng khi sao chép DNS name khu vực.
- Điền tên S3 bucket bạn đã tạo trước đó.

![copy file](/images/5-Workshop/5.4-S3-onprem/cli2.png)

Giờ file đã được thêm vào S3 bucket. Ở bước tiếp theo, hãy kiểm tra bucket đó.

#### Kiểm tra object trong S3 bucket

1. Truy cập S3 console
2. Nhấp Buckets
3. Nhấp vào tên bucket của bạn và bạn sẽ thấy `testfile2.xyz` đã được thêm vào bucket

![check bucket](/images/5-Workshop/5.4-S3-onprem/check-bucket.png)
