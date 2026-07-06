---
title: "Worklog Tuần 1"
date: 2026-04-17
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1

* Nắm vững các dịch vụ AWS chính (EC2, S3, RDS)
* Thiết lập môi trường phát triển và AWS CLI
* Tìm hiểu các nguyên tắc cơ bản về kiến trúc đám mây

---

### Các công việc cần triển khai trong tuần này

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu cơ bản AWS và tổng quan dịch vụ <br> - Hiểu biết EC2, S3, RDS cơ bản <br> - Tìm hiểu IAM và best practices bảo mật | 17/04/2026 | 17/04/2026 | https://aws.amazon.com/training/ |
| 3 | - Tạo tài khoản AWS Free Tier <br> - Cài đặt và cấu hình AWS CLI <br> - Thiết lập access keys và regions | 18/04/2026 | 18/04/2026 | https://docs.aws.amazon.com/cli/ |
| 4 | - Khởi chạy EC2 instance đầu tiên <br> - Kết nối qua SSH <br> - Cấu hình security groups | 19/04/2026 | 19/04/2026 | Tài liệu AWS EC2 |
| 5 | - Tạo S3 bucket <br> - Upload và quản lý objects <br> - Tìm hiểu bucket policies và access control | 20/04/2026 | 21/04/2026 | Tài liệu AWS S3 |
| 6 | - **Thực hành:** Deploy web server đơn giản trên EC2, lưu trữ static files trên S3, kiểm tra kết nối và hiệu suất | 21/04/2026 | 21/04/2026 | Tài liệu AWS |
| 7 | - Ôn lại các learnings tuần 1 <br> - Lập tài liệu key takeaways <br> - Lên kế hoạch cho tuần 2 | 22/04/2026 | 22/04/2026 | Personal notes |

---

### Kết quả đạt được tuần 1

* **Tạo tài khoản và bảo mật:** Tạo tài khoản AWS Free Tier thành công, thiết lập thông tin cá nhân và bật xác thực hai bước (MFA).
* **Quản lý chi phí:** Hoàn thành thiết lập AWS Budgets để kiểm soát rủi ro phát sinh phí.
* **Cài đặt và cấu hình AWS CLI v2:** Đã thiết lập access credentials, cấu hình region mặc định và xác minh kết nối qua các lệnh test.
* **Khởi chạy và cấu hình EC2 instance đầu tiên:** Lựa chọn instance type phù hợp, cấu hình security groups an toàn và kết nối thành công qua SSH.
* **Tạo và quản lý S3 bucket:** Hoàn thành upload files/objects, cấu hình bucket policies và nắm vững cơ chế access control.
* **Deploy:** Triển khai thành công các thành phần ứng dụng web cơ bản trên AWS.

**Minh chứng thực hành:**

![Account Info](/static/images/1-Worklog/account.png)
![MFA Login](/static/images/1-Worklog/MFA.png)
![AWS Budget](/static/images/1-Worklog/budget.png)