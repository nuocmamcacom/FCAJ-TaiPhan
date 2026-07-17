---
title : "Giới thiệu"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### VPC endpoints
- **VPC endpoints** là các thiết bị ảo. Chúng là thành phần VPC có khả năng mở rộng theo chiều ngang, dự phòng và có tính sẵn sàng cao. Chúng cho phép giao tiếp giữa tài nguyên tính toán của bạn và các dịch vụ AWS mà không làm tăng rủi ro về tính sẵn sàng.
- Tài nguyên tính toán chạy trong VPC có thể truy cập **Amazon S3** bằng Gateway endpoint. Interface endpoint của PrivateLink có thể được dùng bởi tài nguyên chạy trong VPC hoặc trong môi trường on-premises.

#### Tổng quan workshop
Trong workshop này, bạn sẽ sử dụng hai VPC.
- **"VPC Cloud"** dành cho tài nguyên cloud như **Gateway endpoint** và một EC2 instance để kiểm tra.
- **"VPC On-Prem"** mô phỏng môi trường on-premises như nhà máy hoặc trung tâm dữ liệu của doanh nghiệp. Một EC2 instance chạy phần mềm strongSwan VPN đã được triển khai trong "VPC On-prem" và được cấu hình tự động để thiết lập đường hầm Site-to-Site VPN với AWS Transit Gateway. VPN này mô phỏng kết nối từ on-premises đến AWS cloud. Để giảm chi phí, workshop chỉ cấp phát một instance VPN. Khi triển khai cho workload thực tế, AWS khuyến nghị dùng nhiều thiết bị VPN để đạt tính sẵn sàng cao.

![overview](/images/5-Workshop/5.1-Workshop-overview/diagram1.png)
