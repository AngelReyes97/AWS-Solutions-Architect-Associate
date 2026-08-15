# 🏰 AWS Control Tower Overview

## 🧩 Definition

**AWS Control Tower** is a service designed to simplify the **creation, management, and auditing of multiple AWS accounts**.

It orchestrates over **14 different AWS services** to provide centralized management.

---

## 🎛️ Centralized Management

AWS Control Tower provides a **centralized console** for managing:

- 👤 **Identity and access management**
- 🏢 **Account management**
- 📝 **Logging**
- 🔐 **Security**

This eliminates the need to individually set up these services.

---

## 🏗️ Multi-Account Environment

AWS Control Tower allows you to:

- ➕ Create new **multi-account environments**.
- 🏢 Extend governance into **existing AWS accounts**.
- ⚖️ Apply consistent **controls and governance** across AWS accounts.

---

## 🏗️ Landing Zone

AWS Control Tower is built around the concept of a **Landing Zone**.

A **Landing Zone** is a **multi-account architecture** that follows:

- 🔐 Security best practices
- ⚖️ Compliance best practices

Control Tower automatically creates the Landing Zone using **best practice blueprints**.

---

## 📂 Organizational Units

AWS Control Tower provisions **three Organizational Units (OUs)**:

### 1. 🌳 Root OU

The **Root OU** is the top-level organizational unit.

### 2. 🛡️ Core OU

The **Core OU** contains:

- 📝 **Log Archive account**
- 🔍 **Audit account**

### 3. 💼 Custom OU

The **Custom OU** contains **working accounts**.

---

## 👤 Identity Management

AWS Control Tower integrates identity management through:

**AWS Single Sign-On**

This provides centralized identity management across the multi-account environment.

---

## 📝 Logging and Auditing

AWS Control Tower provides centralized:

- 📝 **Logging**
- 🔍 **Auditing**

This helps provide visibility across AWS accounts.

---

## 🛡️ Control Types

AWS Control Tower provides three types of controls:

### 🔍 Detective Controls

Controls that help **detect** issues.

### 🚫 Preventive Controls

Controls that help **prevent** actions that violate governance requirements.

### 🔮 Proactive Controls

Controls that help evaluate resources **proactively**.

---

## 💰 Pricing

There is **no additional charge** for using AWS Control Tower itself.

However, users must pay for the **underlying AWS services** that Control Tower provisions.

For example:

- ⚙️ **AWS Config** for compliance controls.

---

## ⚖️ Key Benefits

- 🏢 Simplifies management of **multiple AWS accounts**.
- 🎛️ Provides a **centralized management console**.
- 🔐 Helps establish consistent **security and governance**.
- 🏗️ Creates multi-account environments using a **Landing Zone**.
- 📐 Uses **best practice blueprints**.
- 📂 Provisions **Root, Core, and Custom OUs**.
- 👤 Integrates identity management through **AWS Single Sign-On**.
- 📝 Provides centralized **logging and auditing**.
- 🛡️ Supports **Detective, Preventive, and Proactive controls**.
- 🔄 Extends governance into **existing AWS accounts**.
- 💰 Has no additional Control Tower charge, but users pay for the **underlying services** it provisions.

### 🧠 Key Idea

**AWS Control Tower = Simplifies multi-account AWS management**

**Landing Zone = Best-practice multi-account architecture**

**Core OU = Log Archive + Audit accounts**

**Custom OU = Working accounts**

**Controls = Detective + Preventive + Proactive**