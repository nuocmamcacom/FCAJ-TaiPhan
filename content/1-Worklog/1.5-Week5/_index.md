---
title: "Week 5 Worklog"
date: 2026-05-15
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---


### Week 5 Objectives:

* Master security and identity services (IAM, KMS, Secrets Manager)
* Implement encryption and key management
* Learn compliance and audit logging

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Deep dive into IAM roles and policies <br> - Learn principle of least privilege <br> - Understand policy evaluation logic | 15/05/2026 | 15/05/2026 | AWS IAM documentation |
| 3 | - Create IAM users, groups, and roles <br> - Implement fine-grained permissions <br> - Set up cross-account access | 16/05/2026 | 16/05/2026 | AWS IAM documentation |
| 4 | - Learn KMS and key management <br> - Understand encryption at rest and in transit <br> - Configure key policies | 17/05/2026 | 17/05/2026 | AWS KMS documentation |
| 5 | - Implement encryption for services (S3, EBS, RDS) <br> - Use Secrets Manager for sensitive data <br> - Set up CloudTrail logging | 18/05/2026 | 19/05/2026 | AWS security docs |
| 6 | - **Hands-on Practice:** <br>&emsp; + Design zero-trust security architecture <br>&emsp; + Implement encryption and key rotation <br>&emsp; + Enable audit logging and monitoring | 19/05/2026 | 19/05/2026 | AWS documentation |
| 7 | - Review security implementations <br> - Document security best practices <br> - Prepare for week 6 | 20/05/2026 | 20/05/2026 | Personal notes |

### Week 5 Achievements:

* Comprehensive IAM implementation:
  * Created role-based access control (RBAC) structure
  * Implemented least-privilege policies across organization
  * Set up cross-account access for multi-team collaboration

* Encryption and key management:
  * Configured KMS master keys and policies
  * Implemented encryption for all storage services
  * Automated key rotation policies

* Compliance and auditing:
  * Enabled CloudTrail for all API activities
  * Configured log aggregation and analysis
  * Implemented password policies and MFA enforcement

* Security monitoring and incident response:
  * Set up CloudWatch alarms for security events
  * Created security event playbooks
  * Demonstrated incident response procedures

**Practical Evidence:**

![IAM](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/IAM.png)
![MFA](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/MFA.png)
![S3KMS](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/S3KMS.png)
![SecretsManager](https://raw.githubusercontent.com/nuocmamcacom/FCAJ-TaiPhan/main/static/images/1-Worklog/SecretsManager.png)