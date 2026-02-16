# 📌 Amazon RDS Multi-AZ

## 🧠 Overview
- 🌍 **Multi-AZ in Amazon RDS** deploys a secondary RDS instance in a different Availability Zone (AZ)
- 🛡️ Ensures resiliency and business continuity
- 🔁 The secondary instance serves as a failover option for the primary
- 📖 Not used for offloading read-only traffic (that is the role of read replicas)
- 🔄 Data replication between primary and secondary is synchronous
- ⚡ Failover is automatic and managed by AWS

---

## 🚨 Failover Scenarios
Failover can occur due to:

- 🛠️ Maintenance events  
- 💥 Host failure  
- 🌍 Availability Zone failure  
- 🔄 Instance reboot with failover  
- 🖥️ Instance class modification  

---

## 🔔 Monitoring & Notifications
- 📩 Failover notifications can be configured via:
  - SMS  
  - SNS  
- 📋 Events are recorded in the RDS Console

---

## 🗄️ SQL Server Multi-AZ
- 🔁 Uses SQL Server Mirroring
- 🌍 Requires a database subnet group with at least two AZs
- 🔗 Primary and secondary instances share the same endpoint

---

## 🐘 Amazon Aurora & Multi-AZ
- 🛡️ Aurora clusters are fault-tolerant by default
- 🔄 Data is replicated across different AZs
- ⚡ Enabling Multi-AZ reduces failover time
- 🔁 A replica is automatically promoted to primary upon failure
- 📈 Up to 15 replicas can be created
- 🎯 Each replica has a priority for takeover in case of failure

---

## 🧠 Analogy

Imagine you own a popular bakery in a city.

- 🥖 You open a second bakery in another part of town
- 🔄 Every loaf baked in the main bakery is immediately copied to the second bakery
- 🍞 Both bakeries always have the same fresh bread

---

### 🚨 If the Main Bakery Fails
- ❌ Power outage or fire shuts it down
- 🟢 The second bakery immediately serves customers
- 👥 Customers may not even notice the switch

---

### 💡 In IT Terms
- 🏪 Primary database = Main bakery  
- 🏪 Standby database = Second bakery  
- 🔄 Synchronous replication