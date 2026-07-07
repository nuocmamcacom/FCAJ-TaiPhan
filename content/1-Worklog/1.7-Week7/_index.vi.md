---
title: "Worklog Tuần 7"
date: 2026-05-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Mục tiêu tuần 7:

* Nắm vững messaging và integration services (SNS, SQS, EventBridge)
* Thiết kế decoupled architectures
* Triển khai publish-subscribe patterns

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Tìm hiểu SNS (Simple Notification Service) cơ bản <br> - Hiểu message topics và subscriptions <br> - Tìm hiểu delivery guarantees | 29/05/2026 | 29/05/2026 | Tài liệu AWS SNS |
| 3 | - Tạo SNS topics và subscriptions <br> - Triển khai message filtering <br> - Thiết lập email và SMS notifications | 30/05/2026 | 30/05/2026 | Tài liệu AWS SNS |
| 4 | - Tìm hiểu SQS (Simple Queue Service) concepts <br> - Hiểu FIFO và standard queues <br> - Tìm hiểu message retention policies | 31/05/2026 | 31/05/2026 | Tài liệu AWS SQS |
| 5 | - Tạo SQS queues và cấu hình messages <br> - Triển khai consumer applications <br> - Thiết lập dead-letter queues | 01/06/2026 | 02/06/2026 | Tài liệu AWS SQS |
| 6 | - **Thực hành:** <br>&emsp; + Thiết kế decoupled microservices <br>&emsp; + Triển khai message-based workflows <br>&emsp; + Tạo resilient communication patterns | 02/06/2026 | 02/06/2026 | Tài liệu AWS |
| 7 | - Ôn lại messaging architectures <br> - Lập tài liệu integration patterns <br> - Chuẩn bị cho tuần 8 | 03/06/2026 | 03/06/2026 | Personal notes |

### Kết quả đạt được tuần 7:

* Triển khai SNS toàn diện:
  * Tạo multi-protocol subscriptions (Email, SMS, HTTP)
  * Triển khai message filtering và routing
  * Thiết lập cross-region notifications

* Quản lý SQS queue thành công:
  * Tạo FIFO và standard queues cho các use cases khác nhau
  * Triển khai visibility timeout và long polling
  * Thiết lập dead-letter queues cho error handling

* Thiết kế decoupled architectures:
  * Triển khai publish-subscribe messaging patterns
  * Tạo producer và consumer applications
  * Đạt được loose coupling giữa các services

* Xây dựng resilient communication systems:
  * Cấu hình message retention và expiration
  * Triển khai retry mechanisms
  * Tạo monitoring và alerting cho message queues