---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Truy Cập S3 An Toàn Trong Mô Hình Hybrid Bằng VPC Endpoint

#### Tổng quan

**AWS PrivateLink** cung cấp kết nối riêng tư đến các dịch vụ AWS từ VPC và cả mạng on-premises, mà không đưa lưu lượng ra Internet công cộng.

Trong lab này, bạn sẽ học cách tạo, cấu hình và kiểm tra các VPC endpoint để workload truy cập dịch vụ AWS mà không phải đi qua Internet công cộng.

Bạn sẽ tạo hai loại endpoint để truy cập Amazon S3: Gateway VPC endpoint và Interface VPC endpoint. Hai loại này có lợi thế khác nhau tùy việc bạn truy cập S3 từ cloud hay từ vị trí on-premises.
- **Gateway** - Tạo gateway endpoint để gửi lưu lượng đến Amazon S3 hoặc DynamoDB bằng địa chỉ IP riêng. Lưu lượng từ VPC được định tuyến đến gateway endpoint thông qua route table.
- **Interface** - Tạo interface endpoint để gửi lưu lượng đến các endpoint service sử dụng Network Load Balancer để phân phối lưu lượng. Lưu lượng đến service được phân giải bằng DNS.

#### Nội dung

1. [Tổng quan workshop](5.1-Workshop-overview)
2. [Chuẩn bị](5.2-Prerequiste/)
3. [Truy cập S3 từ VPC](5.3-S3-vpc/)
4. [Truy cập S3 từ on-premises](5.4-S3-onprem/)
5. [Chính sách VPC Endpoint (phần thêm)](5.5-Policy/)
6. [Dọn dẹp](5.6-Cleanup/)
