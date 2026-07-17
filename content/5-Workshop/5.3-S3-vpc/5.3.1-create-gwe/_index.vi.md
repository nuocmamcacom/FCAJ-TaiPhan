---
title : "Tạo gateway endpoint"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

1. Mở [Amazon VPC console](https://us-east-1.console.aws.amazon.com/vpc/home?region=us-east-1#Home:)
2. Trong thanh điều hướng, chọn **Endpoints**, sau đó nhấp **Create Endpoint**:

{{% notice note %}}
Bạn sẽ thấy **6 VPC endpoint** đã tồn tại để hỗ trợ **AWS Systems Manager (SSM)**. Các endpoint này được **CloudFormation Templates** triển khai tự động cho workshop này.
{{% /notice %}}

![endpoint](/images/5-Workshop/5.3-S3-vpc/endpoints.png)

3. Trong màn hình Create endpoint:
- Đặt tên endpoint: ```s3-gwe```
- Trong service category, chọn **AWS services**

![endpoint](/images/5-Workshop/5.3-S3-vpc/create-s3-gwe1.png)

- Trong **Services**, gõ ```s3``` vào ô tìm kiếm và chọn service có loại **gateway**

![endpoint](/images/5-Workshop/5.3-S3-vpc/services.png)

- Với VPC, chọn **VPC Cloud** từ danh sách thả xuống.
- Ở **Configure route tables**, chọn route table đã gắn với **2 subnet** (lưu ý: đây không phải route table chính của VPC mà là route table thứ hai do CloudFormation tạo).

![endpoint](/images/5-Workshop/5.3-S3-vpc/vpc.png)

- Ở **Policy**, giữ lựa chọn mặc định **Full Access** để cho phép truy cập đầy đủ vào service. Bạn sẽ triển khai **VPC endpoint policy** ở phần sau để minh họa việc giới hạn quyền truy cập đến **S3 buckets** theo policy.

![endpoint](/images/5-Workshop/5.3-S3-vpc/policy.png)

- Không thêm tag cho VPC endpoint lúc này.
- Nhấp **Create endpoint**, rồi đóng cửa sổ sau khi thấy thông báo tạo thành công.

![endpoint](/images/5-Workshop/5.3-S3-vpc/complete.png)
