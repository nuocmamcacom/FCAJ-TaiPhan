---
title: "[AWS Security] Bảo mật Serverless không chỉ là một lớp bảo vệ"
date: 2026-07-06
weight: 2
draft: false
---

## [AWS Security] Bảo mật Serverless không chỉ là một lớp bảo vệ

Serverless giúp giảm bớt gánh nặng trong việc quản lý máy chủ, nhưng điều đó không có nghĩa là hệ thống sẽ tự động an toàn. Với kiến trúc microservices sử dụng serverless, mỗi API, hàm Lambda, thông tin bí mật (secret) hoặc cơ sở dữ liệu đều có thể trở thành điểm yếu nếu được cấu hình không đúng.

Vì vậy, bảo mật không nên chỉ dựa vào một lớp duy nhất như WAF hoặc API Gateway. Kiến trúc nên áp dụng nguyên tắc **defense-in-depth (phòng thủ nhiều lớp)**, nghĩa là triển khai nhiều lớp bảo vệ kế tiếp nhau để nếu một lớp bị vượt qua thì các lớp còn lại vẫn có thể giảm thiểu thiệt hại.

### 7 lớp bảo vệ chính trong kiến trúc AWS

*   **Edge Protection:** Bảo vệ lưu lượng truy cập đầu vào bằng CloudFront, AWS WAF và AWS Shield.
*   **Identity Protection:** Xác thực người dùng và kiểm soát quyền truy cập bằng Amazon Cognito.
*   **API Protection:** Bảo vệ API, xác thực token, triển khai giới hạn tốc độ (rate limiting) và mã hóa kết nối bằng Amazon API Gateway.
*   **Network Isolation:** Cô lập các tài nguyên nhạy cảm bằng VPC, Security Groups, Network ACLs và VPC Endpoints.
*   **Compute Security:** Bảo mật Lambda bằng nguyên tắc IAM Least Privilege, AWS KMS, Resource-based Policies và Code Signing.
*   **Secrets Protection:** Quản lý thông tin xác thực, API Key và các dữ liệu nhạy cảm bằng AWS Secrets Manager.
*   **Data Protection:** Bảo vệ dữ liệu bằng mã hóa DynamoDB, kiểm soát quyền truy cập và cơ chế sao lưu (backup).

### Giám sát liên tục

Bên cạnh 7 lớp bảo vệ trên, hệ thống cần được giám sát liên tục bằng GuardDuty, CloudTrail, CloudWatch, Security Hub và Amazon Bedrock để phát hiện bất thường, theo dõi hoạt động và hỗ trợ phân tích các vấn đề bảo mật.

### Ưu điểm

Kiến trúc này không phụ thuộc vào một lớp bảo vệ duy nhất. Nếu AWS WAF bị vượt qua, hệ thống vẫn còn API Gateway, Cognito, IAM, Secrets Manager và các dịch vụ giám sát hoạt động phía sau để giảm phạm vi ảnh hưởng của sự cố (blast radius).

### Kết luận

Serverless giúp giảm khối lượng công việc quản lý máy chủ nhưng không loại bỏ trách nhiệm về bảo mật. Đối với các hệ thống chạy trong môi trường production, bảo mật cần được thiết kế ngay từ đầu, bao phủ toàn bộ các thành phần như lưu lượng truy cập, xác thực, API, mạng, Lambda, secrets, dữ liệu và giám sát.

---
**Tham khảo:** [AWS Security Blog - Building an AI-powered defense-in-depth security architecture for serverless microservices](https://aws.amazon.com/vi/blogs/security/building-an-ai-powered-defense-in-depth-security-architecture-for-serverless-microservices/)