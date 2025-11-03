# 🧱 AWS Storage Services – Exam Overview  

## 🧩 Summary  
This section provides an overview of **core AWS storage services** that are commonly tested on the **AWS Certified Solutions Architect – Associate** exam.  
Understanding the **features, configurations, and use cases** for each service is critical for both the exam and practical AWS architecture design.  

---

## ☁️ Amazon S3 (Simple Storage Service)  
- **Key Concepts:** High availability, durability, cost-effectiveness, and accessibility.  
- **Exam Focus Areas:**  
  - 📦 **Storage classes:** Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier, and Glacier Deep Archive.  
  - 🕒 **Versioning** – maintain multiple object versions for data recovery.  
  - 🔄 **Lifecycle rules** – automate object transitions between storage classes.  
  - 🚀 **Transfer Acceleration** – enable faster uploads via Amazon CloudFront’s edge network.  
  - 🔒 **Security controls** – bucket policies, IAM roles, ACLs, and encryption (SSE-S3, SSE-KMS).  

---

## 📁 Amazon EFS (Elastic File System)  
- **Definition:** A **fully managed, scalable file storage** system for use with Amazon EC2 instances.  
- **Exam Focus Areas:**  
  - 💾 **Storage classes:** Standard and Infrequent Access (IA).  
  - ⚙️ **Performance modes:** General Purpose and Max I/O.  
  - 📊 **Throughput modes:** Bursting and Provisioned.  
  - 🔐 **Encryption options:** Data encryption at rest and in transit.  

---

## 💽 Amazon EBS (Elastic Block Store)  
- **Definition:** Provides **persistent block storage volumes** for Amazon EC2 instances.  
- **Exam Focus Areas:**  
  - 🧱 **Snapshots:** Point-in-time backups of EBS volumes.  
  - 🔐 **Encryption:** Protects data in transit and at rest using KMS.  
  - 🌍 **Regional considerations:** EBS volumes are **region-specific** and **availability zone–bound**.  
  - ⚡ **Performance options:** SSD-based (gp3, io1/io2) and HDD-based (st1, sc1).  

---

## 🗂️ Amazon FSx  
- **Definition:** Provides **fully managed file systems** optimized for specific workloads.  
- **Variants and Use Cases:**  
  - 🪟 **FSx for Windows File Server:** Integrates with **Active Directory**, supports SMB, and is ideal for Windows-based applications.  
  - 🧬 **FSx for Lustre:** High-performance parallel file system for compute-intensive workloads (e.g., **HPC and machine learning**).  

---

## 🏠 AWS Storage Gateway  
- **Definition:** A **hybrid cloud storage solution** that connects **on-premises environments** with AWS storage services.  
- **Gateway Types:**  
  - 📁 **File Gateway:** For storing files as objects in Amazon S3.  
  - 💾 **Volume Gateway:** Provides block storage, with snapshots stored in S3.  
  - 📼 **Tape Gateway:** Replaces physical tape infrastructure with virtual tapes in AWS.  

---

## 🔄 AWS Backup  
- **Definition:** A **centralized backup service** for managing and automating backups across AWS services.  
- **Supported Services:** EBS, RDS, DynamoDB, EFS, FSx, and more.  
- **Exam Focus Areas:**  
  - 🧭 **Backup policies and vaults** for centralized control.  
  - 🕒 **Scheduled and incremental backups** for cost efficiency.  
  - 🔐 **Encryption and cross-region replication** for compliance and data durability.  

---

## 🧠 Exam Preparation Tips  
- 📘 Understand **key use cases** for each storage service.  
- 🧩 Know when to use **object, block, or file storage**.  
- 🔄 Be familiar with **lifecycle rules**, **snapshot management**, and **backup automation**.  
- ⚙️ Review **hybrid storage solutions** (Storage Gateway, DataSync) and their components.  
- 📊 Focus on **durability, availability, performance modes, and encryption options** for each service.  

---