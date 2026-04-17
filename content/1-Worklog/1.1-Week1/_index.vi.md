---
title: "Worklog Tuần 1"
date: 2026-04-17
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---


### Mục tiêu tuần 1:

* Nắm vững các dịch vụ AWS chính (EC2, S3, RDS)
* Thiết lập môi trường phát triển và AWS CLI
* Tìm hiểu các nguyên tắc cơ bản về kiến trúc đám mây

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu cơ bản AWS và tổng quan dịch vụ <br> - Hiểu biết EC2, S3, RDS cơ bản <br> - Tìm hiểu IAM và best practices bảo mật | 17/04/2026 | 17/04/2026 | https://aws.amazon.com/training/ |
| 3 | - Tạo tài khoản AWS Free Tier <br> - Cài đặt và cấu hình AWS CLI <br> - Thiết lập access keys và regions | 18/04/2026 | 18/04/2026 | https://docs.aws.amazon.com/cli/ |
| 4 | - Khởi chạy EC2 instance đầu tiên <br> - Kết nối qua SSH <br> - Cấu hình security groups | 19/04/2026 | 19/04/2026 | Tài liệu AWS EC2 |
| 5 | - Tạo S3 bucket <br> - Upload và quản lý objects <br> - Tìm hiểu bucket policies và access control | 20/04/2026 | 21/04/2026 | Tài liệu AWS S3 |
| 6 | - **Thực hành:** <br>&emsp; + Deploy web server đơn giản trên EC2 <br>&emsp; + Lưu trữ static files trên S3 <br>&emsp; + Kiểm tra kết nối và hiệu suất | 21/04/2026 | 21/04/2026 | Tài liệu AWS |
| 7 | - Ôn lại các learnings tuần 1 <br> - Lập tài liệu key takeaways <br> - Lên kế hoạch cho tuần 2 | 22/04/2026 | 22/04/2026 | Personal notes |

### Kết quả đạt được tuần 1:

* Tạo tài khoản AWS Free Tier thành công với cấu hình bảo mật phù hợp

* Cài đặt và cấu hình AWS CLI v2:
  * Thiết lập access credentials
  * Cấu hình region mặc định
  * Xác minh kết nối với các lệnh test

* Khởi chạy và cấu hình EC2 instance đầu tiên:
  * Lựa chọn instance type phù hợp
  * Cấu hình security groups
  * Kết nối thành công qua SSH

* Tạo và quản lý S3 bucket:
  * Upload files và objects
  * Cấu hình bucket policies
  * Hiểu rõ cơ chế access control

* Deploy thành công các thành phần ứng dụng web trên AWS