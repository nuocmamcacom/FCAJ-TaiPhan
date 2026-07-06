---
title: "Week 2 Worklog"
date: 2026-04-24
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives

* Deep dive into EC2 services and instance management.
* Understand networking in AWS (VPC, subnets, security groups).
* Practice auto-scaling and load balancing.

---

### Tasks to be implemented this week

| Day | Task | Start Date | End Date | Resources |
| --- | -------- | ------------ | --------------- | -------------- |
| Monday | - Review EC2 instance types and use cases <br> - Learn about AMI (Amazon Machine Images) <br> - Understand EBS volumes and snapshots | 24/04/2026 | 24/04/2026 | AWS EC2 Documentation |
| Tuesday | - Create VPC and configure subnets <br> - Set up Internet Gateway and Route Tables <br> - Understand Network ACLs and security groups | 25/04/2026 | 25/04/2026 | AWS VPC Documentation |
| Wednesday | - Launch multiple EC2 instances in different subnets <br> - Configure Elastic Load Balancer <br> - Test load balancing across instances | 26/04/2026 | 26/04/2026 | AWS ELB Documentation |
| Thursday | - Set up Auto Scaling Group <br> - Configure scaling policies <br> - Monitor instance metrics and logs | 27/04/2026 | 28/04/2026 | AWS Auto Scaling Documentation |
| Friday | - **Practice:** Create a high-availability architecture, simulate load and observe auto-scaling, monitor and troubleshoot | 28/04/2026 | 28/04/2026 | AWS Documentation |
| Saturday | - Review week 2 achievements <br> - Document networking patterns <br> - Prepare for week 3 | 29/04/2026 | 29/04/2026 | Personal notes |

---

### Week 2 Achievements

* **EC2 & Storage:** Mastered various instance types, use cases, creation and management of AMIs, as well as operations on EBS volumes and snapshots.
* **Network Infrastructure (VPC):** Successfully designed and deployed a VPC with multiple subnets, configured Internet Gateway, routing, Network ACLs, and Security Group rules.
* **High Availability:** Successfully deployed load balancing and auto-scaling by configuring an Elastic Load Balancer (ELB) and creating Auto Scaling Groups with scaling policies.
* **Monitoring & Troubleshooting:** Demonstrated monitoring and troubleshooting skills by using CloudWatch to track metrics, analyzing application logs, and resolving connectivity/performance issues.

**Practical Evidence:**

*Creating a custom VPC and Subnet:*
![VPC Created](/static/images/1-Worklog/vpc-created.png)
![Subnet Created](/static/images/1-Worklog/subnet-created.png)


*Configuring Security Group (opening RDP port) and successfully launching a Windows EC2 instance:*
![Security Group](/static/images/1-Worklog/security-group.png)
![EC2 Running](/static/images/1-Worklog/ec2-running.png)

*Successfully connecting to the AWS server via Remote Desktop:*
![Windows Desktop RDP](/static/images/1-Worklog/window-desktop.png)