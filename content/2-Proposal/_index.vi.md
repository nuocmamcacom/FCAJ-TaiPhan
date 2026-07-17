---
title: "Bản đề xuất"
date: 2026-04-17
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Nền Tảng Thương Mại Điện Tử Đa Tầng Với AWS
## Kiến Trúc Serverless Sẵn Sàng Cho Sản Xuất Với Khả Năng Mở Rộng Cao

### 1. Tóm Tắt Điều Hành

Đề xuất này trình bày thiết kế và triển khai một **nền tảng thương mại điện tử hoàn chỉnh, sẵn sàng cho sản xuất** sử dụng các dịch vụ đám mây AWS. Nền tảng này thể hiện cách áp dụng các best practices của AWS trên các khía cạnh tính toán, lưu trữ, mạng, bảo mật, phân tích dữ liệu và tự động hóa hạ tầng.

Giải pháp được xây dựng hoàn toàn trên kiến trúc serverless để tự động mở rộng, đạt khả năng sẵn sàng cao và tối ưu chi phí. Đây cũng là một dự án học tập toàn diện nhằm tổng hợp kiến thức tích lũy trong suốt 12 tuần của chương trình đào tạo AWS chuyên sâu.

**Mục tiêu chính:**
- Thiết kế và triển khai một hệ thống thương mại điện tử đa tầng, khả dụng cao
- Áp dụng best practices bảo mật với IAM, KMS và mã hóa
- Tạo pipeline CI/CD tự động cho triển khai liên tục
- Thiết lập giám sát toàn diện và khả năng quan sát hệ thống
- Tối ưu chi phí và hiệu suất

### 2. Vấn Đề Và Tổng Quan Giải Pháp

#### Thách Thức
Các nền tảng thương mại điện tử truyền thống thường gặp phải:
- **Vấn đề mở rộng**: Không thể xử lý lượng truy cập tăng đột biến trong mùa cao điểm mua sắm
- **Chi phí vận hành cao**: Cần đội DevOps chuyên trách để quản lý hạ tầng
- **Hiệu quả chi phí kém**: Cơ sở hạ tầng cố định dù không sử dụng thường xuyên
- **Phạm vi địa lý hạn chế**: Triển khai ở một khu vực gây độ trễ cao cho người dùng quốc tế
- **Quy trình triển khai thủ công**: Cập nhật chậm và dễ phát sinh lỗi

#### Giải Pháp Của Chúng Tôi
Nền tảng **Thương Mại Điện Tử Serverless AWS** giải quyết các thách thức này bằng cách:
- **Tính toán tự động mở rộng**: Lambda xử lý hàng triệu yêu cầu
- **Phân phối toàn cầu**: CloudFront CDN và triển khai đa khu vực
- **Cơ sở hạ tầng dạng mã**: Terraform và CloudFormation để tái lập, kiểm soát phiên bản
- **Tự động hóa hoàn toàn**: CI/CD loại bỏ triển khai thủ công
- **Bảo mật cấp doanh nghiệp**: IAM, mã hóa khi lưu trữ và truyền tải, cô lập mạng
- **Phân tích dữ liệu thời gian thực**: Pipeline dữ liệu từ giao dịch đến bảng điều khiển phân tích

### 3. Kiến Trúc Giải Pháp

#### Các Thành Phần Kiến Trúc Cấp Cao

#### Các Dịch Vụ AWS Chính Được Triển Khai

**Tính Toán & Containerization:**
- AWS Lambda: REST API backend, event processors
- Amazon ECS/Fargate: Microservices được container hóa
- AWS API Gateway: Quản lý API và định tuyến

**Lưu Trữ & Cơ Sở Dữ Liệu:**
- Amazon S3: Tài sản web, hình ảnh sản phẩm, dữ liệu thô
- Amazon RDS: Dữ liệu quan hệ (PostgreSQL)
- Amazon DynamoDB: Danh mục sản phẩm, phiên người dùng
- Amazon ElastiCache: Redis để lưu vào bộ nhớ đệm

**Mạng & Phân Phối Nội Dung:**
- Amazon VPC: Cô lập mạng
- AWS CloudFront: Phân phối nội dung toàn cầu
- Application Load Balancer: Cân bằng tải cho container
- Route 53: DNS và định tuyến

**Bảo Mật & Tuân Thủ:**
- AWS IAM: Quản lý danh tính và truy cập
- AWS KMS: Quản lý khóa
- AWS Secrets Manager: Lưu trữ thông tin xác thực
- VPC Security Groups: Tường lửa mạng

**Nhắn Tin & Tích Hợp:**
- Amazon SNS: Thông báo đến hàng
- Amazon SQS: Xử lý tác vụ không đồng bộ
- AWS EventBridge: Quy trình làm việc được điều khiển bởi sự kiện

**Dữ Liệu & Phân Tích:**
- Amazon Athena: Truy vấn SQL trên hồ dữ liệu
- AWS Glue: Pipeline dữ liệu ETL
- Amazon Kinesis: Truyền phát dữ liệu thời gian thực
- QuickSight: Bảng điều khiển trí tuệ kinh doanh

**Vận Hành & Giám Sát:**
- Amazon CloudWatch: Metrics, logs, alarms
- AWS X-Ray: Tracing phân tán
- AWS CloudTrail: Ghi dấu audit API
- CloudFormation/Terraform: Infrastructure as Code

### 4. Chi Tiết Triển Khai Kỹ Thuật

#### 4.1 Tầng Frontend & Web
**Ngăn Xếp Công Nghệ:**
- Next.js cho server-side rendering
- React cho giao diện tương tác
- TailwindCSS cho kiểu dáng
- Được lưu trữ trên AWS Amplify

**Tính Năng:**
- Server-side rendering để tối ưu hóa SEO
- Khả năng Progressive Web App (PWA)
- Tính sẵn sàng sản phẩm thời gian thực
- Thanh toán một cú nhấp chuột với xác thực Cognito

#### 4.2 Tầng API & Ứng Dụng
**REST API:**
- Kiến trúc API Gateway + Lambda
- Endpoints:
  - GET /products (danh sách sản phẩm)
  - GET /products/{id} (chi tiết sản phẩm)
  - POST /orders (tạo đơn hàng)
  - GET /orders/{id} (theo dõi đơn hàng)
  - POST /users/auth (xác thực)

**GraphQL API (Thay Thế):**
- AWS AppSync cho GraphQL
- Đồng bộ thời gian thực cho trạng thái đơn hàng
- Tối ưu hóa truy vấn tự động

**Microservices:**
- Product Service (ECS/Fargate)
- Order Service (ECS/Fargate)
- Payment Service (Lambda + tích hợp bên thứ ba)
- Notification Service (SQS consumer)

#### 4.3 Kiến Trúc Tầng Dữ Liệu

**Cơ Sở Dữ Liệu Quan Hệ (RDS PostgreSQL):**
Các bảng:

users (id, email, password_hash, created_at)
products (id, name, price, inventory, sku)
orders (id, user_id, total, status, created_at)
order_items (id, order_id, product_id, quantity, price)
payments (id, order_id, amount, status, processor)

**Cơ Sở Dữ Liệu NoSQL (DynamoDB):**
Các bảng:

ProductCatalog (pk: product_id, sk: timestamp, attributes: chi tiết sản phẩm)
SessionStore (pk: session_id, ttl: expiration, attributes: dữ liệu giỏ hàng)
UserPreferences (pk: user_id, sk: preference_type, attributes: cài đặt)

**Hồ Dữ Liệu (S3):**
- Raw events: s3://data-lake-raw/events/
- Processed data: s3://data-lake-processed/analytics/
- Backup: s3://backup-vault/daily-backup/

#### 4.4 Pipeline ETL & Phân Tích

**Luồng Dữ Liệu:**
1. **Tiếp nhận**: Orders -> SNS -> Lambda -> S3 (raw)
2. **Chuyển đổi**: AWS Glue Crawler phát hiện schema -> Công việc ETL chuyển đổi -> S3 (processed)
3. **Phân tích**: Athena truy vấn dữ liệu đã xử lý -> Hiển thị qua QuickSight
4. **Insights**: Bảng điều khiển hiển thị:
   - Tổng doanh số theo khu vực
   - Sản phẩm nổi tiếng
   - Giá trị suốt đời của khách hàng
   - Mức tồn kho

#### 4.5 Triển Khai Bảo Mật

**Kiến Trúc IAM:**
- Role admin: Truy cập đầy đủ
- Role developer: Truy cập hạn chế đến tài nguyên phát triển
- Role execution Lambda: Đọc/ghi vào S3 bucket cụ thể
- Truy cập RDS: Thông qua thông tin xác thực tạm thời qua Secrets Manager

**Mã Hóa:**
- Tại rest: S3 SSE-KMS, RDS encryption, DynamoDB encryption
- Truyền tải: TLS 1.2+, HTTPS everywhere

**Bảo Mật Mạng:**
- VPC với public và private subnets
- Bastion host để truy cập RDS
- Security groups hạn chế lưu lượng truy cập
- NACLs cho kiểm soát ở cấp subnet

**Bảo Mật API:**
- Xác thực API Gateway với API keys
- JWT tokens cho phiên người dùng
- CORS policies cho yêu cầu cross-origin
- Rate limiting để ngăn chặn lạm dụng

#### 4.6 Pipeline CI/CD

**Infrastructure as Code:**
    GitHub Repository
        ->
    CodePipeline (Trigger on push)
        ->
    CodeBuild (Run tests, build artifacts)
        ->
    CodeDeploy (Deploy to Lambda, ECS)
        ->
    Production Environment

**Các Giai Đoạn Triển Khai:**
1. **Dev**: Triển khai tự động khi push branch
2. **Staging**: Yêu cầu phê duyệt thủ công
3. **Production**: Canary deployment (5% -> 50% -> 100%)

### 5. Lộ Trình Triển Khai

#### Tuần 1-2: Nền Tảng & Lập Kế Hoạch
- Ôn tập các nguyên tắc cơ bản AWS
- Thiết kế kiến trúc và tạo sơ đồ
- Thiết lập tài khoản AWS và vai trò IAM
- Khởi tạo các mẫu IaC

#### Tuần 3-4: Cơ Sở Hạ Tầng Cốt Lõi
- Triển khai VPC, RDS, DynamoDB
- Thiết lập S3 buckets với chính sách vòng đời
- Cấu hình IAM policies và KMS keys
- Triển khai ElastiCache cluster

#### Tuần 5-6: API & Ứng Dụng
- Phát triển Lambda functions cho REST API
- Tạo API Gateway endpoints
- Xây dựng và container hóa microservices
- Triển khai trên ECS/Fargate

#### Tuần 7-8: Frontend & Bảo Mật
- Xây dựng frontend Next.js
- Triển khai xác thực Cognito
- Thiết lập CloudFront distribution
- Triển khai trên AWS Amplify

#### Tuần 9: Nhắn Tin & Phân Tích
- Cấu hình SNS/SQS messaging
- Xây dựng pipeline dữ liệu với Glue
- Tạo truy vấn Athena
- Thiết lập QuickSight dashboard

#### Tuần 10: CI/CD & Tự Động Hóa
- Tạo CodePipeline
- Xây dựng CodeBuild projects
- Triển khai CodeDeploy configurations
- Tự động hóa với CloudFormation/Terraform

#### Tuần 11: Giám Sát & Tối Ưu Hóa
- Cấu hình CloudWatch dashboards
- Thiết lập alarms và notifications
- Triển khai X-Ray tracing
- Điều chỉnh hiệu suất và tối ưu hóa chi phí

#### Tuần 12: Kiểm Thử, Tài Liệu & Trình Bày
- Kiểm thử end-to-end
- Kiểm thử tải với Artillery
- Tạo runbooks và tài liệu
- Chuẩn bị trình bày cuối cùng

### 6. Ngăn Xếp Công Nghệ & Công Cụ

**Ngôn Ngữ & Frameworks:**
- JavaScript/TypeScript (Lambda, Next.js)
- Python (Glue ETL scripts)
- SQL (RDS, Athena)
- HCL (Terraform)
- YAML (CloudFormation)

**Công Cụ Phát Triển:**
- AWS SAM CLI cho phát triển Lambda cục bộ
- Docker cho container hóa
- Git cho kiểm soát phiên bản
- VS Code cho phát triển
- Postman cho kiểm thử API

**AWS CLI & SDK:**
- AWS CLI cho hoạt động dòng lệnh
- Boto3 (Python AWS SDK)
- AWS SDK cho JavaScript/Node.js

### 7. Ước Tính Chi Phí

#### Phân Tích Chi Phí Hàng Tháng

| Dịch Vụ | Sử Dụng | Chi Phí/Tháng |
|---------|--------|---------------|
| Lambda | 1M requests, 512MB, 1s avg | $20.00 |
| API Gateway | 1M requests | $35.00 |
| RDS (db.t3.micro, Multi-AZ) | 730 hours | $60.00 |
| DynamoDB (on-demand) | 1M reads, 500K writes | $50.00 |
| S3 Storage | 100 GB | $2.30 |
| S3 Requests | 1M PUT, 2M GET | $5.00 |
| CloudFront | 50 GB transfer | $4.25 |
| ElastiCache (cache.t3.micro) | 730 hours | $18.00 |
| VPC NAT Gateway | 45 GB processed | $32.40 |
| CloudWatch Logs | 10 GB ingested | $5.00 |
| Glue ETL Jobs | 2 DPUs, 8 hours/month | $2.88 |
| Glue Crawlers | 1 crawler, 5 runs | $0.44 |
| Amplify Hosting | 500 MB stored, 1 GB data transfer | $5.00 |
| **Tổng Cộng** | | **$240.27** |

**Chiến Lược Tối Ưu Hóa Chi Phí:**
- Sử dụng Reserved Instances cho RDS (tiết kiệm 30%)
- Bật S3 Intelligent-Tiering (tự động giảm chi phí)
- Lên lịch tắt tài nguyên không phải sản xuất
- Sử dụng VPC endpoints để tránh phí NAT Gateway
- Mục tiêu: khoảng $150/tháng sau tối ưu

### 8. Đánh Giá Rủi Ro & Biện Pháp Giảm Thiểu

#### Ma Trận Rủi Ro

| Rủi Ro | Xác Suất | Tác Động | Mức Độ | Biện Pháp Giảm Thiểu |
|--------|----------|----------|--------|---------------------|
| Vượt giới hạn tỉ lệ API | Trung bình | Cao | Cao | Triển khai rate limiting, tự động mở rộng |
| Cạn kiệt kết nối DB | Thấp | Cao | Cao | Connection pooling, RDS proxy |
| Mất dữ liệu | Thấp | Tối Hạn | Tối Hạn | Backup tự động, sao chép đa khu vực |
| Vượt quá ngân sách | Trung bình | Trung bình | Trung bình | AWS Budget Alerts, Reserved Instances |
| Vấn đề cold start Lambda | Thấp | Trung bình | Thấp | Provisioned concurrency, optimization |
| Lỗi triển khai | Thấp | Trung bình | Thấp | Rollback tự động, kiểm thử |

#### Kế Hoạch Dự Phòng

1. **Lỗi Cơ Sở Dữ Liệu**:
   - Failover tự động với Multi-AZ RDS
   - DynamoDB global tables cho sao chép
   - Snapshot thường xuyên và backup đa khu vực

2. **Suy Giảm Hiệu Suất API**:
   - Bật Lambda provisioned concurrency
   - Triển khai ElastiCache cho dữ liệu truy cập thường xuyên
   - Mở rộng DynamoDB capacity on-demand

3. **Vi Phạm Bảo Mật**:
   - Phân tích CloudTrail ngay lập tức
   - Xoay tất cả thông tin xác thực qua Secrets Manager
   - Triển khai WAF rules trên API Gateway
   - Cô lập tài nguyên bị ảnh hưởng

### 9. Kết Quả Học Tập Dự Kiến

#### Năng Lực Kỹ Thuật Đạt Được

1. **Kiến Trúc Đám Mây**
   - Thiết kế hệ thống đa tầng, khả dụng cao
   - Hiểu kiến trúc serverless vs. container-based
   - Triển khai chiến lược khôi phục thảm họa

2. **Thạo Dịch Vụ AWS**
   - Trải nghiệm thực hành với 20+ dịch vụ AWS
   - Các mẫu tích hợp và best practices
   - Các kỹ thuật tối ưu hóa chi phí

3. **Bảo Mật & Tuân Thủ**
   - Thiết kế chính sách IAM và nguyên tắc least privilege
   - Triển khai mã hóa (KMS, TLS)
   - Ghi dấu audit và giám sát tuân thủ

4. **DevOps & Tự Động Hóa**
   - Infrastructure as Code với Terraform/CloudFormation
   - Triển khai pipeline CI/CD
   - Kiểm thử và triển khai tự động

5. **Kỹ Thuật Dữ Liệu**
   - Thiết kế pipeline ETL
   - Kiến trúc hồ dữ liệu
   - Phân tích và hình ảnh hóa

6. **Giám Sát & Khả Năng Quan Sát**
   - CloudWatch metrics và alarms
   - Distributed tracing với X-Ray
   - Tập hợp và phân tích log

#### Deliverables Thực Tế

1. **GitHub Repository**: Mã IaC được lặp, tài liệu đầy đủ
2. **Sơ Đồ Kiến Trúc**: Nhiều góc nhìn (logic, deployment, data flow)
3. **Runbooks**: Quy trình vận hành và hướng dẫn khắc phục sự cố
4. **Phân Tích Chi Phí**: Phân tích chi phí chi tiết và báo cáo tối ưu hóa
5. **Báo Cáo Kiểm Thử**: Kết quả kiểm thử tải, kiểm thử bảo mật
6. **Tài Liệu**: Tài liệu API toàn diện, hướng dẫn triển khai, hướng dẫn người dùng

### 10. Chỉ Số Thành Công

**Chỉ Số Kỹ Thuật:**
- Tất cả 20+ dịch vụ AWS được triển khai và hoạt động
- Thời gian phản hồi API < 200ms (p95)
- Uptime hệ thống > 99.9%
- Tỷ lệ thành công triển khai tự động > 95%

**Chỉ Số Bảo Mật:**
- Không có lỗ hổng bảo mật trong code scan
- Tất cả dữ liệu được mã hóa khi lưu trữ và truyền tải
- Ghi dấu audit được bật trên tất cả tài nguyên
- Tuân thủ OWASP Top 10 đạt được

**Chỉ Số Chi Phí:**
- Chi phí vận hành < $200/tháng
- Chi phí trên mỗi giao dịch < $0.01
- Xác định các cơ hội tối ưu hóa chi phí

**Chỉ Số Học Tập:**
- Hoàn thành toàn bộ 12 tuần đào tạo
- Vượt qua bài thi thực hành AWS SAA (Solutions Architect Associate)
- Tạo tài liệu toàn diện
- Trình bày prototype hoạt động cho các bên liên quan

### 11. Kết Luận

Dự án nền tảng thương mại điện tử này đại diện cho **ứng dụng thực tế toàn diện** các dịch vụ đám mây AWS đã học trong suốt kỳ thực tập 12 tuần FCAJ. Bằng cách xây dựng dự án này, tôi sẽ:

- Tổng hợp kiến thức lý thuyết thành kỹ năng thực tế
- Thể hiện sự thành thạo trên nhiều danh mục dịch vụ AWS
- Tạo dự án danh mục giới thiệu khả năng kiến trúc đám mây
- Thiết lập nền tảng cho các chứng chỉ AWS trong tương lai (SAA, Developer, DevOps)

Dự án được thiết kế để có **khả năng mở rộng, an toàn, hiệu quả chi phí và sẵn sàng cho sản xuất**, phục vụ như một công cụ học tập và triển khai tham chiếu cho các giải pháp đám mây cấp doanh nghiệp.

