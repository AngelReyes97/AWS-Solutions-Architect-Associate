# 🏢 AWS Organizations Overview

## 🧩 Definition

**AWS Organizations** is a service that allows businesses to **centrally manage multiple AWS accounts**.

As businesses grow, they may require multiple AWS accounts for:

- 🏗️ Better **infrastructure management**
- 💰 **Cost optimization**
- 🔐 **Security**
- ⚖️ **Governance**
- 📦 **Resource grouping**

AWS Organizations helps manage these accounts centrally, reducing **security risks** and improving **compliance and account management**.

---

## 🏗️ AWS Organizations Structure

An AWS Organization forms a **hierarchical structure** for managing AWS accounts.

The main components include:

- 🏢 **Organization**
- 🌳 **Root**
- 📂 **Organizational Units (OUs)**
- ☁️ **Accounts**
- 🛡️ **Service Control Policies (SCPs)**

### 🌳 Root

The **Root** is the top-level container within an Organization.

It sits at the top of the hierarchy and contains:

- 📂 **Organizational Units**
- ☁️ **AWS Accounts**

---

## 📂 Organizational Units (OUs)

**Organizational Units (OUs)** help categorize and group AWS accounts.

They allow accounts to be organized into a **hierarchical structure**.

### 🎯 Example Structure

**Organization → Root → Organizational Units → AWS Accounts**

---

## ☁️ AWS Accounts

AWS accounts can be grouped within **Organizational Units**.

Using multiple accounts allows businesses to organize their infrastructure based on their management needs.

Accounts can be grouped to support:

- 🏗️ Infrastructure management
- 💰 Cost optimization
- 🔐 Security
- ⚖️ Governance
- 📦 Resource grouping

---

## 🛡️ Service Control Policies (SCPs)

**Service Control Policies (SCPs)** control access to **AWS services and features** within AWS accounts.

They act as **permission boundaries**.

SCPs provide greater control over what can be accessed within accounts managed by AWS Organizations.

---

## 🧩 AWS Organizations Hierarchy

The structure can be represented as:

```text
🏢 Organization
      │
      ▼
🌳 Root
      │
      ├── 📂 Organizational Unit
      │       ├── ☁️ AWS Account
      │       └── ☁️ AWS Account
      │
      └── 📂 Organizational Unit
              ├── ☁️ AWS Account
              └── ☁️ AWS Account
```
**SCPs** can be used to control access to AWS services and features within the accounts.

---

## ⚖️ Key Benefits

- 🏢 Provides **centralized account management**.
- 🔐 Helps reduce **security risks**.
- ⚖️ Improves **compliance and governance**.
- 🛡️ Provides enhanced control through **SCPs**.
- 💰 Supports **consolidated billing**.
- 📂 Enables effective **categorization and grouping** of AWS accounts.
- 🏗️ Helps businesses manage multiple AWS accounts as their infrastructure grows.

### 🧠 Key Idea

**AWS Organizations = Centralized management of multiple AWS accounts**

**Root = Top-level container**

**OUs = Group and organize accounts**

**Accounts = Individual AWS environments**

**SCPs = Permission boundaries controlling services and features**

---

# 🏢 AWS Organizations Setup and Configuration

## 🧩 Setup Overview

AWS Organizations can be set up and configured starting from a **master AWS account**.

The master account is responsible for managing the organization and its AWS accounts.

---

## 🔐 Master Account

It is recommended to use the **master account solely for organizational purposes**.

- 🚫 Do not use the master account for **provisioning resources**.
- 🔐 This helps enhance **security**.

The master account has administrative capabilities, including:

- ➕ Creating AWS accounts.
- 📩 Inviting existing AWS accounts.
- ❌ Removing AWS accounts from the organization.
- 🛡️ Applying security policies.

---

## ⚙️ Organization Configuration

When creating an organization, you can choose between:

### 1. 🛡️ All Features

Enabling **all features** allows the organization to use:

- 🛡️ **Service Control Policies (SCPs)**

### 2. 💰 Consolidated Billing

**Consolidated billing** centralizes cost management across the organization.

---

## 📂 Organizational Units

The master account can create **Organizational Units (OUs)** to organize and manage AWS accounts.

For example:

- 🏭 **Production**
- 🧪 **Test**

Accounts can be organized into the appropriate OUs after joining the organization.

---

## 📩 Inviting Existing AWS Accounts

The master account can invite existing AWS accounts to join the organization.

The process involves:

1. 📩 The master account sends an **invitation** to an existing AWS account.
2. 📧 The invited account receives an **email**.
3. ✅ The invited account **accepts the invitation**.
4. 📂 The account can then be organized into an **Organizational Unit**.

---

## 🎯 AWS Organizations Setup Flow

**Create Organization → Choose Organization Features → Create OUs → Invite AWS Accounts → Accept Invitation → Organize Accounts into OUs**

---

## ⚖️ Key Benefits

- 🔐 Keeps the master account focused on **organizational management**.
- 🛡️ Allows the master account to apply **security policies**.
- 📂 Provides **Organizational Units** for account management.
- 📩 Allows existing AWS accounts to be **invited into the organization**.
- 🛡️ **All Features** enables the use of **Service Control Policies**.
- 💰 **Consolidated Billing** centralizes cost management.
- 🏭 Allows accounts to be organized into OUs such as **Production** and **Test**.

### 🧠 Key Idea

**Master Account = Manages the organization**

**All Features = Enables SCPs**

**Consolidated Billing = Centralizes cost management**

**OUs = Organize AWS accounts**

**Invitations = Add existing AWS accounts to the organization**