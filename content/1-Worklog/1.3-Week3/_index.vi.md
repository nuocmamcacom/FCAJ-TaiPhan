---
title: "Worklog Tuần 3"
date: 2026-05-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---


### Mục tiêu tuần 3:

* Nắm vững các dịch vụ cơ sở dữ liệu (RDS, DynamoDB, ElastiCache)
* Tìm hiểu các chiến lược persistent và backup
* Triển khai replication và failover cơ sở dữ liệu

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu RDS (MySQL, PostgreSQL, MariaDB) <br> - Hiểu database engines và versions <br> - Tìm hiểu backup và recovery procedures | 01/05/2026 | 01/05/2026 | Tài liệu AWS RDS |
| 3 | - Tạo RDS database instance <br> - Cấu hình multi-AZ deployment <br> - Thiết lập read replicas | 02/05/2026 | 02/05/2026 | Tài liệu AWS RDS |
| 4 | - Tìm hiểu DynamoDB cơ bản và các trường hợp sử dụng <br> - Tạo tables và indexes <br> - Hiểu capacity modes | 03/05/2026 | 03/05/2026 | Tài liệu AWS DynamoDB |
| 5 | - Triển khai ứng dụng DynamoDB <br> - Tìm hiểu query và scan operations <br> - Thiết lập monitoring và scaling | 04/05/2026 | 05/05/2026 | Tài liệu AWS DynamoDB |
| 6 | - **Thực hành:** <br>&emsp; + Thiết kế kiến trúc ứng dụng multi-tier <br>&emsp; + Tích hợp databases với ứng dụng <br>&emsp; + Thực hiện backup và disaster recovery | 05/05/2026 | 05/05/2026 | Tài liệu AWS |
| 7 | - Ôn lại các database services đã học <br> - Lập tài liệu database patterns <br> - Chuẩn bị cho tuần 4 | 06/05/2026 | 06/05/2026 | Personal notes |

### Kết quả đạt được tuần 3:

* Hiểu biết toàn diện về các dịch vụ database của AWS:
  * Các tùy chọn RDS engine và cấu hình
  * DynamoDB design patterns và các trường hợp sử dụng
  * ElastiCache cho in-memory caching

* Triển khai thành công cơ sở hạ tầng database sẵn sàng cho production:
  * Tạo RDS instances multi-AZ để đạt high availability
  * Cấu hình automated backups và snapshots
  * Triển khai read replicas để phân phối tải

* Triển khai các giải pháp NoSQL database:
  * Thiết kế và tạo DynamoDB tables
  * Tối ưu hóa indexes và capacity modes
  * Cấu hình automatic scaling

* Phát triển các chiến lược disaster recovery:
  * Triển khai backup và restore procedures
  * Kiểm tra failover mechanisms
  * Tạo recovery runbooks

**Minh chứng thực hành:**
![RDS Created](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/RDS.png)
![DynamoDB](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/DynamoDB.png)

