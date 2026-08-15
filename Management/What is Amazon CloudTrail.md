# 🕵️ What is AWS CloudTrial?

## 🧩 Definition
**AWS CloudTrail** is a service designed to **record and track AWS API requests** made within your AWS account.

API requests can originate from:

- 🛠️ **SDKs**
- 💻 **AWS Command Line Interface (CLI)**
- 🖥️ **AWS Management Console**
- ☁️ **Other AWS services**

---

## 📝 Event Recording

CloudTrail captures API requests as **events**.

These events are recorded in **log files** and stored in **Amazon S3**.

Each event includes metadata such as:

- 👤 **Identity of the caller**
- ⏰ **Timestamp**
- 🌐 **Source IP address**

### 🎯 Key Idea

**API Request → CloudTrail Event → Log File → Amazon S3**

---

## 📊 Event Types

CloudTrail categorizes events into **three types**:

### 1. ⚙️ Management Events
Also Known as **Control Plane Operations**, these track information about **management operations** taken against AWS resources within your account.
Example:
- Amazon RDS CreateDBInstance API
- AWS IAM CreateUser API

Some Captured events are classed as **non-API events**.
Example:
- When an automatic key rotation of a **KMS key** is performed.
- When a user has a **successful** or **unsuccessful** sign-in to the AWS Management Console.

### 2. 📦 Data Events
Also known as **Data Plane Operations**, these show information about resource operations performed on or in a resource.
Example:
- Amazon S3 Object-level API acitvity including:
    - GetObject
    - Delete Object
    - PutObject

- AWS EBS Snapshot Operations, such as:
    - PutSnapshotBlock
    - GetSnapshotBlock
    - ListChangedBlkocks

### 3. 🔍 Insight Events
- Allow you to capture events triggered by unsual activity within your account.
- Stored in a different folder in S3 to the Mangement and Data events and contians information about:
    - Time of the event
    - Error codes
    - Associated APIs
    - Additional statistics

---

## Trails
1. **All Region Trail:**
    - Applies to **all regions** within your AWS account.
    - AWS CloudTrail records events configured for **in each region** that you are operating.
        - Deliver these events via **log files** to your S3 Bucket.
    - Enables you to **capture and record** data across your entire account.

2.  **Signle Region Trail:**
    - Created using the AWS command line interface (CLI).
    - Data captured from a **signle region** only:
        - You can customize which regions you are interested in recording data for.
    - The event log files are delivered to a destination such as:
        - Amazon S3 Bucket acting as a single repository.

3. **AWS Organization Trail:**
    - Captures **all events** from **all accounts** that belong to the AWS organization.
    - Can be configured to capture events from **single region** or **all regions**.
    - Management account **mnust** be used to create the trail, which will be associated and applied to all of your member accounts.


---

## 📜 Log Management

CloudTrail typically creates **new log files every five minutes**.

These logs can also be delivered to **CloudWatch Logs** for monitoring.

### 🔗 CloudWatch Logs Integration

CloudTrail events can be sent to **CloudWatch Logs**, allowing you to:

- 📊 Create **custom metrics**.
- 🚨 Monitor activity.
- 📢 Trigger **SNS notifications** when thresholds are crossed.

### 🎯 Flow

**CloudTrail Events → CloudWatch Logs → Custom Metrics → Threshold Crossed → SNS Notification**

---

## 🌎 Global Service

CloudTrail supports:

- 🌎 **All AWS Regions**
- ☁️ **More than 60 AWS services**

This provides comprehensive coverage for **tracking and auditing API requests**.

---

## 🛡️ Security and Compliance

CloudTrail is an important tool for **security analysis**.

It allows users to:

- 🔍 Monitor **API activity**.
- 📋 Track and audit API requests.
- 🚨 Detect potential **security threats**.

CloudTrail can integrate with services such as:

- 🛡️ **Amazon Macie**
- 👮 **Amazon GuardDuty**

These integrations can help with security analysis and detecting potential threats.

---

## ⚖️ Key Benefits

- 📝 Records and tracks **AWS API requests**.
- 👤 Provides information about the **identity of the caller**.
- ⏰ Records the **timestamp** of API activity.
- 🌐 Records the **source IP address**.
- 📊 Categorizes events into **Management, Data, and Insight Events**.
- 💾 Stores log files in **Amazon S3**.
- 🔗 Integrates with **CloudWatch Logs**.
- 📢 Can trigger **SNS notifications** when thresholds are crossed.
- 🌎 Supports **all AWS Regions**.
- ☁️ Supports **more than 60 AWS services**.
- 🏢 Allows trails to be configured across **AWS Organizations**.
- 🛡️ Supports **security analysis and auditing**.
- 🔍 Can integrate with **Amazon Macie and Amazon GuardDuty**.

---

## 🧠 Analogy: AWS CloudTrail as a Security Camera System

Imagine **AWS CloudTrail as a security camera system for your AWS environment**.

- 📹 Just like security cameras record **every movement and activity** in a building, CloudTrail records **every action and event** that happens in your AWS account.
- 🚪 The person who **opens a door** is like someone making an **API call**.
- ⏰ CloudTrail records **what time** the action occurred.
- 🛠️ It also records what was done, such as **creating or deleting resources**.
- 🔍 If something unexpected happens, you can review the **CloudTrail logs**, similar to reviewing security camera footage.
- 👤 The logs help you determine:
  - Who was involved.
  - ⏰ When the activity occurred.
  - 🛠️ What action was performed.

### 🎯 Key Idea

**CloudTrail = Security cameras for your AWS environment**

It records AWS activity so you can **review what happened, who was involved, and when it happened**, helping keep your AWS environment **secure and well-monitored**.

---

# 🛡️ AWS CloudTrail Security, Visibility, and Auditing

## 🧩 Overview
**AWS CloudTrail** captures extensive data across **AWS Regions and organizations**, providing benefits for:

- 🛡️ **Security**
- 🔍 **Visibility**
- 📋 **Auditing**
- 🏛️ **Governance and regulatory compliance**

---

## 🛡️ Security Tool

CloudTrail can serve as a **security tool** by helping identify **unauthorized events**.

When an unauthorized event is detected:

- 🔍 Security teams can **investigate** the event.
- 🛡️ Teams can use the information to help **prevent future occurrences**.

---

## 🗂️ Centralized Activity Records

CloudTrail can consolidate activity records from **multiple AWS Regions** into a **single S3 bucket**.

This simplifies:

- 📊 **Data analysis**
- 🔍 **Auditing**
- 🗂️ Management of activity records

### 🎯 Key Idea

**Multiple Regions → Single S3 Bucket → Simplified Analysis and Auditing**

---

## 👀 AWS Environment Visibility

CloudTrail enhances visibility into AWS environments.

It can help:

- 🔍 Detect **unusual behavior**.
- ⚠️ Provide **early warnings of potential attacks**.
- 👀 Monitor activity across AWS environments.

---

## 🔎 CloudTrail Insights

**CloudTrail Insights** tracks and identifies **unusual API behavior**.

When unusual API behavior is identified, CloudTrail Insights captures **additional metadata** for analysis.

### 📊 Insights Storage

Insights are:

- 💾 **Stored separately**
- 🖥️ Available for review in the **AWS Management Console**

---

## 📋 Audit Trail

CloudTrail maintains a **recorded audit of actions and configuration changes**.

This information can assist with:

- 🏛️ **Governance**
- 📋 **Regulatory compliance**
- 🔍 Reviewing AWS activity

---

## 📝 Event Log Information

Each CloudTrail event log includes detailed information such as:

- 👤 **Principal**
- 🆔 **Account ID**
- 👤 **Username**
- ⏰ **Event Time**
- 🌐 **Source**
- 📝 **Event Name**
- 🌎 **Region**
- 🌐 **Source IP Address**

This information provides detailed context about each recorded event.

---

## ⚖️ Key Benefits

- 🛡️ Helps identify **unauthorized events**.
- 🔍 Allows security teams to **investigate activity**.
- 🛡️ Helps prevent future unauthorized occurrences.
- 🗂️ Consolidates activity records from multiple Regions into a **single S3 bucket**.
- 📊 Simplifies **data analysis and auditing**.
- 👀 Enhances visibility into AWS environments.
- ⚠️ Helps detect **unusual behavior**.
- 🚨 Provides early warnings of **potential attacks**.
- 🔎 **CloudTrail Insights** identifies unusual API behavior.
- 💾 Stores Insights separately for review.
- 📋 Maintains an audit of **actions and configuration changes**.
- 🏛️ Supports **governance and regulatory compliance**.
- 📝 Provides detailed event information for analysis and auditing.