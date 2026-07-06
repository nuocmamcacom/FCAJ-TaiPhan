---
title: "Worklog Tuần 5"
date: 2026-05-15
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---


### Mục tiêu tuần 5:

* Nắm vững các dịch vụ security và identity (IAM, KMS, Secrets Manager)
* Triển khai encryption và key management
* Tìm hiểu compliance và audit logging

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu sâu IAM roles và policies <br> - Học principle of least privilege <br> - Hiểu policy evaluation logic | 15/05/2026 | 15/05/2026 | Tài liệu AWS IAM |
| 3 | - Tạo IAM users, groups, và roles <br> - Triển khai fine-grained permissions <br> - Thiết lập cross-account access | 16/05/2026 | 16/05/2026 | Tài liệu AWS IAM |
| 4 | - Tìm hiểu KMS và key management <br> - Hiểu encryption at rest và in transit <br> - Cấu hình key policies | 17/05/2026 | 17/05/2026 | Tài liệu AWS KMS |
| 5 | - Triển khai encryption cho services (S3, EBS, RDS) <br> - Sử dụng Secrets Manager cho sensitive data <br> - Thiết lập CloudTrail logging | 18/05/2026 | 19/05/2026 | Tài liệu AWS security |
| 6 | - **Thực hành:** <br>&emsp; + Thiết kế zero-trust security architecture <br>&emsp; + Triển khai encryption và key rotation <br>&emsp; + Bật audit logging và monitoring | 19/05/2026 | 19/05/2026 | Tài liệu AWS |
| 7 | - Ôn lại các security implementations <br> - Lập tài liệu security best practices <br> - Chuẩn bị cho tuần 6 | 20/05/2026 | 20/05/2026 | Personal notes |

### Kết quả đạt được tuần 5:

* Triển khai IAM toàn diện:
  * Tạo role-based access control (RBAC) structure
  * Triển khai least-privilege policies trên toàn tổ chức
  * Thiết lập cross-account access cho collaboration

* Encryption và key management:
  * Cấu hình KMS master keys và policies
  * Triển khai encryption cho tất cả storage services
  * Tự động hóa key rotation policies

* Compliance và auditing:
  * Bật CloudTrail cho tất cả API activities
  * Cấu hình log aggregation và analysis
  * Triển khai password policies và MFA enforcement

* Security monitoring và incident response:
  * Thiết lập CloudWatch alarms cho security events
  * Tạo security event playbooks
  * Thể hiện incident response procedures

**Minh chứng thực hành:**

![IAM](/static/images/1-Worklog/IAM.png)
![MFA](/static/images/1-Worklog/MFA.png)
![S3KMS](/static/images/1-Worklog/S3KMS.png)
![SecretsManager](/static/images/1-Worklog/SecretsManager.png)
