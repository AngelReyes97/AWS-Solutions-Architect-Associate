# 📌 Data Migration and Storage Solutions

## 🧠 Overview
- ⚡ Efficient data migration, storage, and backup are key for high availability, performance, and disaster recovery in AWS
- 🗂️ Choose services and storage based on data volume, durability, and performance requirements

---

## 🔄 Data Migration

- **AWS DataSync**  
  - For migrating **large volumes of data** to:
    - Amazon S3  
    - Amazon EFS  
    - Amazon FSx  
  - Ideal for **machine learning** and **life sciences** workloads

- **AWS Direct Connect**  
  - Recommended for **high network performance** transfers

- **AWS Snowball**  
  - Suitable for **data volumes >50 TB**  
  - Secure offline transfer to AWS

- **AWS Database Migration Service (DMS)**  
  - Migrate databases like **Oracle**, **SQL Server** to Amazon RDS  

---

## 💾 Storage Options

- **Persistent storage** preferred unless otherwise specified
- **Amazon EBS**  
  - Enhanced networking for maximum performance  
  - Supports Multi-Attach for **up to 16 Linux instances** in the same AZ
- **Amazon S3** – Durable object storage  
- **Amazon Glacier** – Long-term archives  
- **Amazon FSx / EFS** – Managed network file systems  

- **High Performance Storage**  
  - Nitro-based EC2 Instances with **EBS-provisioned IOPS SSD (io1/io2)** for high IOPS workloads  

---

## 📤 Data Transfer & Backup

- **Data Transfer Options**:
  - AWS Direct Connect  
  - VPN  
  - AWS Snowball  
  - Storage Gateway (File, Volume, Tape)  

- **AWS Snowball** – Ideal for **large, secure transfers**  
- **Storage Gateway** – Integrates **on-premises storage** with AWS, supports backups and DR  

---

## 🛡️ Disaster Recovery & Backup

- **RTO (Recovery Time Objective)** & **RPO (Recovery Point Objective)** critical for DR planning
- **Amazon S3 Storage Classes**:
  - Standard – Frequent access, high durability  
  - Infrequent Access – Lower cost, less frequent access  
  - Glacier – Archival storage, lowest cost  
- Choose based on durability, availability, and cost

---

## 🔒 Security & Compliance

- Access controls:
  - IAM Policies  
  - Bucket Policies  
  - Access Control Lists (ACLs)
- Encryption:
  - At-rest and in-transit options
- Additional Enhancements:
  - Cross-region replication for DR  
  - Multipart uploads for improved performance