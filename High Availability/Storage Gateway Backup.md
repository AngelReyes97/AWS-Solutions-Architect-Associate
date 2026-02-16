# 📌 AWS Storage Gateway

## 🧠 Overview
- 🌉 **AWS Storage Gateway** bridges on-premise storage systems with AWS cloud storage
- ☁️ Integrates with services like:
  - Amazon S3  
  - Amazon Glacier  
- 🖥️ Delivered as a software appliance
- ⚙️ Can be installed on:
  - VMware hypervisors  
  - Microsoft hypervisors  
- 🔐 Supports secure data transfer and storage
- 🎯 Designed for backup and disaster recovery use cases

---

## 🗂️ Gateway Configurations

AWS Storage Gateway offers three configurations:

- 📁 File Gateway  
- 💾 Volume Gateway  
- 🎞️ Tape Gateway  

Each serves different backup and disaster recovery needs.

---

## 📁 File Gateway
- 📦 Stores files as objects in Amazon S3
- 🖥️ Files are accessible like local network shares
- 🔒 Uses HTTPS for secure data transfer
- 🛡️ Uses server-side encryption for secure storage

---

## 💾 Volume Gateway

Available in two types:

### 🟢 Stored Volume Gateway
- 🖥️ Keeps a complete copy of data locally
- ⚡ Provides low-latency access
- ☁️ Backs up data to Amazon S3 as EBS snapshots

---

### 🔵 Cached Volume Gateway
- ☁️ Stores primary data in Amazon S3
- 💾 Uses local storage as a cache
- ⚡ Frequently accessed data remains locally for low latency

---

## 🎞️ Tape Gateway (Gateway VTL)
- 📼 Provides a virtual tape library (VTL)
- ☁️ Backs up data to Amazon S3
- 🗄️ Archives data to Amazon Glacier
- 🔄 Replaces physical tape infrastructure with virtual components

---

## 🔐 Security & Backup Features
- 🔒 Secure data transfer and storage
- 🔁 Supports incremental backups
- 🛡️ Enables disaster recovery solutions