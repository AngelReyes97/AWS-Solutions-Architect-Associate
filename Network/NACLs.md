# 🧱 Network Access Control Lists (NACLs)  

## 🧩 Definition  
**Network Access Control Lists (NACLs)** are **virtual network-level firewalls** that control **inbound and outbound traffic** at the **subnet level** within a **Virtual Private Cloud (VPC)**.  

- Operate at the **subnet level**, unlike **Security Groups**, which work at the **instance level**.  
- **Stateless** – responses to allowed inbound traffic must be **explicitly permitted** by outbound rules, and vice versa. In other words, they **do not automatically remember** or **track the state of a connection**.  
- Composed of **rules** that define what type of traffic is allowed or denied.  
- Each rule includes:  
  - **Rule number** (evaluated in order, lowest to highest)  
  - **Type** (e.g., SSH, HTTP, HTTPS)  
  - **Protocol** (e.g., TCP, UDP, ICMP)  
  - **Port range**  
  - **Source** (for inbound) or **Destination** (for outbound)  
  - **Action** (allow or deny)  
- **Inbound NACL rules** specify the **source IP address**, while **outbound rules** specify the **destination**.  
- The **default NACL** allows all inbound and outbound traffic, but it is **recommended** to restrict access to only necessary traffic.  
- A **NACL can be associated with multiple subnets**, but each subnet can have **only one NACL**.  
- Any traffic that does **not match an allow rule** is **denied by default**.  

---

![alt text](NACLs.png)

---

## 🧩 Analogy: NACLs as Your Home’s Front Door Security System  

Imagine your **home** has a **security system** at the **front door** that checks the **ID** of anyone who wants to enter — this is your **Network Access Control List (NACL)**.  

- 🚪 The system decides who can **enter or leave** based on pre-set rules — just like NACLs control **inbound and outbound traffic**.  
- 🧍 You might allow only **family members** (specific IP addresses) to enter while denying others.  
- 📦 You could permit **mail delivery** during the day (like allowing HTTP/HTTPS traffic) but **lock the door at night** (deny other protocols).  
- 🧠 The system is **stateless** — it doesn’t “remember” who was allowed in earlier; every new attempt must be **re-evaluated**.  
- 🛑 Any visitor who doesn’t meet the allowed rules is **denied access**, just like NACLs block unauthorized network traffic.  

This ensures that only trusted and necessary connections reach your subnet, adding a **layer of network-level security** to your VPC.  

---

## ⚙️ Key Features and Characteristics  

- 🌐 **Subnet-Level Firewall** – Operates at the **subnet** level, not per instance.  
- 🔁 **Stateless** – Return traffic must be **explicitly allowed** in the opposite direction.  
- ⚖️ **Rule Evaluation Order** – Rules are processed in **ascending order** based on **rule number**.  
- 🧩 **Inbound and Outbound Rules** – Separate sets of rules for controlling incoming and outgoing traffic.  
- 🚫 **Default Behavior** – The **default NACL** allows all traffic; **custom NACLs** deny all traffic until configured.  
- 🔄 **Association Limits** – A single NACL can be linked to **multiple subnets**, but each subnet can have **only one NACL**.  
- 🛡️ **Layered Security** – Works alongside **Security Groups** to provide an **extra layer of protection**.  
- 📜 **Implicit Deny** – Any traffic not explicitly allowed is **automatically denied**.

---