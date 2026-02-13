# 📌 Amazon DocumentDB

## 🧠 Overview
- 📄 **Amazon DocumentDB** is a fully managed, non-relational (NoSQL) database service
- 🌐 Operates within a **Virtual Private Cloud (VPC)** for network isolation and security
- 📦 Designed to store **JSON-like document data**
- 🔍 Supports querying and indexing for fast data retrieval
- 📈 Allows **separate scaling of compute and storage resources**
- 💾 Storage automatically increases in **10 GB increments** up to **64 TB**
- 🔄 Fully compatible with **MongoDB**
  - Enables seamless migration using **AWS Database Migration Service (DMS)**
  - ✅ No application code changes required

---

## 🏗️ Architecture
- 🧩 A **DocumentDB cluster** can contain up to **16 DB instances**
  - 🟢 **1 Primary instance** – handles write operations
  - 🔵 Up to **15 Read Replicas** – handle read requests
- ⚡ Designed for high availability with minimal replication lag
- 📈 Supports scalable read performance through replicas

---

## 🔗 Endpoints

DocumentDB uses endpoints to manage connectivity, failover, and load balancing.

### 🟢 Cluster Endpoint
- 🌍 A URL that points to the **current primary DB instance**
- ✍️ Used for **both read and write operations**
- 🔄 If the primary fails:
  - A read replica is automatically promoted to primary
  - Or a new primary is created if no replicas exist
- 🔁 The cluster endpoint automatically updates to the new primary
- ✅ No application changes required

---

### 🔵 Reader Endpoint
- 📖 Designed for **read-only operations**
- 🌍 Connects to **any available read replica**
- ⚖️ Helps distribute read traffic across replicas
- 📌 Only **one reader endpoint** exists, even if multiple replicas are configured
- 🚀 Improves performance by offloading reads from the primary instance

---

### 🖥️ Instance Endpoints
- 🎯 Each DB instance (primary or replica) has its own unique endpoint
- 🔗 Points directly to that specific instance
- ⚖️ Useful for directing traffic to specific instances
- 📈 Helps with custom load balancing and traffic distribution

---

## 🔄 High Availability & Failover
- 🚨 If the primary instance fails:
  - A read replica is automatically promoted
  - The cluster endpoint redirects to the new primary
- 🔁 Ensures seamless connectivity and operational continuity
- 🛡️ Provides high availability and fault tolerance

---

## 💾 Backups & Durability
- 🗓️ Automatic daily backups
- ⏳ Retention period of up to **35 days**
- 🔄 Supports **Point-in-Time Recovery (PITR)**
- ☁️ Backups are stored in **Amazon S3**
- 🛡️ Ensures strong data durability

---

## 🧠 Analogy

Imagine **Amazon DocumentDB** as a highly organized digital filing cabinet inside a secure office building (the Virtual Private Cloud).

- 🗄️ The filing cabinet = The DocumentDB cluster  
- 📂 Each drawer = Storage  
- 📁 Each folder = A document collection  
- 📄 Each document = JSON data  
- 📑 Smart indexing = A detailed table of contents for fast lookup  

If your office grows:
- ➕ You can add more drawers (storage)
- 👨‍💼 You can hire more assistants (compute power)

Only:
- 🟢 One assistant can make changes at a time (Primary instance)
- 🔵 Other assistants help people read documents (Read Replicas)

And if you previously used a similar filing system (like MongoDB), you can move your folders in without rewriting them.