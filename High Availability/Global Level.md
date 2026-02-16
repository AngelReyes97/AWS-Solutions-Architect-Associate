# 📌 Designing for Failure on AWS

## 🧠 Core Principle

- ⚠️ Failure is inevitable in distributed systems
- 🏗️ Systems must be **designed with failure in mind**
- 🎯 The goal is to maintain availability even when components fail

This principle is known as **“Designing for Failure.”**

---

## 🚨 What is an Outage?

- ⛔ An **outage** is a period when a service or system is unavailable or not functioning as expected
- ☁️ In AWS, outages can affect:
  - Specific services (e.g., EC2, RDS)
  - Entire Availability Zones
  - Rarely, full regions
- 📉 Outages can impact applications and businesses relying on those services

---

## 🚨 Single Point of Failure

A basic architecture may include:

- 🌐 One VPC
- 🏢 One Availability Zone (AZ)
- 🖥️ EC2 instance
- 🗄️ RDS database

⚠️ Problem:
- If that single AZ fails, the entire infrastructure becomes unavailable
- This creates a **single point of failure**

---

## 🌍 Multi-AZ Architecture (High Availability)

- 🏢 Availability Zones (AZs) within a region are:
  - Interconnected
  - Physically isolated
- 🔐 Isolation reduces the blast radius of failures

### ✅ Best Practices:
- 🚀 Deploy EC2 instances across multiple AZs
- ⚖️ Use an **Application Load Balancer (ALB)** to distribute traffic
- 🗄️ Enable **Multi-AZ RDS** deployment

### 🎯 Result:
- If one AZ fails, the system continues operating from another AZ
- Achieves **high availability**

---

## 🌎 Regional Failures

- ⚠️ Regional failures are rare but possible
- 🏗️ Designing for regional failover:
  - Increases cost
  - Adds architectural complexity
  - Requires duplication of resources
  - Requires data synchronization across regions

---

## 📊 Business Considerations

Before implementing regional failover, evaluate:

- ⏱️ **Recovery Time Objective (RTO)**
  - How quickly must the system recover?
- 💾 **Recovery Point Objective (RPO)**
  - How much data loss is acceptable?
- 💰 Business impact of downtime
- ⚖️ Cost vs availability trade-offs

---

## 🔄 Multi-Region Disaster Recovery

AWS services that help with cross-region recovery:

- 🌍 Amazon Route 53 (DNS failover)
- 🚀 Amazon CloudFront (global content delivery)
- 🔄 AWS Database Migration Service (DMS)

---

## 🛠️ Recovery Strategies

### 🗂️ Snapshot & Restore
- 📦 Take periodic snapshots
- 🔄 Restore in another region when needed
- ⏳ Suitable for **longer RTOs**
- 💰 Lower cost option

---

### 🔁 Continuous Replication
- 📡 Ongoing data synchronization between regions
- ⚡ Faster recovery
- 🎯 Suitable for **short RTOs and low RPOs**
- 💰 Higher cost but minimal downtime

---

## 🎯 Summary

Designing for failure means:

- 🚫 Avoiding single points of failure
- 🌍 Using multiple AZs for high availability
- 🌎 Considering regional failover for critical workloads
- 📊 Aligning architecture with business RTO and RPO requirements