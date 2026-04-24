---
title: "Worklog Tuần 2"
date: 2026-04-24
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:

* Tìm hiểu sâu về dịch vụ EC2 và quản lý instances
* Tìm hiểu networking trong AWS (VPC, subnets, security groups)
* Thực hành auto-scaling và load balancing

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Ôn lại các loại EC2 instances và các trường hợp sử dụng <br> - Tìm hiểu AMI (Amazon Machine Images) <br> - Hiểu biết về EBS volumes và snapshots | 24/04/2026 | 24/04/2026 | Tài liệu AWS EC2 |
| 3 | - Tạo VPC và cấu hình subnets <br> - Thiết lập Internet Gateway và Route Tables <br> - Hiểu Network ACLs và security groups | 25/04/2026 | 25/04/2026 | Tài liệu AWS VPC |
| 4 | - Khởi chạy nhiều EC2 instances trong các subnets khác nhau <br> - Cấu hình Elastic Load Balancer <br> - Kiểm tra load balancing giữa các instances | 26/04/2026 | 26/04/2026 | Tài liệu AWS ELB |
| 5 | - Thiết lập Auto Scaling Group <br> - Cấu hình scaling policies <br> - Theo dõi metrics và logs của instances | 27/04/2026 | 28/04/2026 | Tài liệu AWS Auto Scaling |
| 6 | - **Thực hành:** <br>&emsp; + Tạo kiến trúc high-availability <br>&emsp; + Mô phỏng tải và quan sát auto-scaling <br>&emsp; + Theo dõi và troubleshoot | 28/04/2026 | 28/04/2026 | Tài liệu AWS |
| 7 | - Ôn lại thành tựu tuần 2 <br> - Lập tài liệu networking patterns <br> - Chuẩn bị cho tuần 3 | 29/04/2026 | 29/04/2026 | Personal notes |

### Kết quả đạt được tuần 2:

* Nắm vững các khả năng của dịch vụ EC2:
  * Các loại instances khác nhau và các trường hợp sử dụng
  * Tạo và quản lý AMI
  * Các thao tác trên EBS volumes và snapshots

* Thiết kế và triển khai thành công cơ sở hạ tầng VPC:
  * Tạo VPC với nhiều subnets
  * Cấu hình Internet Gateway và routing
  * Triển khai Network ACLs và security group rules

* Triển khai load balancing và auto-scaling:
  * Cấu hình Elastic Load Balancer
  * Tạo Auto Scaling Groups với scaling policies
  * Đạt được kiến trúc high-availability

* Thể hiện kỹ năng monitoring và troubleshooting:
  * Sử dụng CloudWatch để theo dõi metrics
  * Phân tích application logs
  * Giải quyết các vấn đề kết nối và hiệu suất