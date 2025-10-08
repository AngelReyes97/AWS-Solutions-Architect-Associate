# 🖥️ Amazon EC2 (Elastic Compute Cloud)

**Amazon EC2** stands for **Elastic Compute Cloud** — it’s a web service that gives you **virtual servers** 🧩 in the **AWS Cloud**.  
These servers provide **resizable compute power**, meaning you can make them **bigger or smaller** depending on your needs.  

Think of EC2 as **your own computer in the cloud** ☁️ that you can turn on, use, and pay for only while it’s running. 💰

---

## 🏢 Easy Analogy: The Cloud Apartment Complex

Imagine **EC2** as a **giant apartment complex in the cloud** 🏙️.  
Each apartment (or **EC2 instance**) can be customized to your liking:

- 🏠 **Size** = **Instance Type** (choose how big or small your server is)  
- 🎨 **Interior Design** = **Operating System and Applications** via **AMIs**  
- 📜 **Lease Agreement** = **Purchasing Option** (On-Demand, Reserved, or Spot)  
- 🔒 **Security** = **Security Groups** (control who can enter your apartment)  
- ⏱️ **Short-Term Lease** = **Spot Instance** (cheap but temporary)  
- 💼 **Long-Term Lease** = **Reserved Instance** (steady and cost-effective)  
- 🧱 **Auto Scaling** = Add or remove apartments when you need more or less space  

Just like managing your apartment, EC2 lets you decide how much space, power, and security you want — all within the AWS “building.” ☁️

---

## 🚀 Why EC2 Is Important
- EC2 is often the **first compute service** people use in AWS.  
- It’s a key part of many AWS solutions — from **web apps** 🌐 to **databases** 💾.  
- You can control almost everything: the **operating system**, **software**, and **security**.

---

## ⚙️ Key Parts of EC2

### 🧱 Amazon Machine Images (AMIs)
- Pre-made **templates** for launching new servers.  
- Include the **OS** (like Linux or Windows) and sometimes apps (like WordPress or MySQL).  
- Think of an AMI as a **blueprint** 🧩 for your EC2 instance.
- **AWS Marketplace** is essentially an online store that allows you to purchase AMIs from trusted vendors.

---

### 🧮 Instance Types
**Instance types** in AWS EC2 are configurations that define the **size and capability** of an instance, tailored to **specific performance needs**.  

They are grouped into families with distinct purposes:

- **General Purpose** ⚖️ — Balanced mix of CPU, memory, and storage; good for small-to-medium databases, test environments, or web servers.  
- **Compute Optimized** 🏎️ — High CPU performance; ideal for batch processing or machine learning.  
- **Memory Optimized** 🧠 — Large memory for in-memory apps and real-time data processing.  
- **Accelerated Computing** ⚡ — Hardware accelerators for fast floating-point calculations.  
- **Storage Optimized** 💾 — SSD-backed storage for high IOPS; great for data file systems and log processing.  
- **HPC Optimized** 🚀 — Tailored for high-performance computing workloads.  

**Key parameters** to consider: **vCPUs**, **memory**, **instance storage**, and **network performance**.  
With hundreds of instance types, you can **pick exactly what your application needs** for optimal performance.

---

### 💵 Purchasing Options
# 🖥️ Amazon EC2 (Elastic Compute Cloud)

**Amazon EC2** stands for **Elastic Compute Cloud** — it’s a web service that gives you **virtual servers** 🧩 in the **AWS Cloud**.  
These servers provide **resizable compute power**, meaning you can make them **bigger or smaller** depending on your needs.  

Think of EC2 as **your own computer in the cloud** ☁️ that you can turn on, use, and pay for only while it’s running. 💰

---

## 🏢 Easy Analogy: The Cloud Apartment Complex

Imagine **EC2** as a **giant apartment complex in the cloud** 🏙️.  
Each apartment (or **EC2 instance**) can be customized to your liking:

- 🏠 **Size** = **Instance Type** (choose how big or small your server is)  
- 🎨 **Interior Design** = **Operating System and Applications** via **AMIs**  
- 📜 **Lease Agreement** = **Purchasing Option** (On-Demand, Reserved, Spot, etc.)  
- 🔒 **Security** = **Security Groups** (control who can enter your apartment)  
- ⏱️ **Short-Term Lease** = **Spot Instance** (cheap but temporary)  
- 💼 **Long-Term Lease** = **Reserved Instance** (steady and cost-effective)  
- 🧱 **Auto Scaling** = Add or remove apartments when you need more or less space  

Just like managing your apartment, EC2 lets you decide how much space, power, and security you want — all within the AWS “building.” ☁️

---

## 🚀 Why EC2 Is Important
- EC2 is often the **first compute service** people use in AWS.  
- It’s a key part of many AWS solutions — from **web apps** 🌐 to **databases** 💾.  
- You can control almost everything: the **operating system**, **software**, and **security**.

---

## ⚙️ Key Parts of EC2

### 🧱 Amazon Machine Images (AMIs)
- Pre-made **templates** for launching new servers.  
- Include the **OS** (like Linux or Windows) and sometimes apps (like WordPress or MySQL).  
- Think of an AMI as a **blueprint** 🧩 for your EC2 instance.

---

### 🧮 Instance Types
**Instance types** in AWS EC2 are configurations that define the **size and capability** of an instance, tailored to **specific performance needs**.  

They are grouped into families with distinct purposes:

- **General Purpose** ⚖️ — Balanced mix of CPU, memory, and storage; good for small-to-medium databases, test environments, or web servers.  
- **Compute Optimized** 🏎️ — High CPU performance; ideal for batch processing or machine learning.  
- **Memory Optimized** 🧠 — Large memory for in-memory apps and real-time data processing.  
- **Accelerated Computing** ⚡ — Hardware accelerators for fast floating-point calculations.  
- **Storage Optimized** 💾 — SSD-backed storage for high IOPS; great for data file systems and log processing.  
- **HPC Optimized** 🚀 — Tailored for high-performance computing workloads.  

**Key parameters** to consider: **vCPUs**, **memory**, **instance storage**, and **network performance**.  
With hundreds of instance types, you can **pick exactly what your application needs** for optimal performance.  

---

### 💵 Purchasing Options
EC2 provides several **purchasing options** to help optimize costs and fit your workload:

- **On-Demand Instances** 🕒  
  - Launch at any time, billed by the second, no long-term commitment  
  - Ideal for **short-term or irregular workloads** that **cannot be interrupted**, such as testing and development environments

- **Reserved Instances** 💸
  - Discounted for **long-term, predictable workloads**  
  - Purchase a discounted On-Demand Instance for a set period.
  - Commit for 1 or 3 years  
  - Two classes:  
    - **Standard**: Some modifications allowed, cannot be exchanged  
    - **Convertible**: More flexibility, smaller discount  
  - Payment options: **All Upfront, Partial Upfront, No Upfront**  
    - **All Upfront**: Complete payment is paid at the beginning of the term, Offers largest discount, No further payment required
    - **Partial Upfront**: A smaller payment is made at the start of the term, A discount is applied to all remaining hours during the term
    - **No Upfront**: No upfront or partial payments are made, The smallest discount is applied to the remaining hours in the term
  - Savings based on how much money you wish to **pay upfront**

- **Spot Instances** ⚠️  
  - Use **unused EC2 capacity** at a lower cost  
  - Variable **hourly price** based on **supply and demand**
  - Suitable for **interruptible workloads**  
  - Can be terminated if the spot price exceeds your max or capacity is unavailable

- **On-Demand Capacity Reservations** 📌  
  - Reserve capacity for any length of time without a long-term commitment  
  - Ensures availability within a specific **Availability Zone**
  - Typically used for **short-term** workloads
  - Can be combined with Reserved Instances or EC2 Savings Plans for additional cost savings
  - No billing discounts, but you can create and cancel these reservations at any time

- **BYOL (Bring Your Own License)** 🏷️  
  - Currently available for **Oracle Database**  
  - Use your **existing software licenses**  

- **Serverless** ☁️  
  - Available for **Aurora**  
  - Automatically scales based on demand  
  - Flexible and cost-effective for **variable workloads**  

> 💡 **Tip:** Choose the right purchasing option to balance **cost** 💰 and **availability** ⚡ for y

---

### 🏠 Tenancy

**EC2 tenancy** refers to the type of **physical server environment** on which your EC2 instance runs within an AWS data center.  

- **Shared Tenancy** (default) 🌐  
  - Your instance shares the **host server** with instances from **other AWS customers**.  
  - AWS ensures **security isolation** between instances.  
  - Recommended if you have **no special licensing, compliance, or security requirements** to **minimize costs** 💰.

- **Dedicated Tenancy** 🏢  
  - Your instance runs on **dedicated hardware** for your account.  
  - Suitable for workloads with **strict security policies, compliance needs, or licensing requirements**.  
  - Two options:  
    - **Dedicated Instances** 🖥️ — Hosted on hardware **exclusive to your account** no other customer can accesss; may incur extra cost (becuase no other customer's EC2 are on the same hardware) for unused capacity.  
    - **Dedicated Hosts** 🏷️ — Provide **full control** over instance placement and allow use of **existing software licenses tied to hardware**.

> 💡 **Tip:** Use **shared tenancy** unless your workload specifically requires dedicated hardware for **security, compliance, or licensing** reasons.

---

### 🗂️ Storage Options
- **EBS (Elastic Block Store)** 💽 — like a hard drive attached to your EC2.  
- **Instance Store** — temporary storage that’s erased when the instance stops.  
- **S3** 🪣 — separate cloud storage, often used for backups.

---

### 🔒 Security
- **Security Groups** act as **firewalls** 🔥 to control who can access your EC2.  
- **Key Pairs** 🔑 encrypt login credentials so only you can connect safely.

---

## 💡 Common Use Cases
- Hosting **websites** 🌐  
- Running **databases** 💾  
- Powering **applications and APIs** ⚙️  
- Building **testing and development environments** 🧪

---

## 📝 Key Takeaways
- **Amazon EC2** = virtual servers in the AWS cloud ☁️  
- **AMIs** are blueprints for creating instances  
- **Instance types** define CPU, RAM, and performance ⚙️  
- **Purchasing options** (On-Demand, Reserved, Spot) help control cost 💰  
- **Security Groups** and **Key Pairs** keep your instances safe 🔒  
- Used for **websites, databases, and app hosting** 🚀
