---
title: "Event 1"
date: 2026-06-08
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## "FCAJ Community Day" Reflection Report

### Event Overview

**FCAJ Community Day** is a community event organized by the **First Cloud A Journey (FCAJ)** group, gathering nearly 400 attendees on the 26th floor of the **Bitexco Financial Tower**, Ho Chi Minh City. This was a morning of in-depth learning and networking, where speakers from the community itself – students and pioneers – shared practical knowledge about AI, Cloud, and modern technologies.

The special feature of the event lies in the **"by the community, for the community"** spirit: the speakers were not distant experts, but people on the same journey as the audience – which made the content much more relatable, practical, and in-depth.

---

### Purpose of the Event

*   Connect the First Cloud Journey community – those learning and practicing AWS in Vietnam.
*   Share practical knowledge about AI, Cloud, and modern technologies from experienced practitioners.
*   Inspire and provide career orientation for students and young developers entering the cloud field.
*   Create a peer-to-peer learning space, where knowledge is shared laterally rather than top-down.
*   Build and strengthen the growing AWS community ecosystem in Vietnam.

---

### Event Information

| Information | Details |
| --- | --- |
| **Event Name** | FCAJ Community Day |
| **Organized by** | Huỳnh Hoàng Long, Thiện Lữ & Trần Đại Vĩ |
| **Location** | 26th Floor, Bitexco Financial Tower, 2 Hai Trieu, District 1, HCMC |
| **Attendance** | ~399 people |
| **Time** | 9:00 – 12:00 on May 23, 2026 |
| **Language** | Vietnamese |

---

### List of Sessions

| Time | Topic | Main Content |
| --- | --- | --- |
| 08:30 – 09:00 | Check-in | Settle down on the 26th floor |
| 09:00 – 09:30 | Context Is Everything | Making AI Actually Work for You |
| 09:30 – 09:45 | Friendly AI Assistant | Amazon QuickSight Q |
| 09:45 – 10:25 | From Edge To Origin | CloudFront as Your Foundation |
| 10:25 – 10:55 | 36 hrs with LotusHacks | Building UTMorpho from Idea to Reality |
| 10:55 – 11:00 | Break | Rest break |
| 11:00 – 11:30 | Non-Determinism of LLM | "Deterministic" Settings |
| 11:30 – 12:00 | Multi-Agent System | Enterprise Credit Scoring Case Study |

---

### Detailed Content of Sessions

#### Session 1: Context Is Everything – Making AI Actually Work for You (09:00 – 09:30)

The speaker addressed the issue directly: **why AI often produces poor results**, and the answer lies not in the AI but in the **user's lack of context**.

**Why AI fails:**

*   Short, generic prompts → generic answers, no practical value.
*   Lack of background, objectives, and constraints → AI cannot optimize for specific use cases.

**What "Context" truly is:**

*   Includes: the role you want AI to play, specific goals, constraints, examples, and interaction history.
*   The **Second AI Brain** concept: building a "second memory" that accumulates over time instead of querying the AI one by one.

**The evolution of AI usage:**

*   Phase 1: Using single prompts, random results.
*   Phase 2: Knowing how to write structured prompts.
*   Phase 3: Building a sustainable context system, AI understands you over time.

---

#### Session 2: Friendly AI Assistant with Amazon QuickSight Q (09:30 – 09:45)

*   **Quick Chat Agent:** Ask questions in natural language to explore datasets, no SQL required.
*   **Quick Flows:** Create intelligent workflows by describing them in Vietnamese/English, no code needed.
*   **Quick Spaces:** Collaborative spaces to share insights from individuals to the whole team, solving the "data silo" problem.
*   **QuickSight Dashboards:** Build dashboards from raw data using natural language, AI automatically suggests appropriate chart types.

---

#### Session 3: From Edge To Origin – CloudFront as Your Foundation (09:45 – 10:25)

CloudFront is not just a CDN but a **comprehensive foundation** for any modern workload.

**Cost Optimization:**

*   **Price Class**: choose suitable edge locations according to user region.
*   **Cache hit ratio**: increase cache hit ratio → reduce requests to origin → reduce costs.
*   **Origin Shield**: add a centralized cache layer before the origin.
*   **Compression**: automatically enable Gzip/Brotli to reduce bandwidth.

**Security:**

*   Integrated **AWS WAF**, **Shield Standard/Advanced**, **HTTPS/TLS 1.3**.
*   **Geo restriction**, **Signed URLs/Cookies** for private content.
*   **OAC**: protect S3 buckets to only allow CloudFront access.

**Performance & Reliability:**

*   Over **600 global edge locations**, **HTTP/2 and HTTP/3**, persistent connections.
*   Built-in automatic failover, health check, and retry logic.

---

#### Session 4: 36 hrs with LotusHacks – Building UTMorpho (10:25 – 10:55)

**UTMorpho** is an AI-powered personalized learning path platform for students, built during a 36-hour hackathon.

**Key learnings:**

*   Defining the MVP in the first 2 hours is the most important decision.
*   Knowing when to cut features: dropped 2 major features at hour 28 to have a stable demo.
*   **Communication within the team is more important than technical skills** when working under pressure.
*   Hackathons are not about winning but about **learning velocity**.

---

#### Session 5: Non-Determinism of "Deterministic" LLM Settings (11:00 – 11:30)

**Common misconception:** Temperature=0 does not guarantee the results will always be the same.

**Reasons for remaining non-deterministic:**

*   Floating point arithmetic is not deterministic on GPUs.
*   Tensor parallelism when the model is distributed across multiple GPUs.
*   Load balancers routing requests to different server instances.
*   Quantization (int8, int4) causes a loss of some precision.

**Mitigation strategies:**

*   Seed control, output validation layer, caching layer.
*   Design systems to **tolerate** non-determinism rather than fighting it.

---

#### Session 6: Enterprise-Grade Multi-Agent System – Startup Credit Scoring (11:30 – 12:00)

**Problem:** Startups are underserved because banks cannot accurately evaluate them due to a lack of financial history, intangible assets, and volatile cash flows.

**Why Multi-Agent:** A single agent processing multiple data types → context overflow, inaccuracy, and difficult to maintain.

**Virtual Credit Committee:**

*   Data Collection → Financial Analysis → Market Intelligence → Team Assessment → Risk Scoring.
*   Orchestrator coordinates the entire pipeline.

**Guardrails:** Mandatory explainability, human-in-the-loop for major decisions, full audit trails, periodic bias detection.

---

### What Was Learned

#### Mindset on AI & Context

*   **Context-first mindset**: The quality of AI output depends entirely on the quality of the input context – it's not about finding a stronger AI, but learning how to provide better context.
*   **Second AI Brain concept**: Build a context system that accumulates over time instead of querying the AI one by one.
*   **LLMs are probabilistic, not deterministic**: Even if Temperature=0 is set, results can still change due to floating point arithmetic, tensor parallelism, and inference optimization.
*   **Multi-Agent thinking**: When a problem is complex enough, separating it into specialized agents improves quality and maintainability.

#### AWS Technical Architecture

*   **CloudFront is a foundation, not just a CDN**: Includes security (WAF, Shield), smart routing, edge computing (Lambda@Edge), and cost optimization.
*   **OAC vs OAI**: OAC is the newer, more secure method to restrict S3 to only allow CloudFront access.
*   **Comprehensive cache strategy**: Need to consider TTL for each content type, invalidation strategy, Origin Shield, and cache hit ratio to optimize both cost and performance.

#### Product Mindset & Soft Skills

*   **Done beats perfect**: A product with 80% features working is better than a product with all features but unstable.
*   **Communication under pressure**: Clear and frequent communication is more important than technical skills when the deadline approaches.
*   **Scope management**: Knowing how to say "no" to new features and strictly maintaining the MVP scope is an extremely important skill.

---

### Application to Work

*   **Improve AI usage**: Create comprehensive system prompts, providing clear context about the codebase, tech stack, and constraints before asking the AI.
*   **Production-ready CloudFront**: Configure OAC correctly, optimize cache behavior, enable compression, and consider Origin Shield.
*   **LLM integration awareness**: Temperature=0 does not guarantee determinism, a validation layer and caching strategy are needed.
*   **Multi-Agent approach**: For complex AI problems, having each agent with a clear scope will make testing and maintaining easier.

---

### Experience During the Event

*   The speakers were people from the community – working engineers, recent graduates – creating a more relatable and realistic atmosphere compared to typical events.
*   Great value came not only from the session content but also from the people met – learning AWS together, facing similar issues, feeling that you are not learning alone.

---

### Some photos from the event
