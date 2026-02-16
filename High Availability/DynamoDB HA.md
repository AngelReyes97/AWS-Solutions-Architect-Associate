# 📌 DynamoDB High Availability (HA)

## 🧠 Overview
- ⚡ **AWS DynamoDB** is a fully managed, schemaless NoSQL database
- 🌍 Designed to partition data and traffic across multiple backend servers
- 🏗️ HA is achieved by distributing data across **three Availability Zones (AZs)** within a region
- 💾 Each partition is a dedicated SSD storage area
- 🔁 Data in each partition is **synchronously replicated** across all three AZs
- 🛡️ Provides protection against node or zone outages

---

## 🔧 Throughput & Partitioning
- 📈 Provisioned throughput can be adjusted based on application needs
- 🔄 Automatic partitioning and replication ensures HA and performance
- 🏗️ Partitions scale automatically with data and traffic

---

## 🌎 Cross-Region Replication (Global Tables)
- 🔁 Allows a single DynamoDB table to be replicated across multiple AWS regions
- ⚡ Enhances data availability and reduces latency by serving data from the nearest replica
- 🔄 Supports **multi-master read/write** capability with **eventual consistency**
  - Reads and writes can occur from any configured table
  - Near **sub-second replication** to other tables
- 🛠️ Existing tables can be converted to Global Tables using:
  - AWS DynamoDB Console  
  - AWS CLI  

---

## 🎯 Key Takeaways
- ✅ DynamoDB ensures HA **within a region** through multi-AZ synchronous replication
- ✅ **Global Tables** extend HA **across regions**, with multi-master read/write support
- ⚡ Scales automatically to meet application throughput and resilience requirements

---

## 🧠 Analogy

Imagine you run a popular chain of coffee shops across a city. You want to make sure that no matter what happens—bad weather, a power cut, or a sudden rush of customers—your customers can always get their coffee quickly and reliably.

### ☕ Single Shop, Multiple Baristas (Multi-AZ within a region)
- Each shop has three baristas (availability zones)
- If one barista is unavailable, the others keep serving customers
- Orders are written in at least two places before being finalized, so nothing is lost

### 📜 Backup Recipes (On-Demand Backups & Point-in-Time Recovery)
- Keep backup copies of your secret coffee recipes in a safe
- If something goes wrong, you can restore your shop to how it was at any point in time

### 🌍 Shops in Multiple Cities (Global Tables)
- Open identical shops in different cities (regions)
- Each shop can serve and take orders independently
- All shops keep menus and orders in sync
- If one city has a problem, customers can go to another shop and get the same service

---

### 💡 Takeaway
Your coffee business (DynamoDB) is always available, fast, and resilient—no matter what happens!

---

# 📌 DynamoDB On-Demand Backups

## 🧠 Overview
- 📝 **On-demand backups** allow users to manually request a full backup of a DynamoDB table at any time
- 🖥️ Can be initiated via:
  - AWS DynamoDB Console  
  - AWS CLI
- 🎯 Useful for scenarios like:
  - Table corruption  
  - Compliance requirements  
  - Testing
- ♾️ No limit on the number of backups or their retention period
- ⚡ Does not affect table performance

---

## 🔧 Creating & Restoring Backups
- 📋 Example using AWS CLI:
  - Command: `aws dynamodb create-backup`
- ⏱️ Backup process is fast, typically completing within seconds
- 🔄 Restoration process:
  - Select the backup in the console  
  - Name the new table  
  - Click **Restore**
- ⏳ Restoring usually takes 2–5 minutes

---

## 🧠 Analogy

Imagine your database is like a notebook where you write important information every day.

- 📄 An on-demand backup is like taking a photocopy of your notebook at a specific moment—whenever you choose
- 🗂️ You can make as many photocopies as you want, and each is safely stored in a folder

### 🚨 If Something Happens
- ☕ Maybe you spill coffee on your notebook or tear out a page
- ✅ Use a saved photocopy to restore your notebook to how it was at the time of that backup
- 🔄 You never lose important notes and can always go back to a previous version whenever needed

---

# 📌 DynamoDB Point-In-Time Recovery (PITR)

## 🧠 Overview
- ⏱️ **Point In Time Recovery (PITR)** allows recovery of table data to a **specific point in time**
- 🎯 Useful when data modifications are incorrect or undesired
- 🗄️ Operates at the **table level**
- 🕒 Can recover data from **any time within the last 35 days**
- ⚠️ Disabled by default; must be enabled to use
- 📅 Recovery requests require specifying **date and time with second-level precision**
- 🔄 Restorations are performed into a **new table**
  - Can be in the same region or a different region from the original table

---

## 🧠 Analogy

Point-in-time recovery is like using the **“undo”** feature in a word processor.

- 📝 Imagine you’re writing a long document and accidentally delete a paragraph
- ⏮️ If you’ve been saving versions, you can go back to a version from just before the mistake
- 🔄 Restore the document, losing only changes made after that point

### 💡 In Database Terms
- PITR lets you restore table data **exactly as it was** at a chosen moment
- ✅ “Undo” mistakes or recover from problems without losing all work
- ⚡ Only changes after the selected point are lost