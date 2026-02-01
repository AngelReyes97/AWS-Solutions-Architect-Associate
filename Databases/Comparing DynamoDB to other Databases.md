# 📌 Comparing DynamoDB to Other Databases

## 🧠 Overview
- **Amazon DynamoDB** is a fully managed **NoSQL** database designed for **high scalability and low latency**
- It differs significantly from **relational databases** (MySQL, Oracle) in how it:
  - Scales
  - Structures data
  - Handles queries
- DynamoDB is also comparable to other **NoSQL databases** (e.g., MongoDB) but is **AWS-native**

---

## 🚀 Scaling Differences
- **DynamoDB**
  - Scales **horizontally** 📈
  - Adds more servers automatically as traffic increases
  - No downtime during scaling
- **Relational Databases (MySQL, Oracle)**
  - Scale **vertically** 🏗️
  - Increase CPU, RAM, or storage on a single server
  - Scaling can be expensive and disruptive

---

## 🧩 Schema & Data Model
- **DynamoDB**
  - **Schemaless** 🧠
  - Each item can have different attributes
  - Supports **key-value** and **document** data models
- **Relational Databases**
  - Require a **fixed schema**
  - Tables must be predefined
  - Schema changes often require migrations

---

## 🔍 Query Capabilities
- **DynamoDB**
  - Does **not** support full SQL
  - Queries are based on:
    - Partition keys
    - Sort keys
  - Supports **PartiQL** (SQL-like syntax) for simpler querying
- **Relational Databases**
  - Support **full SQL**
  - Highly flexible queries with joins, filters, and aggregations

---

## 📦 Data Types & Limitations
- **DynamoDB**
  - Limited native data types
  - Some data (e.g., dates) must be stored as:
    - Strings
    - Numbers
  - **Maximum item size: 400 KB** ⚠️
    - Large objects must be stored elsewhere (e.g., S3)
  - Some limits can be increased by contacting AWS Support
- **Relational Databases**
  - Rich set of native data types
  - No strict per-row size limit like DynamoDB

---

## 🔄 DynamoDB vs Other NoSQL Databases
- Similar to **MongoDB** in being NoSQL
- Key differences:
  - DynamoDB is **AWS-specific**
  - Fully managed with built-in scaling
  - Designed for predictable performance at massive scale

---

## 🧪 Exam Tips (SAA Focus)
- Choose **DynamoDB** when you see:
  - Serverless
  - Massive scale
  - Single-digit millisecond latency
  - Key-value or document access
- Choose **RDS** when you see:
  - Complex SQL queries
  - Joins
  - Transactions across multiple tables
- Remember the **400 KB item size limit** ⚠️
- DynamoDB = **horizontal scaling**, not vertical

---

## 🧠 Analogy
> Traditional databases (MySQL, Oracle) are like a **large library** 📚:
> - Strict organization (fixed schema)
> - Every book must fit on predefined shelves
> - Scaling means building a **bigger building** (vertical scaling)

> DynamoDB is like a **vast open field** 🌾:
> - Place books anywhere
> - Add new item types without restructuring
> - Scaling means adding **more land** (horizontal scaling)
> - Faster to expand, but requires planning how you find things

---

## ✅ Quick Summary
- DynamoDB is a **schemaless, NoSQL, AWS-native database**
- Scales **horizontally** and automatically
- Less flexible querying than SQL databases
- Best for **high-scale, low-latency** applications
- Requires careful data modeling for efficient access

---

# 📌 Interacting with DynamoDB

## 🧠 Overview
- 🗄️ **DynamoDB** provides multiple ways to interact with tables and data
- 🧰 You can manage tables, read/write items, and run transactions
- 🧪 AWS exams test **which interaction method** and **which API type** to use

---

## 🧰 Ways to Interact with DynamoDB
- 🖥️ **AWS Management Console**  
  - Visual UI for managing tables and data
  - Best for learning, testing, and quick changes

- 📞 **AWS CLI**  
  - Command-line interaction with DynamoDB
  - Useful for scripting and automation

- 🧑‍💻 **AWS SDKs**  
  - Programmatic access using languages like Java, Python, and JavaScript
  - Most common method in production applications

- 🗺️ **NoSQL Workbench for DynamoDB**  
  - Visual data modeling and table design
  - Helps explore and interact with data efficiently

---

## ⚙️ DynamoDB API Structure
- 📦 DynamoDB APIs are organized into **operations**
- 📝 Each operation:
  - Requires specific **input parameters**
  - Returns defined **outputs**
- 🧪 Operations are grouped into **three main categories**:
  - 🛠️ Control Plane
  - 📊 Data Plane
  - 🔐 Transactions

---

## 🛠️ Control Plane Operations
> Used to manage **tables**, not the data inside them

- 🆕 **CreateTable**
  - Creates a new DynamoDB table
  - Defines primary keys and capacity settings

- 🔧 **UpdateTable**
  - Modifies existing table settings
  - Used to:
    - 🚀 Change provisioned throughput
    - ➕ Add Global Secondary Indexes (GSIs)

- 🗑️ **DeleteTable**
  - Deletes a table and **all data** inside it
  - ⚠️ Destructive and irreversible

📌 **Use case**: Setting up, modifying, or removing database structures

---

## 📊 Data Plane Operations (CRUD)
> Used to **Create, Read, Update, and Delete data**

### 📥 Read Operations
- 🔍 **GetItem**
  - Retrieves **one item**
  - Requires the **primary key**

- 📦 **BatchGetItem**
  - Retrieves **multiple items** in a single request
  - More efficient than multiple GetItem calls

- 🔎 **Query**
  - Requires a **partition key**
  - 🧭 Optional **sort key condition**
  - 🧹 Supports **filter expressions** (applied after query)

📌 **Important**: Query ≠ Scan (Scan reads the entire table)

---

## 🔐 DynamoDB Transactions
- 🧾 Provide **ACID compliance**:
  - 🔒 Atomicity
  - 📏 Consistency
  - 🧱 Isolation
  - 💾 Durability
- 🧪 Ensures all operations succeed **or none do**

### 🔁 Transaction APIs
- 📖 **TransactGetItems**
  - Reads multiple items atomically

- ✍️ **TransactWriteItems**
  - Writes across multiple tables atomically

- 🧾 **PartiQL Transactions**
  - Uses **ExecuteTransaction**
  - SQL-like syntax for transactional operations

📌 **Use cases**:
- 💰 Banking systems
- 📦 Inventory management
- 🔁 Multi-step operations that must succeed together

---

## 🧪 Exam Tips (SAA Focus)
- 🛠️ **Control plane** = table management
- 📊 **Data plane** = item-level CRUD
- 🔐 **Transactions** = ACID guarantees
- 🔎 Query requires a **partition key**
- ⚠️ Filter expressions do **not** reduce read capacity usage
- 🧠 PartiQL ≠ full SQL

---

## 🧠 Analogy
> DynamoDB is a **large, secure library** 📚

- 🖥️ **AWS Console** = front desk where you view and manage books
- 📞 **AWS CLI** =  like using a telephone to make specific requests to the library staff, asking them to fetch or update information on your behalf without you being physically there.
- 🧑‍💻 **AWS SDKs** = a personal assistant who handles requests for you
- 🗺️ **NoSQL Workbench** = an interactive map and toolkit for navigating shelves

Each method provides a different way to access and manage the same library, depending on your needs.

---

## ✅ Quick Summary
- 🧰 DynamoDB supports multiple interaction methods
- 🛠️ Control plane manages tables
- 📊 Data plane handles CRUD operations
- 🔐 Transactions provide ACID compliance
- 🧪 Choosing the correct API type is key for the SAA exam