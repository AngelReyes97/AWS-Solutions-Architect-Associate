# 📌 Amazon Keyspaces

## 🧠 Overview
- 🗄️ **Amazon Keyspaces** is a serverless, fully managed database service
- 🔄 Compatible with **Apache Cassandra**
- 🌍 Built for distributed, NoSQL workloads requiring high availability
- ⚡ Designed to handle **large volumes of data** with low latency
- 🛠️ Eliminates infrastructure management (no servers to provision or maintain)
- 📈 Provides automatic scalability and high availability
- 💰 Uses a **pay-as-you-go pricing model**
- 🧩 Compatible with existing Cassandra tools, drivers, and application code
- 🧠 Uses **CQL (Cassandra Query Language)** for communication
  - Similar to SQL
  - Makes transition easier for users familiar with relational databases

---

## 🚀 Key Features
- ⚡ Extreme performance
- 📈 High scalability
- 🔄 Elastic capacity adjustments
- 🌍 Distributed architecture
- 🛠️ Abstracted storage layer (focus on business logic, not infrastructure)

---

## 🎯 Use Cases
- 🛣️ Route optimization systems
- 📊 Trade monitoring platforms
- 📉 Applications requiring **low latency**
- 📦 High-throughput, distributed workloads

---

## ⚙️ Throughput Capacity Modes

Amazon Keyspaces provides **two throughput capacity modes**:

---

### 🔥 On-Demand Throughput
- ✅ Default option when creating tables
- 📈 Automatically scales based on workload
- ⚡ Can handle thousands of requests per second
- 💰 Pricing based on actual read and write operations
- 🎯 Ideal for:
  - Unpredictable workloads
  - Variable traffic patterns
  - Applications needing instant scaling

---

### 📊 Provisioned Throughput
- 🎯 Designed for predictable workloads
- 🧮 You specify expected reads and writes per second
- ⚡ Can achieve faster throughput for consistent workloads
- 📈 Supports auto scaling with defined upper and lower thresholds
- 🛠️ Requires more planning and management
- 💰 Can be more cost-effective for steady, predictable traffic

---

# 📌 Amazon Quantum Ledger Database (QLDB)

## 🧠 Overview
- 📖 **Amazon QLDB** is a fully managed, serverless ledger database service
- 🔐 Designed to maintain a **complete and immutable history of data**
- 🧮 Uses cryptographic algorithms such as **SHA-256** to ensure integrity
- 🏢 Centrally managed by a **trusted authority**
- ❌ Unlike blockchain, it does NOT require decentralized consensus
- 🛡️ Ideal for industries requiring high integrity and transparency
  - 🏥 Insurance
  - 👩‍💼 Human Resources
  - 💰 Financial record tracking
- 📄 Uses **Amazon Ion documents** (a superset of JSON)
  - Supports structured and unstructured data
  - Maintains a full audit history of all changes

---

## 🗂️ Storage Architecture

QLDB uses two types of storage:

### 📜 Journal Storage
- 📝 Stores the immutable, append-only transaction log
- 🔗 Each record is cryptographically linked to the previous one
- 🔒 Ensures data cannot be altered without detection

### 📇 Index Storage
- ⚡ Optimized for fast querying
- 📊 Improves performance when retrieving ledger data
- 🔎 Works alongside journal storage for efficient lookups

---

## 🔗 Integration
- 🌊 Integrates with **Amazon Kinesis**
- ⚡ Enables real-time data streaming
- 🔄 Supports event-driven architectures
- 📊 Allows timely insights and automated actions based on data changes

---

## 🧠 Analogy

Imagine a traditional notebook where every time you write something down, you can never erase or change what you wrote—you can only add new pages with updates.

- 📖 Each page = A transaction record
- ➕ New pages can be added
- ❌ Old pages can never be edited or deleted
- 🔗 Each page contains a unique code linking it to the previous one

If someone tried to change an earlier page, the chain would break immediately.

**Amazon QLDB works like this special notebook:**
- 🛡️ Every transaction is permanently recorded
- 🔐 Each record is cryptographically linked to the previous one
- 📜 A complete, verifiable history is always maintained
- 🎯 Perfect for financial records, employee data, or any system requiring absolute integrity