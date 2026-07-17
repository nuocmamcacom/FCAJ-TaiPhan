---
title : "Truy cập S3 từ on-premises"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

#### Tổng quan

- Trong phần này, bạn sẽ tạo một Interface endpoint để truy cập Amazon S3 từ môi trường on-premises mô phỏng. Interface endpoint sẽ cho phép bạn định tuyến đến Amazon S3 qua kết nối VPN từ môi trường on-premises mô phỏng.

- Vì sao dùng **Interface endpoint**:
  - Gateway endpoint chỉ hoạt động với tài nguyên đang chạy trong VPC nơi nó được tạo. Interface endpoint hoạt động với tài nguyên chạy trong VPC và cả tài nguyên chạy trong môi trường on-premises. Kết nối từ on-premises lên cloud có thể được cung cấp bởi AWS Site-to-Site VPN hoặc AWS Direct Connect.
  - Interface endpoint cho phép bạn kết nối đến các dịch vụ được hỗ trợ bởi AWS PrivateLink. Các dịch vụ này bao gồm một số dịch vụ AWS, dịch vụ do đối tác và khách hàng AWS lưu trữ trong VPC riêng của họ, cũng như các dịch vụ AWS Marketplace được hỗ trợ. Trong workshop này, chúng ta tập trung vào Amazon S3.

![Interface endpoint architecture](/images/5-Workshop/5.4-S3-onprem/diagram3.png)
