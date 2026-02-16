# 📌 High Availability (HA) vs Fault Tolerance (FT)

## 🧠 Overview
- 🛡️ Both **High Availability (HA)** and **Fault Tolerance (FT)** aim to keep systems operational during failures
- ⚖️ They differ in approach and level of resilience
- 🎯 The choice depends on business impact and acceptable downtime

---

## 🟢 High Availability (HA)

- 📊 Focuses on maintaining a specific uptime percentage
- 📜 Often aligned with Service Level Agreements (SLAs)
- 🏗️ Uses strategies such as:
  - Multiple Availability Zones (AZs)
  - Load balancing
- ⏳ Allows minimal downtime
- 💡 Example:
  - Deploy applications across two AZs
  - Use multiple EC2 instances
  - If one instance or AZ fails, service continues

---

## 🔵 Fault Tolerance (FT)

- 🚫 Provides uninterrupted service even if multiple components fail
- 💰 Typically incurs higher costs due to increased resiliency
- 🌍 Infrastructure can be mirrored across multiple regions
- 🛡️ Operations continue even if an entire region fails
- ⏱️ Offers greater uptime than HA

---

## 🔁 Relationship Between HA and FT
- ✅ Fault-tolerant systems are inherently highly available
- ❌ Not all highly available systems are fault-tolerant
- 🎯 Decision depends on:
  - Business impact of failure
  - Acceptable level of downtime

---

## 🧠 Analogy

### 👨‍🍳 High Availability
- 🍽️ Like having several chefs in the kitchen
- 🤒 If one chef calls in sick:
  - Others keep the kitchen running
  - Service may be slightly slower
- ⏳ Customers still get meals
- 🟢 The restaurant stays open

---

### 👨‍🍳👨‍🍳 Fault Tolerance
- 🧑‍🍳 Each working chef has a backup chef beside them
- ⚡ If something happens:
  - The backup chef steps in immediately
- 🚫 Customers notice no disruption
- 🔄 Service continues without delay

---

## 🎯 Key Difference
- 🟢 High Availability → Minimizes downtime  
- 🔵 Fault Tolerance → Eliminates downtime