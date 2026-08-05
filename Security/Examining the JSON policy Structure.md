# 📜 Examining the JSON Policy Structure

## 🧩 Definition

**IAM Policies** are formatted as **JSON documents** that define what an identity can or cannot access.

IAM policies are used in:

- 👤 **Identity-Based Policies**
- 🗄️ **Resource-Based Policies**

IAM policies contain different elements that define how permissions are granted or denied.

---

## 🏗️ IAM Policy Structure

IAM policies contain several key elements:

- 📌 **Version**
- 📝 **Statement**
- 🆔 **Sid**
- ⚖️ **Effect**
- 👤 **Principal**
- ⚙️ **Action**
- 🗄️ **Resource**
- 🔍 **Condition**

---

## 📌 Version

The **Version** element specifies the **policy language version** being used.
- E.g **"Version":"2012-10-17"** 

---

## 📝 Statement

The **Statement** Defines the main element of the policy.

It contains sub-elements that define the permissions and conditions of the policy.

Common Statement sub-elements include:

- 🆔 **Sid**
- ⚖️ **Effect**
- 👤 **Principal**
- ⚙️ **Action**
- 🗄️ **Resource**
- 🔍 **Condition**

---

## 🆔 Sid

The **Sid (Statement ID)** allows you to set a unique **identifier within the statement**.

Making them more easily identifiable.
- E.g **"Sid":"AllowGetObjectForS3"**

---

## ⚖️ Effect

The **Effect** either **grants** or **restricts** access for the **"Actions"** defined in the Statement. By default all access to your resources are denied.

- ✅ **Allowed**
- 🚫 **Denied**

---

## 👤 Principal

The **Principal** Defines which principal the policy relates to.

The **Principal** is only used for **resource-based policies**.
- For example those policies attached to S3 Buckets
- **"Principal":"AWS":"arn:aws:iam:8423798759:user/Stuart"**
- When using **identity-based polciies** this parameter is not required within the policy as the policy itself is associated with the principal and not a resource.
- This can be replaced with the **NotPrincipal** parameter which specifies the User, Role, or AWS account that is NOT allowed or denied access to the associated resource.

---

## ⚙️ Action

The **Action** the action that will either be allowed or denied, depending on the value entered for the **"Effect"** element.

- **"cloudtrail:CreateTrail"**
- **"cloudtrial:DeleteTrail"**
or

- **"Action":cloudtrail:*"**

We can replace the Action parameter with **NotAction** and this cloud help you optimize your policy by creating a shorter version.
- **"NotAction":"cloudtrial:DeleteTrail"** allows all actions from cloudtrail apart from delete.

Actions are often prefixed with the name of the **AWS service**.

---

## 🗄️ Resource

The **Resource** specifies the actual resource you wish the **"Action"** and **"Effect"** to be applied to using ARNs **(Amazon Resource Names)**.
- E.g **"Resource":"arn:aws:s3:::mybucket"**
- Can also use a **NotResource** to explicitly match all other resources except those specified.

---

## 🔍 Condition

The **Condition** an **optional** element that allow you to control when the permissions will be effective based upon set citeria.

Conditions can be used to control when the permissions defined in the policy apply.

---

## 🆚 Identity-Based vs Resource-Based Policies

IAM policies can be used as both **identity-based** and **resource-based** policies.

### 👤 Identity-Based Policies

Identity-based policies define what an identity can or cannot access.

They are associated with identities such as:

- 👤 Users
- 👥 User Groups
- 🎭 Roles

### 🗄️ Resource-Based Policies

Resource-based policies define access directly on a resource.

They use the **Principal** element to specify the user or entity that the policy applies to.

---

## 📋 IAM Policy Elements

| Element | Purpose |
|---|---|
| 📌 **Version** | Specifies the policy language version |
| 📝 **Statement** | Main element containing the policy permissions |
| 🆔 **Sid** | Optional unique statement identifier |
| ⚖️ **Effect** | Determines whether access is allowed or denied |
| 👤 **Principal** | Specifies the user or entity the policy applies to |
| ⚙️ **Action** | Specifies the actions allowed or denied |
| 🗄️ **Resource** | Identifies the resource using an ARN |
| 🔍 **Condition** | Defines optional criteria for when permissions are effective |

---

## ✨ Features

- 📜 IAM policies are formatted as JSON documents.
- 👤 Define what identities can or cannot access.
- 🗄️ Support resource-based access control.
- ⚖️ Can allow or deny access.
- ⚙️ Define specific AWS actions.
- 🗄️ Identify resources using ARNs.
- 👤 Use Principals in resource-based policies.
- 🔍 Support optional conditions for controlling when permissions are effective.

---

## 🎯 Use Cases

- 🔐 Defining what an identity can access.
- 🚫 Defining what an identity cannot access.
- 🗄️ Controlling access to AWS resources.
- ⚙️ Allowing or denying specific AWS actions.
- 👤 Specifying which users or entities can access resources.
- 🔍 Adding conditions that control when permissions are effective.

---

## ⚖️ Key Benefits

- 🔐 Provides structured access control for AWS resources.
- 📜 Uses a standardized JSON format.
- ⚖️ Supports both allowed and denied access.
- ⚙️ Provides control over specific AWS actions.
- 🗄️ Allows policies to target specific resources using ARNs.
- 🔍 Allows additional conditions to control when permissions are effective.
- 👤 Supports both identity-based and resource-based policies.

---

## 🧠 Analogy: IAM Policy as Security Guard Instructions

Imagine a **JSON policy** as a set of instructions for a **security guard at a building**.

The entire policy is like a **folder** containing one or more **instruction sheets (Statements)**.

Each instruction sheet has specific sections:

### 📌 Version
Like the **date or version of the rules** the guard should follow.

### 📝 Statement
The main **instruction sheet**, which contains several details about what the guard should do.

### 🆔 Sid
A **label or name** for the instruction.

For example:

> **"Front Door Access"**

### ⚖️ Effect
Tells the guard whether to:

- ✅ **Allow** entry.
- 🚫 **Deny** entry.

### 👤 Principal
Defines **who the instruction applies to**.

For example:

> 👥 **Only employees**

### ⚙️ Action
Defines **what the person is allowed or denied to do**.

For example:

> 🚪 **Open the main door**

### 🗄️ Resource
Defines **which part of the building the rule applies to**.

For example:

> 🚪 **Main entrance**

### 🔍 Condition
Defines any **special requirements** that must be met.

For example:

- 🕐 **Only during office hours**
- 🪪 **Must show ID**

Just like a security guard follows these **clear, structured instructions**, AWS uses **JSON policies** to control access to AWS resources.