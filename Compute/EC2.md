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

### 🍳 AMI Analogy: The Meal Kit

Imagine you're a **chef preparing a complex dish**:  

- Instead of gathering ingredients, measuring spices, and prepping vegetables from scratch, you receive a **meal kit** delivered to your door.  
- The **meal kit** contains pre-measured ingredients, a recipe card, and even pre-made sauces.  
- You just **follow the recipe** to quickly make your meal.

In this analogy:  

- **Meal kit** = **Amazon Machine Image (AMI)**  
- **Dish** = **EC2 instance**  
- AMI contains the **operating system, applications, and configurations** needed to launch a virtual server.  
- Instead of setting up a server from scratch, you **select an AMI**, and it provides the instance with everything it needs to start running immediately — just like using the meal kit to efficiently cook a meal.  

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
**Amazon Elastic Block Store (EBS)** 💽  
- Provides **persistent and durable block-level storage** for Amazon EC2 instances.  
- **Independent** of EC2 instances, giving flexibility in data management compared to instance store volumes.  
- **Data persistence**: Data remains intact even if the EC2 instance is **stopped, restarted, or terminated**.  
- **Snapshots**: Point-in-time backups stored on **Amazon S3**; incremental, capturing only changes since the last snapshot.  
  - Snapshots can be used to **recreate EBS volumes**, providing resilience and disaster recovery.  
- **Replication**: Volumes are replicated **within the same availability zone** for reliability.  
  - To recover across zones, use snapshots.  
- **Volume types**:  
  - **SSD-backed** ⚡ — For smaller block, transactional workloads.  
  - **HDD-backed** 💾 — For larger block, throughput-intensive workloads.  
- **Encryption** 🔒: Supports data at rest and in transit using **AWS Key Management Service (KMS)**.  
- Can be **created and managed** through the AWS Management Console, with options for **size, type, and encryption**.

### 📚 EBS Analogy
Imagine **EBS (Amazon Elastic Block Store)** as a bookshelf in your house that is dedicated to storing your favorite books. This bookshelf is special because it allows you to add, remove, or replace books at any time without affecting the rest of your house. The books represent the data you store on **EBS volumes**, which can be attached to an EC2 instance **(like adding the bookshelf to a room in your house)**. Even if you decide to renovate the room **(stop, restart, or terminate the EC2 instance)**, your bookshelf and the books on it **remain intact**. You can also **create copies** of your favorite books **(snapshots)** and store them in a safe place **(Amazon S3)**, ensuring that even if something happens to the original books, you have **backups** that can be used to **recreate the bookshelf** exactly as it was.

> 💡 **Tip:** Use **EBS for persistent, block-level storage**, **instance store for temporary high-speed storage**, and **S3 for scalable, durable object storage**.

---

**Instance Store** 🖥️  
- Temporary storage **physically attached** to the EC2 host.  
- Data is **lost** when the instance stops or terminates.  
- Suitable for **temporary or cache data**.

**Amazon S3** 🪣  
- Object storage service for **backups, static website hosting, and large-scale storage**.  
- **Highly durable** and accessible from anywhere.  
- Often used to **store EBS snapshots** and other persistent data.

---

**EC2 Security Groups Overview** 🛡️  
- Security groups act as **virtual firewalls** for your EC2 instances.  
- They control **both inbound and outbound traffic** at the **instance level**.  
- Unlike **Network Access Control Lists (NACLs)**, which operate at the subnet level, security groups are **directly applied to instances**.

**Key Pairs** 🔑  
- Consist of a **public key** and **private key**  
- **Public key**: Managed by AWS  
- **Private key**: Must be **securely stored by the user**  
- Used to **encrypt and decrypt login information** for EC2 instances

**AWS Shared Responsibility Model** ☁️  
- Defines **security and compliance obligations** of AWS and its customers.  
- **AWS responsibility ("of" the cloud)**:  
  - Protects the infrastructure running AWS Cloud services  
  - Includes **hardware, software, networking, and facilities**  
- **Customer responsibility ("in" the cloud)**:  
  - Manage security of **data, applications, and operating systems**  
  - Configure **security settings**, manage **user access**, ensure **data encryption**  
- Understanding this division is key to a **secure cloud environment**  
  - AWS provides the **foundational security**  
  - Customers build upon it with their own **security measures**

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
 