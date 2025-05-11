# aws-web-hosting-scalable
Scalable and secure web hosting on AWS using EC2, Auto Scaling, ALB, WAF, CloudWatch, and SNS

This project demonstrates a **highly available and secure web hosting architecture on AWS**, designed for scalability and real-time monitoring. It deploys a website on **EC2 (Ubuntu)** using **Apache**, integrates **Auto Scaling** based on CPU utilization, and uses **Application Load Balancer (ALB)**, **WAF**, **CloudWatch**, and **SNS** for a complete production-ready deployment setup.

---

# Features

- **Website hosted** on EC2 instances running Ubuntu + Apache.
- **Application Load Balancer (ALB)** distributes traffic evenly.
- **Auto Scaling Group (ASG)** adjusts instance count based on CPU usage.
- **AWS WAF** protects the application from web exploits and bots.
- **CloudWatch & SNS** configured for monitoring and alert notifications.
- **Highly available** and **fault-tolerant** architecture.

---

Technologies & Services Used

| Category        | Tools & Services             |
|----------------|------------------------------|
| Compute         | EC2 (Ubuntu)                 |
| Networking      | Application Load Balancer   |
| Security        | AWS WAF                      |
| Scaling         | Auto Scaling Group           |
| Monitoring      | CloudWatch, SNS              |
| Web Server      | Apache2                      |
| OS              | Ubuntu Server 20.04+         |

---
 Setup Instructions

### 1. 🧑‍💻 Launch EC2 Instance (Ubuntu)
- Use Ubuntu 20.04 AMI
- Install Apache2:
  ```bash
  sudo apt update
  sudo apt install apache2 -y
  sudo systemctl enable apache2
Create Launch Template
Base it on the EC2 with Apache installed

Add Apache install script as user data

3. Configure Auto Scaling Group (ASG)
Use Launch Template

Set scaling policy based on CPU Utilization > 60%

Minimum: 1 instance, Maximum: 3 (adjust as needed)

4. Set Up Application Load Balancer (ALB)
Target group: EC2 ASG instances

Listener: HTTP (port 80)

Health check: /

5. Add AWS WAF to ALB
Create WAF Web ACL (e.g., block common attacks)

Associate WAF with ALB

6. Setup Monitoring & Alerts
CloudWatch Alarm: CPU > 60%

SNS Topic: Alert Email on CPU spike

Subscribe your email to SNS topic and confirm



