---
title : "Chuẩn bị môi trường on-premises"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---

Để chuẩn bị cho phần này của workshop, bạn cần:
- Sửa bảng định tuyến VPC.

Các thành phần này hoạt động cùng nhau để mô phỏng DNS forwarding và name resolution.

Mẫu CloudFormation sẽ tạo thêm các dịch vụ hỗ trợ mô phỏng môi trường on-premises:
- Một Route 53 Private Hosted Zone lưu trữ các bản ghi Alias cho PrivateLink S3 endpoint
- Một Route 53 Inbound Resolver endpoint cho phép "VPC Cloud" giải quyết các yêu cầu DNS tới Private Hosted Zone
- Một Route 53 Outbound Resolver endpoint cho phép "VPC On-prem" chuyển tiếp các yêu cầu DNS cho S3 sang "VPC Cloud"

1. Nhấp vào link sau để mở [AWS CloudFormation console](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/quickcreate?templateURL=https://s3.amazonaws.com/reinvent-endpoints-builders-session/R53CF.yaml&stackName=PLOnpremSetup). Template sẽ được nạp sẵn vào menu. Chấp nhận mọi giá trị mặc định và nhấp Tạo stack.

2. Chờ vài phút để stack được triển khai xong. Bạn có thể tiếp tục phần tiếp theo trước khi quá trình hoàn tất.

#### Cập nhật bảng định tuyến private on-premise

Workshop này dùng StrongSwan VPN chạy trên EC2 instance để mô phỏng khả năng kết nối giữa trung tâm dữ liệu truyền thống và môi trường AWS cloud. Hầu hết các thành phần bắt buộc đã được cung cấp trước. Để hoàn tất cấu hình VPN, bạn sẽ sửa bảng định tuyến "VPC on-prem" để hướng lưu lượng đến cloud đi qua StrongSwan VPN instance.

1. Mở [EC2 management console](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Instances:).
2. Chọn instance tên `infra-vpngw-test`. Trong tab Details, sao chép Instance ID và lưu vào trình soạn thảo để dùng ở các bước tiếp theo.
3. Mở menu **VPC** bằng cách gõ `VPC` vào ô Search.
4. Nhấp vào Route Tables, chọn route table `RT Private On-prem route table`, mở tab Routes rồi nhấp Edit Routes.
5. Thêm route mới:
- Destination: `0.0.0.0/0`
- Target: ID của instance `infra-vpngw-test` (đã lưu ở bước trên)
