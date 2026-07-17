---
title : "Truy cập S3 từ VPC"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

#### Sử dụng Gateway endpoint

Trong phần này, bạn sẽ tạo **Gateway endpoint** để truy cập **Amazon S3** từ **một EC2 instance**. Gateway endpoint cho phép tải object lên S3 bucket mà không cần dùng **Public Internet**. Để tạo endpoint, bạn cần chỉ định VPC muốn tạo endpoint và service mà bạn muốn kết nối, trong trường hợp này là S3.

![overview](/images/5-Workshop/5.3-S3-vpc/diagram2.png)

#### Nội dung

- [Tạo gateway endpoint](3.1-create-gwe/)
- [Kiểm tra gateway endpoint](3.2-test-gwe/)
