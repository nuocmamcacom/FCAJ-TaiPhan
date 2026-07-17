---
title : "Tạo S3 Interface endpoint"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---

Trong phần này, bạn sẽ tạo và kiểm tra S3 interface endpoint bằng môi trường on-premises mô phỏng được triển khai cùng workshop này.

1. Quay lại menu Amazon VPC. Trong thanh điều hướng, chọn Endpoints, sau đó nhấp Create Endpoint.

2. Trong màn hình Create endpoint:
- Đặt tên cho interface endpoint
- Trong Service category, chọn **AWS services**

![name](/images/5-Workshop/5.4-S3-onprem/s3-interface-endpoint1.png)

3. Trong ô Search, gõ S3 và nhấn Enter. Chọn endpoint tên `com.amazonaws.us-east-1.s3`. Đảm bảo cột Type hiển thị Interface.

![service](/images/5-Workshop/5.4-S3-onprem/s3-interface-endpoint2.png)

4. Với VPC, chọn `VPC Cloud` từ danh sách thả xuống.
- Mở rộng **Additional settings** và đảm bảo không bật **Enable DNS name** (chúng ta sẽ dùng ở phần sau của workshop)

![vpc](/images/5-Workshop/5.4-S3-onprem/s3-interface-endpoint3.png)

5. Chọn 2 subnet tại các AZ sau: `us-east-1a` và `us-east-1b`

![subnets](/images/5-Workshop/5.4-S3-onprem/s3-interface-endpoint4.png)

6. Với Security group, chọn `SGforS3Endpoint`:

![sg](/images/5-Workshop/5.4-S3-onprem/s3-interface-endpoint5.png)

7. Giữ policy mặc định - full access và nhấp Create endpoint

![success](/images/5-Workshop/5.4-S3-onprem/s3-interface-endpoint-success.png)

Chúc mừng bạn đã tạo S3 interface endpoint thành công. Ở bước tiếp theo, chúng ta sẽ kiểm tra endpoint này.
