# 🧩 General Purpose SSD (GP2/GP3) Storage for Amazon RDS

## 🧠 Definition  
General Purpose SSD Storage is a **versatile and cost-effective** storage option for Amazon RDS, designed to support a broad range of workloads.  
It provides **single-digit millisecond latencies**, making it suitable for most transactional and operational database use cases.

This storage type is used as **primary storage** for RDS engines such as:  
- **MySQL**  
- **PostgreSQL**  
- **MariaDB**  
- **Oracle**  

It supports a **minimum of 20 GiB** and up to **64 TiB** of storage for these engines.  
For **SQL Server**, the maximum storage supported is **16 TiB**.

Charges are based on the **amount of storage provisioned**, *not* on the number of I/O operations performed, making cost predictable.

General Purpose SSD Storage is recommended over **Magnetic Storage**, which is only maintained for **backward compatibility**.

---

## ⚙️ Features and Considerations  
- 📦 Supports 20 GiB to 64 TiB (16 TiB for SQL Server).  
- ⚡ Single-digit millisecond latency performance.  
- 💸 Pricing based on **provisioned storage**, not I/Os.  
- 👍 Recommended over Magnetic Storage for nearly all modern workloads.  
- 🧰 Works across major RDS database engines.

---

## ⚖️ Key Takeaways  
- Ideal for **general-purpose workloads** requiring balanced performance and cost.  
- Predictable pricing due to storage-only billing.  
- Magnetic Storage should only be used for legacy needs.  

---

# 🧩 Provisioned IOPS (SSD) Storage for Amazon RDS

## 🧠 Definition  
Provisioned IOPS (SSD) storage is designed for **high-performance workloads** that require consistently high input/output operations per second (IOPS).  
It allows you to **provision a specific IOPS level**, ensuring predictable, low-latency performance for demanding applications.

For **MySQL, PostgreSQL, MariaDB, and Oracle**, users can provision between **8,000 and 80,000 IOPS**.  
For **SQL Server**, the maximum is **40,000 IOPS**.

The minimum storage requirement is **100 GiB**, with support for up to:  
- **64 TiB** for MySQL, PostgreSQL, MariaDB, and Oracle  
- **16 TiB** for SQL Server  

Pricing is calculated based on:  
- The **amount of storage provisioned**  
- The **IOPS throughput** selected  
—not the total number of I/O operations performed.

This storage option is ideal for applications with **high I/O demands**, offering **predictable performance** and **low latency**.

---

## ⚙️ Features and Considerations  
- ⚡ Supports **8,000–80,000 IOPS** (or **up to 40,000 IOPS** for SQL Server).  
- 💾 Requires **minimum 100 GiB** of storage.  
- 📦 Max storage: **64 TiB** (most engines) or **16 TiB** (SQL Server).  
- 💸 Costs depend on **provisioned storage + selected IOPS throughput**.  
- 🧩 Ideal for performance-intensive, latency-sensitive applications.

---

## ⚖️ Key Takeaways  
- Best choice for workloads needing **high, consistent I/O performance**.  
- Predictable billing based on provisioned resources.  
- Provides reliable, low-latency behavior for critical databases.

---

# 🧩 Amazon RDS Storage Options Overview

## ⚖️ Key Takeaways 
- Storage pricing varies between single-AZ and Multi-AZ deployments, with Multi-AZ typically costing twice as much.
- Storage costs are calculated using the GB-Month metric, which considers the amount of storage provisioned and the duration of use.
- Aurora's storage scales automatically with database growth, and its pricing is based on actual storage used and I/Os processed, unlike other DB engines where charges are based on provisioned storage regardless of if you use all of it or just part of it.