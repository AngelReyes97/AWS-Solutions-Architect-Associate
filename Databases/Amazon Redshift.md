# 📌 Amazon Redshift

## 🧠 Overview
- ⚡ **Amazon Redshift** is a fast, fully-managed, petabyte-scale **data warehouse**  
- 🗄️ Designed for **high-performance analysis** of large datasets  
- 🧩 Compatible with **standard SQL** and existing BI tools  
- 🧪 Based on PostgreSQL, but with modifications for data warehousing workloads
- 🚀 Known for **high performance** — AWS claims Redshift is **3× faster** than other cloud data warehouses at the time of the course  

---

## 🏗️ Architecture
- 🧩 **Definition**: A **Redshift cluster** is a set of computing resources (nodes) that work together to run the Redshift data warehouse.  
- 🖥️ Each cluster contains:
  - **One or more compute nodes** – store data and perform query processing, compute node all contain their own CPU, attached storage, and memory.  
  - **Leader node** (if multiple compute nodes exist) – coordinates queries and distributes work across compute nodes, think of it as a **gateway** 
- ⚡ Enables **Massively Parallel Processing (MPP)**:
  - Distributes data processing tasks across multiple compute nodes simultaneously  
  - Each node works on a portion of the data  
  - Leader node coordinates tasks and aggregates results  
  - ✅ Enhances **query performance** and **scalability** for large datasets and complex queries  
- 🗄️ **Columnar Data Storage**:
  - Stores data **column by column** instead of row by row  
  - Reduces the amount of data read from disk for queries (only relevant columns accessed)  
  - Improves **compression**, reducing storage costs  
  - Optimized for **analytical queries** with aggregations and filters    
- 🔄 Clusters can scale by adding nodes to handle **larger data volumes** or more concurrent queries
- 💡 Quick tip: Single-node clusters combine leader + compute roles, while multi-node clusters separate them  

---

## 📊 Integration & Monitoring
- 📊 Integrates with **Amazon CloudWatch** for performance metrics  
- 🔑 Supports **IAM roles** for secure access to other AWS services (e.g., S3)  
- 📈 Can be used with **Amazon QuickSight** to create dashboards and reports for business intelligence and analytics  
---

## 🔄 ETL Process in Redshift
- 🧩 **Extract**: Retrieve data from multiple sources (online, legacy systems, Salesforce, etc.)  
- 🔧 **Transform**: Map, reformat, and enrich data (e.g., currency conversions, standardization)  
- 📦 **Load**: Insert the transformed data into the Redshift data warehouse for analysis  

---