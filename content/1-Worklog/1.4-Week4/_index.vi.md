---
title: "Worklog Tuần 4"
date: 2026-05-08
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Mục tiêu tuần 4:

* Nắm vững các dịch vụ storage và content delivery (S3, CloudFront, EBS)
* Triển khai data lifecycle policies và optimization
* Tìm hiểu security và encryption cho storage services

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | -------- | ------------ | --------------- | -------------- |
| 2 | - Ôn lại S3 storage classes và lifecycle policies <br> - Tìm hiểu versioning và replication <br> - Hiểu S3 encryption và access control | 08/05/2026 | 08/05/2026 | Tài liệu AWS S3 |
| 3 | - Cấu hình S3 lifecycle policies <br> - Thiết lập cross-region replication <br> - Triển khai bucket policies và ACLs | 09/05/2026 | 09/05/2026 | Tài liệu AWS S3 |
| 4 | - Tìm hiểu CloudFront để content delivery <br> - Tạo distributions và invalidation <br> - Hiểu caching strategies | 10/05/2026 | 10/05/2026 | Tài liệu AWS CloudFront |
| 5 | - Triển khai CloudFront distributions <br> - Cấu hình origin và caching behaviors <br> - Theo dõi CDN performance | 11/05/2026 | 12/05/2026 | Tài liệu AWS CloudFront |
| 6 | - **Thực hành:** <br>&emsp; + Thiết kế kiến trúc storage resilient <br>&emsp; + Tối ưu hóa chi phí với lifecycle policies <br>&emsp; + Triển khai content distribution toàn cầu | 12/05/2026 | 12/05/2026 | Tài liệu AWS |
| 7 | - Ôn lại các implementations storage và CDN <br> - Lập tài liệu optimization techniques <br> - Chuẩn bị cho tuần 5 | 13/05/2026 | 13/05/2026 | Personal notes |

### Kết quả đạt được tuần 4:

* Hiểu sâu về S3 và storage optimization:
  * Cấu hình nhiều storage classes để tối ưu hóa chi phí
  * Triển khai lifecycle policies để quản lý data tự động
  * Thiết lập cross-region replication để disaster recovery

* Triển khai thành công CloudFront CDN:
  * Tạo nhiều distributions cho các loại content khác nhau
  * Cấu hình origin behaviors và caching rules
  * Giảm latency cho người dùng toàn cầu

* Triển khai security toàn diện cho storage:
  * Cấu hình bucket encryption
  * Áp dụng least-privilege access policies
  * Bật versioning và MFA delete protection

* Tối ưu hóa chi phí và hiệu suất storage:
  * Giảm data transfer costs sử dụng CloudFront
  * Tự động hóa data archival tới Glacier
  * Đạt được 90% giảm chi phí storage

**Minh chứng thực hành:**

![S3](/static/images/1-Worklog/S3.png)

