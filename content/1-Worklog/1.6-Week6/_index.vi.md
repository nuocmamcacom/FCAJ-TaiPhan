---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Mục tiêu tuần 6:

* Tìm hiểu container và serverless technologies (ECS, Lambda, Fargate)
* Triển khai containerized applications
* Deploy serverless architectures

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu Docker cơ bản và containerization <br> - Hiểu ECS và Fargate concepts <br> - Ôn lại container orchestration | 22/05/2026 | 22/05/2026 | Tài liệu AWS ECS |
| 3 | - Tạo Dockerfile và build images <br> - Push images tới ECR (Elastic Container Registry) <br> - Thiết lập container repositories | 23/05/2026 | 23/05/2026 | Tài liệu AWS ECR |
| 4 | - Deploy containers sử dụng ECS với EC2 launch type <br> - Cấu hình task definitions <br> - Quản lý container lifecycle | 24/05/2026 | 24/05/2026 | Tài liệu AWS ECS |
| 5 | - Tìm hiểu AWS Lambda và serverless computing <br> - Tạo Lambda functions và handlers <br> - Cấu hình triggers và permissions | 25/05/2026 | 26/05/2026 | Tài liệu AWS Lambda |
| 6 | - **Thực hành:** <br>&emsp; + Deploy containerized microservices <br>&emsp; + Tạo serverless workflows <br>&emsp; + Triển khai event-driven architecture | 26/05/2026 | 26/05/2026 | Tài liệu AWS |
| 7 | - Ôn lại container và serverless implementations <br> - Lập tài liệu containerization patterns <br> - Chuẩn bị cho tuần 7 | 27/05/2026 | 27/05/2026 | Personal notes |

### Kết quả đạt được tuần 6:

* Nắm vững containerization với Docker:
  * Tạo optimized Dockerfiles cho ứng dụng
  * Build và quản lý container images
  * Push images tới ECR registry

* Triển khai thành công containerized applications:
  * Tạo ECS task definitions
  * Deploy containers trên EC2 launch type
  * Triển khai automatic container restart và monitoring

* Tìm hiểu serverless computing với Lambda:
  * Tạo Lambda functions trong nhiều ngôn ngữ
  * Cấu hình event sources và triggers
  * Triển khai Lambda layers cho code sharing

* Thiết kế event-driven architectures:
  * Tích hợp Lambda với SNS, SQS, và S3
  * Tạo asynchronous workflows
  * Triển khai real-time data processing