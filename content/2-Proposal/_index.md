---
title: "Proposal"
date: 2026-05-14
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

## AI Content Generator Platform - AI Marketing Content Creation Platform on AWS

---

### 1. Project Overview

**AI Content Generator Platform** is a next-generation SaaS platform that empowers Small and Medium Businesses (SMBs) to automate their Marketing content creation process using Generative AI technology. The platform combines **AWS Cloud** and **Gemini API (Google AI)** to deliver a diverse, scalable, and highly secure content generation solution.

| Criteria | Value |
| --- | --- |
| **Business Model** | SaaS – Monthly/Annual Subscription |
| **Target Audience** | Small and Medium Businesses (SMBs), Marketing Agencies |
| **AI Technology** | Gemini API (Google AI) via AWS Lambda |
| **Infrastructure** | AWS ap-southeast-1 / ap-southeast-2 |
| **Scalability** | Auto Scaling – from 10 to 10,000+ users |
| **Availability** | Multi-AZ, RDS Failover – 99.9% uptime |

---

### 2. Objectives

#### 2.1 Project Objectives

| # | Objective | Metric |
| --- | --- | --- |
| 1 | Build a complete MVP within 4 weeks (Weeks 9–12) | Go-live by end of Week 12 |
| 2 | Achieve high availability for the production system | Uptime ≥ 99.9% |
| 3 | Automate the end-to-end AI content generation flow | Time < 60 seconds/content set |
| 4 | Implement an architecture meeting AWS Well-Architected standards | All 6 pillars covered |
| 5 | Comprehensive security following the Least Privilege principle | No wildcard `*` permissions |

#### 2.2 Value Proposition

*   **Time-saving:** Content creation process shortened from 3–5 days to **< 30 minutes**.
*   **Cost-saving:** Reduce 60–80% compared to hiring Copywriters/Agencies (from $500–3,000/month to $50–150/month).
*   **Brand Consistency:** Brand Persona ensures the correct tone of voice whether generating 10 or 1,000 articles.
*   **Easy Scalability:** Scale to multiple products, markets, and languages without a linear increase in human resources.

---

### 3. Problem Statement

#### 3.1 Market Context

The Digital Marketing market in Southeast Asia has grown strongly post-COVID-19. SMBs face the pressure of continuous multi-channel content creation, while creative resources are limited and Copywriter/Agency costs are rising.

#### 3.2 Core Problems

**Problem 1 – High labor costs**
An average SMB spends $500–$3,000/month on marketing content. High-quality creative human resources are scarce and expensive.

**Problem 2 – Lack of brand consistency**
When multiple people or agencies produce content, the brand's tone and image easily diverge, leading to a loss of end-customer trust.

**Problem 3 – Slow content production speed**
The traditional workflow from brief → draft → review → edit → publish takes an average of **3–7 working days**, failing to meet the pace of real-time marketing.

**Problem 4 – Difficulty in scaling**
When a business expands into new products or markets, content demand multiplies, but human resources cannot be scaled linearly.

#### 3.3 Opportunity

The popularity of LLMs and the ability to integrate via APIs open the opportunity to build a **content automation** platform capable of understanding brand context, customizing for target audiences, and exporting to multiple formats — all within a simple interface, requiring no technical skills.

---

### 4. Solution Architecture

#### 4.1 Overview

The system is deployed on AWS with a multi-tier architecture, clearly separating the Edge, API, Compute, Queue, AI Worker, and Data layers. All computing resources are located within a **VPC (10.0.0.0/16)** spanning **2 Availability Zones**.

![Architecture](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/Architecture.png)

### 4.2 Architecture Components

| Layer | Service | Role |
| --- | --- | --- |
| **Edge & Security** | Amazon CloudFront | Global CDN for React SPA, static content caching |
| | AWS WAF | Protection against SQL Injection, XSS, Bots, Layer 7 DDoS |
| **API** | Amazon API Gateway | Request reception, rate limiting, Cognito Authorizer authentication |
| | Amazon Cognito | User authentication and authorization (User Pool) |
| **Compute** | Application Load Balancer | Load distribution to EC2, automatic Health Checks, spanning 2 AZs |
| | Amazon EC2 (Express API) | Business logic: auth, Brand Persona, Prompts, RDS queries (placed in Private Subnet, no Public IP, traffic only via ALB) |
| | Auto Scaling Group | Automatically scale EC2 instances based on actual load |
| **Queue & AI Worker** | Amazon SQS (Main Queue) | Receive AI tasks from EC2, asynchronous processing |
| | AWS Lambda (Node.js) | Worker fetching jobs from SQS, calling Gemini API |
| **AI** | Gemini API (Google AI) | LLM model for generating marketing content |
| **Data** | Amazon RDS PostgreSQL (Multi-AZ) | Store users, Brand Personas, campaign history, job statuses |
| | Amazon S3 | Store exported files (PDF, DOCX, HTML), logos, brand assets |
| **Observability** | CloudWatch | System-wide Logs, Metrics, and Alarms |
| | AWS X-Ray | Distributed tracing – end-to-end request tracking |
| **Security** | AWS Secrets Manager | Secure storage of Gemini API Keys and sensitive info |
| | AWS KMS | Data encryption at-rest (RDS, S3) |
| | AWS IAM | Least Privilege access control for all services |

#### 4.3 Main Execution Flow

1. User → React SPA → CloudFront
2. CloudFront → WAF (checks for SQL Injection, XSS, Bots)
3. WAF → API Gateway (Cognito auth, rate limiting)
4. API Gateway → ALB → EC2 (Auto Scaling Group)
5. EC2: authenticates user, builds Prompt from Brief + Brand Persona, queries RDS → pushes job → SQS Main Queue
6. Lambda Worker: fetches job from SQS, retrieves API Key from Secrets Manager → calls Gemini API
7. Gemini API generates content
8. Lambda: saves file → S3, updates status → RDS
9. EC2 returns result to UI → User edits & exports file

#### 4.4 AWS Well-Architected Framework

| Pillar | Applied Solution |
| --- | --- |
| **Operational Excellence** | CloudWatch Alarms, X-Ray Tracing, Automated CI/CD |
| **Security** | WAF, IAM Least Privilege, Secrets Manager, KMS, Private Subnets |
| **Reliability** | ALB + Auto Scaling, RDS Multi-AZ Failover |
| **Performance Efficiency** | CloudFront CDN, Serverless Lambda, RDS Query Optimization |
| **Cost Optimization** | Lambda pay-per-use, S3 Lifecycle Policies, On-demand Auto Scaling |
| **Sustainability** | Resource allocation based on actual demand, shutting down Dev environments off-hours |

---

### 5. Timeline

| Week | Objective | Main Tasks | Milestone |
| --- | --- | --- | --- |
| **9** | Complete AWS Infrastructure | VPC + Subnets + IAM; RDS Multi-AZ + Secrets Manager; ALB + EC2 ASG; CloudFront + WAF + API Gateway + CI/CD | Successful ping test: CloudFront → API GW → ALB → EC2 → RDS |
| **10** | Business Backend + Basic UI | Auth API (JWT + Cognito); CRUD Brand Persona; Prompt engine from Brief + Persona; React Dashboard (UI v1.0) | Login, create Persona, input Brief, receive automated Prompt |
| **11** | End-to-end AI Worker Flow | SQS pipeline; Lambda → Gemini API → S3 + RDS; Export PDF/DOCX/HTML; Load Testing & optimization | Brief → AI generates content → Export PDF in < 60 seconds |
| **12** | Hardening & Production | Security audit (WAF, IAM, pentest); UAT + collect feedback; Bug fixes + finalize docs/runbooks; Go-Live + onboard | Production live, 24/7 monitoring, first customers onboarded |

---

### 6. Budget

#### 6.1 Build Costs

| Service | Configuration | Est. Cost/Month |
| --- | --- | --- |
| Amazon EC2 | t3.medium × 2 (On-Demand, Auto Scaling min=2, 1/AZ) | ~$60 |
| Amazon RDS PostgreSQL | db.t3.micro, Multi-AZ | ~$50 |
| NAT Gateway | 2 AZs | ~$64 |
| CloudFront | 100 GB transfer | ~$8 |
| API Gateway | 1M requests | ~$3.50 |
| CloudWatch | Basic Logs + Metrics | ~$5 |
| AWS Lambda | ~100,000 invocations, 512MB | ~$1 |
| Amazon SQS | ~500,000 requests | ~$0.20 |
| Amazon S3 | 50 GB | ~$2 |
| AWS Secrets Manager | 1 secret (Gemini API Key) | ~$1 |
| AWS KMS | 1 CMK (encrypting RDS + S3) | ~$1 |
| Amazon Cognito | < 50,000 MAU (Free Tier) | $0 |
| **Total AWS/month** | | **~$196** |

> 💡 **Note:** ElastiCache Redis will be added in Phase 2 when concurrent users exceed 200+, to reduce RDS load and optimize response time.

#### Gemini API (Google AI)

| Phase | Request Volume | Estimated Cost |
| --- | --- | --- |
| Dev/Staging | ~1,000/month | ~$1–5/month |

#### 6.2 Cost Optimization Strategy

*   **Reserved Instances:** Reserve EC2 and RDS for 1 year → save 30–40%
*   **Serverless Lambda:** AI Worker only incurs charges when there's a job, no idle costs
*   **CloudFront caching:** Reduces requests to EC2 and bandwidth load
*   **S3 Lifecycle Policy:** Automatically transition files > 90 days to S3 Glacier
*   **Auto Scaling:** Scale down to minimum instances during off-peak hours
*   **Spot Instances for Dev:** Save 60–70% compared to On-Demand

---

### 7. Risks

#### 7.1 Risk Matrix

| Risk | Likelihood | Impact |
| --- | --- | --- |
| Gemini API downtime/throttling | Medium | High |
| Gemini API costs exceed budget | High | Medium |
| User data security vulnerability | Low | Very High |
| EC2 instance failure (if not Multi-AZ) | Low | High |
| Slow RDS failover | Low | Medium |
| Lambda timeout due to slow Gemini response | Medium | Medium |
| AWS costs exceed estimates | Medium | Low |
| Delay in Phase 3 (AI Integration) | Medium | Low |

#### 7.2 Mitigation Strategies

**Gemini API Downtime/Throttling:**

*   Lambda retries with Exponential Backoff (3 times, max 5 minutes).
*   CloudWatch Alarms trigger when job failure rates spike.
*   Fallback: Integrate OpenAI API or Amazon Bedrock (Phase 2+).

**Gemini API Costs Exceeding Budget:**

*   Limit AI API calls by subscription plan (Free: 10/mo, Basic: 100, Pro: unlimited).
*   Implement Rate limiting at API Gateway (requests/minute per user).
*   Set up Google Cloud Budget Alerts + AWS Cost Anomaly Detection.

**Data Security Vulnerabilities:**

*   EC2, Lambda, and RDS reside in Private Subnets (no Public IP).
*   KMS encrypts data at-rest (RDS + S3); all connections use TLS 1.2+.
*   Secrets Manager fully replaces environment variables for credentials.
*   WAF blocks SQL Injection, XSS, bad bots; CloudTrail provides audit logs for all API calls.
*   Conduct quarterly IAM permissions reviews (every 90 days).

**Lambda Timeout when Gemini Responds Slowly:**

*   Lambda timeout set to 270 seconds (leaving a buffer against the 300s max limit).
*   Each job generates only 1 type of content (avoid batching multiple types into 1 Lambda call).
*   Utilize streaming responses from Gemini API where applicable.
*   On timeout → auto-retry the job with a higher priority queue.

**Delay in Phase 3 (AI Integration):**

*   Allocate a 1-week buffer (Week 12) strictly for Performance Testing and bug fixing.
*   Prototype Lambda + Gemini API independently starting from Week 2, parallel to Phase 1.
*   Utilize the free Gemini API Sandbox during the initial development phase.

---

> References:
>
> [AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/)
>
> [Gemini API Docs](https://ai.google.dev/docs)
>
> [Amazon SQS Best Practices](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/best-practices.html)