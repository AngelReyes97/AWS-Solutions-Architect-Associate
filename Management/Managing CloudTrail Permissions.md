# 🔐 AWS CloudTrail Permissions

## 🧩 Overview

**AWS CloudTrail** requires specific **permissions** to set up and manage trails within an AWS account.

These permissions are managed through **AWS Identity and Access Management (IAM) policies**.

---

## 📜 AWS Managed Policies for CloudTrail

There are **three AWS managed policies** related to CloudTrail:

### 1. 🔗 CloudTrailServiceRolePolicy

**CloudTrailServiceRolePolicy** is a permission policy for a **CloudTrail ServiceLinkedRole**.

It allows CloudTrail to perform specific operations **on behalf of the user**.

Key points:

- 🔗 Linked to a **service-linked role**.
- ⚙️ Allows the CloudTrail service to perform specific operations.
- 🚫 Cannot be attached directly to:
  - 👤 Users
  - 👥 Groups
  - 🎭 Roles

---

### 2. 🛠️ AWSCloudTrail_FullAccess

**AWSCloudTrail_FullAccess** provides comprehensive permissions to **configure AWS CloudTrail**.

It also provides access to related services such as:

- 🪣 **Amazon S3**
- 📢 **Amazon SNS**
- 📊 **CloudWatch Logs**
- 🔐 **AWS Key Management Service (KMS)**

These permissions are necessary for tasks such as:

- 🪣 Specifying **storage locations**.
- 🔐 Configuring **encryption**.
- 📢 Configuring **notification parameters**.
- 📊 Monitoring **trail logs**.

---

### 3. 👀 AWSCloudTrail_ReadOnlyAccess

**AWSCloudTrail_ReadOnlyAccess** allows users to **view CloudTrail information** without modifying trails.

Users with this policy can:

- 👀 View **trail information**.
- 📋 List **trails** within an account.
- 🔍 Look up **management events** from the past **90 days**.
- 🔎 Look up **Insight events** from the past **90 days**.

It does **not** allow users to:

- 🚫 Create trails.
- 🚫 Modify trails.

---

## 🪣 Permissions When Creating a Trail

When creating a trail, CloudTrail may be asked to create resources such as:

- 🪣 **S3 bucket**
- 📢 **SNS topic**

If CloudTrail creates these resources, the **necessary permissions are automatically applied**.

However, if you use **existing resources**, the required permissions must be **manually configured**.

### 🎯 Key Difference

| Resource | Permissions |
|---|---|
| 🆕 CloudTrail creates the resource | Permissions are automatically applied |
| ♻️ Existing resource is used | Permissions must be manually configured |

---

## 🛡️ Principle of Least Privilege

It is recommended to follow the **principle of least privilege** when assigning CloudTrail permissions.

This means users should receive **only the access necessary for their roles**.

### 🎯 Goal

**Required Access Only → Reduced Unnecessary Permissions → Better Security**

---

## ⚖️ Policy Summary

| Policy | Main Purpose |
|---|---|
| 🔗 **CloudTrailServiceRolePolicy** | Allows a CloudTrail service-linked role to perform specific operations |
| 🛠️ **AWSCloudTrail_FullAccess** | Provides comprehensive permissions to configure CloudTrail and related services |
| 👀 **AWSCloudTrail_ReadOnlyAccess** | Allows viewing and looking up CloudTrail information without creating or modifying trails |

### 🧠 Key Idea

**CloudTrail permissions are controlled through IAM policies, with different policies providing service-linked permissions, full configuration access, or read-only access.**