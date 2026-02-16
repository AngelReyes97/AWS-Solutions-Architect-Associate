# 📌 Disaster Recovery (DR) Definitions

## 🧠 Overview
- 🚨 **Disaster Recovery (DR)** aims to restore operations quickly with minimal data loss  
- 🌪️ Addresses catastrophic events such as:
  - Natural disasters  
  - Unauthorized access  
- 🎯 Focuses on minimizing business disruption and impact  

---

## ⏱️ Recovery Time Objective (RTO)
- 🕒 Defines the **maximum allowable time** a service can be unavailable  
- 💥 Beyond this time, the business experiences unacceptable damage  
- 🔧 Determines how quickly systems must be restored after a disaster  
- 📌 Example:
  - If RTO = **2 hours**
  - The service must be operational within **2 hours** after an outage  

---

## 💾 Recovery Point Objective (RPO)
- 📍 Defines the **maximum acceptable amount of data loss**
- ⏳ Indicates how far back in time data must be restored after disruption  
- 🗂️ Helps determine **backup frequency**
- 📌 Example:
  - If RPO = **8 hours**
  - Data must be restored from a backup no older than **8 hours** before the outage  

---

## 🎯 Importance in Disaster Recovery
- 🧩 Both **RTO and RPO** are critical in building an effective DR (Disaster Recovery) strategy  
- 📊 Establish maximum tolerance levels for business impact  
- 🛠️ Guide the design of backup and recovery solutions  

---

## 🏗️ Disaster Recovery Strategies

Different strategies provide varying levels of complexity, cost, RTO, and RPO.

---

### 💿 Backup & Restore
- 💰 Simplest and least expensive strategy  
- 📈 Highest RTO and RPO  
- ⏱️ Typical RTO: **24 hours or less**  
- 💾 RPO: **Measured in hours**  
- 🔄 Involves restoring data from backups  
- 🐢 Can be time-consuming, especially with large data volumes  

---

### 🔦 Pilot Light
- ⚙️ More complex than Backup & Restore  
- ⏱️ RTO: **A few hours**  
- 💾 RPO: **Minutes**  
- 🔁 Replicates data between primary and DR regions  
- 🏗️ Maintains critical core infrastructure in the DR region  
- 🚀 Enables faster scaling and recovery  
- ⚡ Some resources remain inactive until needed  

---

### 🔥 Warm Standby
- 🏗️ Builds on the Pilot Light strategy  
- ⏱️ RTO: **Minutes**  
- 💾 RPO: **Seconds**  
- 🖥️ A scaled-down version of the primary region runs in the DR region  
- ⚡ Allows immediate processing of requests  
- 💰 More expensive due to continuously running DR resources  

---

### 🌍 Multi-Site Active/Active
- 💰 Most complex and costly strategy  
- ⏱️ Near-zero RTO  
- 💾 Near-zero RPO  
- 🌐 Both primary and DR regions are fully operational  
- 🔄 Both regions actively handle requests  
- 🛡️ Ensures minimal disruption during failure  
- 🏗️ Requires significant infrastructure and management investment  

---

## 🧠 Analogy

Imagine your business is like a busy restaurant.

Every day:
- 🍽️ You serve customers  
- 👨‍🍳 You cook meals  
- 🔄 You keep operations running smoothly  

Now imagine a disaster:
- 🔥 A kitchen fire  
- ⚡ A power outage  

Suddenly, your restaurant cannot operate.

---

### 🚨 Disaster Recovery = Your Emergency Plan

Disaster Recovery is like having a well-prepared emergency plan for your restaurant.

You might have:
- 🔌 Backup generators (for power)  
- 🏢 A second kitchen in another location  
- 📞 A list of emergency contacts  

This plan allows you to:
- 🔄 Resume serving customers quickly  
- 💰 Minimize financial losses  
- 🛡️ Reduce long-term damage  

---

### 🎯 The Big Idea

Just as a restaurant must recover quickly to avoid losing customers and money, a business needs a Disaster Recovery plan to restore operations and minimize losses after unexpected events.

It’s all about being ready to bounce back — no matter what happens.

---

# 📌 Determining RTO and RPO

## 🧠 Overview
- 📖 Reviewing cloud architecture and applications is necessary to determine the correct **Recovery Time Objective (RTO)** and **Recovery Point Objective (RPO)**
- 🧩 Each application must be assessed individually
- ⚖️ Different applications require different levels of RTO and RPO
- 🚫 There is no universal metric for RTO and RPO
- 🏢 Values depend on internal business factors
- 🛠️ RTO and RPO must be evaluated before designing a disaster recovery strategy

---

## 🔍 Assessing Applications Individually
- 📱 Every application has unique requirements
- ⚠️ The impact of downtime differs between applications
- 🎯 Proper classification ensures the correct recovery objectives are assigned

---

## ❓ Key Questions to Determine RTO and RPO
When defining recovery objectives, consider:

- 💥 What is the impact if the application is unavailable?
- 💰 What are the financial costs of downtime?
- 🏷️ What are the reputational consequences?
- 📜 Are there service level agreements (SLAs) to meet?
- 🔗 Are there application dependencies?
- ⚖️ Are there regulatory requirements?

---

## ⏱️ RTO and RPO Range
- 📊 Recovery objectives can range from **seconds to days**
- 🧩 The final values depend on business tolerance and impact analysis

---

## 💾 Special Considerations for RPO
- 🔁 Can the data be easily recreated?
- 📈 How frequently does the data change?
- 🗂️ These factors help determine appropriate backup frequency

---

## 🛠️ AWS Resilience Hub
- 🧰 Mentioned as a tool to manage application resilience
- ✅ Helps validate resilience within AWS infrastructure