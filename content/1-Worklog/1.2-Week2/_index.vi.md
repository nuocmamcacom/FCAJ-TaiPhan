---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2

* Tìm hiểu sâu về dịch vụ EC2 và quản lý instances.
* Tìm hiểu networking trong AWS (VPC, subnets, security groups).
* Thực hành auto-scaling và load balancing.

---

### Các công việc cần triển khai trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Ôn lại các loại EC2 instances và trường hợp sử dụng <br> - Tìm hiểu AMI (Amazon Machine Images) <br> - Hiểu biết về EBS volumes và snapshots | 24/04/2026 | 24/04/2026 | Tài liệu AWS EC2 |
| 3 | - Tạo VPC và cấu hình subnets <br> - Thiết lập Internet Gateway và Route Tables <br> - Hiểu Network ACLs và security groups | 25/04/2026 | 25/04/2026 | Tài liệu AWS VPC |
| 4 | - Khởi chạy nhiều EC2 instances trong các subnets khác nhau <br> - Cấu hình Elastic Load Balancer <br> - Kiểm tra load balancing giữa các instances | 26/04/2026 | 26/04/2026 | Tài liệu AWS ELB |
| 5 | - Thiết lập Auto Scaling Group <br> - Cấu hình scaling policies <br> - Theo dõi metrics và logs của instances | 27/04/2026 | 28/04/2026 | Tài liệu AWS Auto Scaling |
| 6 | - **Thực hành:** Tạo kiến trúc high-availability, mô phỏng tải và quan sát auto-scaling, theo dõi và troubleshoot | 28/04/2026 | 28/04/2026 | Tài liệu AWS |
| 7 | - Ôn lại thành tựu tuần 2 <br> - Lập tài liệu networking patterns <br> - Chuẩn bị cho tuần 3 | 29/04/2026 | 29/04/2026 | Personal notes |

---

### Kết quả đạt được tuần 2

* **EC2 & Lưu trữ:** Nắm vững các loại instances, trường hợp sử dụng, tạo và quản lý AMI, cũng như thao tác với EBS volumes và snapshots.
* **Hạ tầng mạng (VPC):** Thiết kế và triển khai thành công VPC với nhiều subnets, cấu hình Internet Gateway, routing, triển khai Network ACLs và các quy tắc Security Group.
* **High Availability:** Triển khai load balancing và auto-scaling thành công bằng cách cấu hình Elastic Load Balancer (ELB) và tạo Auto Scaling Groups với các scaling policies.
* **Giám sát & Khắc phục sự cố:** Thể hiện kỹ năng monitoring và troubleshooting thông qua việc sử dụng CloudWatch để theo dõi metrics, phân tích application logs và giải quyết các vấn đề kết nối/hiệu suất.

**Minh chứng thực hành:**

*Khởi tạo mạng ảo VPC và Subnet tùy chỉnh:*
![VPC Created](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/vpc-created.png)
![Subnet Created](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/subnet-created.png)

*Cấu hình Security Group (mở port RDP) và khởi chạy EC2 Windows thành công:*
![Security Group](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/security-group.png)
![EC2 Running](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/ec2-running.png)

*Kết nối Remote Desktop thành công vào máy chủ AWS:*
![Windows Desktop RDP](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/window-desktop.png)