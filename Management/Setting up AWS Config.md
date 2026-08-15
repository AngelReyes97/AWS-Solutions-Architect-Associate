# ⚙️ AWS Config Overview

## 🧩 Definition

**AWS Config** is a service that enables you to:

- 🔍 **Assess** the configurations of AWS resources.
- 📋 **Audit** AWS resource configurations.
- ⚖️ **Evaluate** AWS resource configurations.

It helps track **configuration changes** and maintain compliance with:

- 🏢 **Internal policies**
- ✅ **Best practices**

---

## ⚙️ Setup and Configuration

To set up AWS Config, you need to configure settings to start the **configuration recorder**.

This involves selecting which resources to include in the configuration.

You can choose:

- 🌎 **All resources** in a specific Region.
- 🎯 **Specific resource types**.

### 🌎 Region-Specific

**AWS Config is region-specific.**

This means configurations are recorded **per Region**.

---

## 💾 Storage and Management

AWS Config stores:

- 📜 **Configuration history**
- 📸 **Snapshot files**

These files are stored in an **Amazon S3 bucket**.

You can:

- 🪣 Create a **new S3 bucket**.
- ♻️ Use an **existing S3 bucket**.
- 🏢 Consolidate configuration files from **multiple accounts into a single bucket**.

---

## 🔔 Notification and Monitoring

AWS Config can send notifications about **configuration changes** through an **SNS topic**.

This allows for:

- ⚡ **Real-time monitoring**
- 🚨 **Alerts** when configuration changes are detected.

### 🎯 Basic Flow

**Configuration Change → AWS Config → SNS Topic → Notification**

---

## 🔗 Integration with Other AWS Services

AWS Config integrates with other **AWS services**.

This integration requires specific:

- 🔐 **IAM roles**
- 📜 **IAM policies**

These permissions allow AWS Config to perform **List and Get API calls** against supported services within the Region.

---

## ⚖️ Compliance Management

AWS Config helps manage compliance using **Config Rules**.

**Config Rules** help ensure that AWS resources comply with:

- 🏢 **Organizational policies**
- ✅ **Best practices**

---

## ⚖️ Key Benefits

- 🔍 Assesses AWS resource configurations.
- 📋 Audits resource configurations.
- ⚖️ Evaluates configurations for compliance.
- 📝 Tracks configuration changes.
- 🏢 Helps maintain compliance with internal policies and best practices.
- 💾 Stores configuration history and snapshots in **Amazon S3**.
- 🏢 Supports consolidating configuration files from multiple accounts.
- 🔔 Sends configuration change notifications through **SNS**.
- 🔗 Integrates with other AWS services using IAM roles and policies.
- 📏 Uses **Config Rules** to help ensure resources comply with organizational policies and best practices.

### 🧠 Key Idea

**AWS Config = Assess → Audit → Evaluate → Track configuration changes → Manage compliance.**

CloudTrail = Who did what, when, and how
AWS Config = What your resources look like, and how they’ve changed over time

---

# 📋 AWS Config Configuration Items, History, and Snapshots

## 🧩 Configuration Items

**AWS Config** delivers **configuration items** to an **Amazon S3 bucket**.

Configuration items include:

- 📝 **Metadata**
- ⚙️ **Attributes**
- 🔗 **Relationships**
- 📊 **Current configuration details** of resources

Configuration items are recorded in **JSON format**.

They do **not** include:

- 🌐 **Network data**
- 🏗️ **Application architecture**

---

## 📜 Configuration History

**Configuration history** is a collection of **configuration items for a specific resource over time**.

- 📦 Contains configuration items for a specific resource.
- ⏱️ Delivered to the **S3 bucket every six hours**.
- 📄 Stored in **JSON format**.

### 🎯 Key Idea

**Resource → Configuration Items Over Time → Configuration History → S3**

---

## 📸 Configuration Snapshots

**Configuration snapshots** capture the **state of all resources at a specific point in time**.

Snapshots can be:

- 🖱️ Generated **manually**.
- ⏱️ Generated at **set intervals**.

Configuration snapshots are:

- 📄 Stored in **JSON format**.
- 🪣 Stored in a **separate folder** within the S3 bucket.

---

## 📂 S3 Storage

Both **configuration histories** and **configuration snapshots** are stored in the **Amazon S3 bucket**.

They are:

- 📄 Stored in **JSON format**.
- 📁 Stored in **separate folders**.

---

## ⚙️ Configuration History vs. Snapshots

| Feature | 📜 Configuration History | 📸 Configuration Snapshot |
|---|---|---|
| Purpose | Configuration items for a specific resource over time | State of all resources at a specific point in time |
| Format | JSON | JSON |
| Storage | Amazon S3 | Amazon S3 |
| Setup | Automatically enabled | Requires manual setup |
| Frequency | Every six hours | Set by the user |
| Scope | Specific resource | All resources |

---

## ⚙️ Setup Requirements

### 📜 Configuration History
- ✅ **Automatically enabled**.
- ⏱️ Delivered every **six hours**.

### 📸 Configuration Snapshots
- ⚙️ Require **manual setup**.
- ⏱️ Require **frequency configuration**.

---

## 🌎 AWS Config Aggregators

**Aggregators** in AWS Config consolidate **configuration and compliance data** from:

- 🏢 **Multiple AWS accounts**
- 🌎 **Multiple AWS Regions**

The data is consolidated into a **single account**.

This provides:

- 👀 **Unified visibility**
- 📊 Consolidated configuration data
- ⚖️ Consolidated compliance data

### 🎯 Basic Flow

**Multiple Accounts + Multiple Regions → AWS Config Aggregator → Single Account → Unified Visibility**

---

## ⚖️ Key Benefits

- 📋 Configuration items provide details about AWS resource configurations.
- 📄 Configuration items are stored in **JSON format**.
- 📜 Configuration history tracks configuration items for a specific resource over time.
- 📸 Configuration snapshots capture the state of all resources at a specific point in time.
- 💾 Histories and snapshots are stored in **Amazon S3**.
- 📁 Histories and snapshots are stored in **separate S3 folders**.
- 🌎 Aggregators consolidate configuration and compliance data across **multiple accounts and Regions**.
- 👀 Aggregators provide **unified visibility** into configuration and compliance data.

### 🧠 Key Idea

**Configuration Item = Current resource configuration**

**Configuration History = Resource configuration over time**

**Configuration Snapshot = State of all resources at a specific point in time**

**Config Aggregator = Consolidated configuration and compliance data from multiple accounts and Regions**

---

# ⚖️ AWS Config Rules

## 🧩 Definition

**AWS Config Rules** define the **desired configuration state** for AWS resources and evaluate those resources for **compliance**.

They help determine whether resources meet the required configuration.

---

## 📚 Managed Rules

AWS provides more than **320 managed rules**.

These rules:

- ✅ Can be used **as-is**.
- 🛠️ Can be **customized**.
- ☁️ Cover more than **55 AWS services**.

### 📋 Examples of Managed Rules

Examples include rules that check whether:

- 🌐 **Elastic IPs are attached**.
- 💾 **EBS volumes are in use**.
- 🔐 **SSH access is restricted**.

---

## 🛠️ Custom Rules

Custom AWS Config Rules can be created using:

- ⚡ **AWS Lambda functions**
- 🛡️ **AWS CloudFormation Guard**

### ⚡ AWS Lambda

The **AWS Lambda console** provides **blueprints** that can be used when creating custom rules.

The **AWS Config Rule Development Kit (RDK)** also simplifies rule development.

---

## 🛡️ AWS CloudFormation Guard

**AWS CloudFormation Guard** allows **policy-as-code evaluations**.

It:

- 📝 Uses a **domain-specific language**.
- 🔍 Validates **infrastructure-as-code resources**.
- 💻 Provides a **CLI** for creating and testing rules.

---

## 🔄 Rule Evaluation Modes

AWS Config Rules support two evaluation modes:

### 1. 🔮 Proactive

**Proactive evaluation** occurs **before provisioning**.

It evaluates resources before they are provisioned.

### 2. 🔍 Detective

**Detective evaluation** evaluates **existing resources**.

---

## ⚡ Rule Triggers

AWS Config Rules can be triggered based on:

- 🔄 **Configuration changes**
- ⏱️ **Set frequencies**

This allows rules to evaluate resources based on changes or configured schedules.

---

## ⚙️ Parameters

**Parameters** are important when configuring rules.

They allow rules to perform **specific evaluations** based on the configured parameters.

---

## 🏷️ Tags

**Tags** are also important for rule configuration.

They can be used for **resource grouping** when evaluating resources.

---

## ⚖️ Key Benefits

- ⚖️ Define the **desired configuration state** for AWS resources.
- 🔍 Evaluate resources for **compliance**.
- 📚 Provides more than **320 managed rules**.
- ☁️ Managed rules cover more than **55 AWS services**.
- 🛠️ Supports **custom rules**.
- ⚡ Custom rules can use **AWS Lambda**.
- 🛡️ Supports **AWS CloudFormation Guard** for policy-as-code evaluations.
- 🧰 The **AWS Config Rule Development Kit (RDK)** simplifies rule development.
- 🔮 Supports **proactive** evaluation before provisioning.
- 🔍 Supports **detective** evaluation of existing resources.
- 🔄 Rules can be triggered by **configuration changes** or **set frequencies**.
- ⚙️ Supports **parameters** for specific evaluations.
- 🏷️ Supports **tags** for resource grouping.

### 🧠 Key Idea

**AWS Config Rules = Define desired configuration → Evaluate resources → Determine compliance.**

---

# ⚖️ AWS Config Compliance and Remediation

## 🧩 Compliance Status

AWS Config evaluates resources and rules for **compliance**.

There are three possible compliance statuses:

### 🟢 Compliant
- The resource meets the required configuration.

### 🔴 Noncompliant
- The resource does not meet the required configuration.

### ⚪ Insufficient Data
- There is not enough **evaluation results** to determine compliance.

---

## 👀 AWS Config Visibility

**AWS Config provides visibility into compliance**, but it does **not prevent non-compliant resources**.

When a resource becomes noncompliant, remediation can be:

- 👤 **Manual**
- 🤖 **Automatic**

---

## 🤖 Automatic Remediation

Automatic remediation uses **AWS Systems Manager Automation**.

When a resource becomes **noncompliant**, automatic remediation can trigger an action to address the issue.

Automatic remediation supports:

- 🔄 **Retries**
- ⚙️ **Predefined actions**

### 🎯 Basic Flow

**Resource → AWS Config Rule → Noncompliant → Systems Manager Automation → Remediation Action**

---

## 🛠️ Systems Manager Change Manager

**Systems Manager Change Manager** can be used for:

- ⚙️ **Configuring changes**
- ✅ **Approvals**

---

## 📦 Conformance Packs

**Conformance Packs** are collections of:

- ⚖️ **AWS Config Rules**
- 🛠️ **Remediation Actions**

They can be deployed across:

- 🏢 **Multiple AWS accounts**
- 🌎 **Organizations**

Conformance Packs use **YAML documents**.

---

## 📋 Pre-Fabricated Conformance Pack Templates

AWS provides **pre-fabricated Conformance Pack templates**.

These templates:

- 📚 Provide a **starting point for compliance frameworks**.
- ⚠️ Do **not guarantee compliance** with specific standards.

---

## ⚖️ Key Benefits

- 📊 Provides three compliance statuses: **Compliant, Noncompliant, and Insufficient Data**.
- 👀 Provides **visibility** into resource compliance.
- 🚫 Does **not prevent non-compliant resources**.
- 👤 Supports **manual remediation**.
- 🤖 Supports **automatic remediation** using **AWS Systems Manager Automation**.
- 🔄 Automatic remediation supports **retries** and **predefined actions**.
- 🛠️ **Systems Manager Change Manager** can be used for changes and approvals.
- 📦 **Conformance Packs** combine AWS Config Rules and remediation actions.
- 🏢 Conformance Packs can be deployed across **accounts or organizations**.
- 📄 Conformance Packs use **YAML documents**.
- 📋 Pre-fabricated templates provide a starting point for **compliance frameworks**.

### 🧠 Key Idea

**AWS Config = Evaluate compliance**

**Systems Manager Automation = Automatically remediate noncompliant resources**

**Conformance Packs = AWS Config Rules + Remediation Actions packaged together**