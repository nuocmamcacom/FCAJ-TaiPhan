---
title: "Week 7 Worklog"
date: 2026-05-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Week 7 Objectives:

* Master messaging and integration services (SNS, SQS, EventBridge)
* Design decoupled architectures
* Implement publish-subscribe patterns

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Learn SNS (Simple Notification Service) basics <br> - Understand message topics and subscriptions <br> - Learn delivery guarantees | 29/05/2026 | 29/05/2026 | AWS SNS documentation |
| 3 | - Create SNS topics and subscriptions <br> - Implement message filtering <br> - Set up email and SMS notifications | 30/05/2026 | 30/05/2026 | AWS SNS documentation |
| 4 | - Learn SQS (Simple Queue Service) concepts <br> - Understand FIFO and standard queues <br> - Learn message retention policies | 31/05/2026 | 31/05/2026 | AWS SQS documentation |
| 5 | - Create SQS queues and configure messages <br> - Implement consumer applications <br> - Set up dead-letter queues | 01/06/2026 | 02/06/2026 | AWS SQS documentation |
| 6 | - **Hands-on Practice:** <br>&emsp; + Design decoupled microservices <br>&emsp; + Implement message-based workflows <br>&emsp; + Create resilient communication patterns | 02/06/2026 | 02/06/2026 | AWS documentation |
| 7 | - Review messaging architectures <br> - Document integration patterns <br> - Prepare for week 8 | 03/06/2026 | 03/06/2026 | Personal notes |

### Week 7 Achievements:

* Comprehensive SNS implementation:
  * Created multi-protocol subscriptions (Email, SMS, HTTP)
  * Implemented message filtering and routing
  * Set up cross-region notifications

* Successful SQS queue management:
  * Created FIFO and standard queues for different use cases
  * Implemented visibility timeout and long polling
  * Set up dead-letter queues for error handling

* Designed decoupled architectures:
  * Implemented publish-subscribe messaging patterns
  * Created producer and consumer applications
  * Achieved loose coupling between services

* Built resilient communication systems:
  * Configured message retention and expiration
  * Implemented retry mechanisms
  * Created monitoring and alerting for message queues