---
title: "Worklog Tuần 9"
date: 2026-06-12
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---


### Mục tiêu tuần 9:

* Nắm vững deployment và infrastructure as code (CloudFormation, Terraform)
* Triển khai CI/CD pipelines (CodePipeline, CodeBuild)
* Tìm hiểu GitOps và infrastructure automation

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu CloudFormation cơ bản và templates <br> - Hiểu JSON/YAML template syntax <br> - Tạo simple stacks | 12/06/2026 | 12/06/2026 | Tài liệu AWS CloudFormation |
| 3 | - Tạo complex CloudFormation templates <br> - Triển khai nested stacks và parameters <br> - Quản lý stack updates | 13/06/2026 | 13/06/2026 | Tài liệu AWS CloudFormation |
| 4 | - Tìm hiểu Terraform cơ bản và HCL syntax <br> - Hiểu state management <br> - Cấu hình AWS provider | 14/06/2026 | 14/06/2026 | Tài liệu Terraform |
| 5 | - Tạo Terraform modules và configurations <br> - Triển khai remote state backend <br> - Thực hành infrastructure changes | 15/06/2026 | 16/06/2026 | Tài liệu Terraform |
| 6 | - **Thực hành:** <br>&emsp; + Xây dựng multi-environment IaC <br>&emsp; + Tạo CI/CD pipeline cho infrastructure <br>&emsp; + Triển khai GitOps workflow | 16/06/2026 | 16/06/2026 | Tài liệu AWS |
| 7 | - Ôn lại các IaC implementations <br> - Lập tài liệu infrastructure patterns <br> - Chuẩn bị cho tuần 10 | 17/06/2026 | 17/06/2026 | Personal notes |

### Kết quả đạt được tuần 9:

* Nắm vững Infrastructure as Code với CloudFormation:
  * Tạo reusable CloudFormation templates
  * Triển khai nested stacks cho modular design
  * Tự động hóa infrastructure provisioning

* Triển khai Terraform cho infrastructure management:
  * Tạo modular Terraform configurations
  * Thiết lập remote state backend (S3 + DynamoDB)
  * Quản lý multi-environment deployments

* Xây dựng automated deployment pipelines:
  * Tạo CodePipeline cho continuous deployment
  * Cấu hình CodeBuild cho infrastructure testing
  * Triển khai approval gates và rollback strategies

* Đạt được infrastructure automation:
  * Giảm manual deployment time 90%
  * Đảm bảo consistent environment configuration
  * Cho phép rapid infrastructure scaling