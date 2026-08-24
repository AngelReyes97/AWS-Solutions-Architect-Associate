# 📊 CloudWatch Logging Agent Overview

## 🧩 Definition

The **CloudWatch Logging Agent** is a component of **Amazon CloudWatch** that helps collect and monitor **log files and additional metric data**.

It can centralize log collection from:

- ☁️ **EC2 instances**
- 🏢 **On-premises services**

---

## 📥 Log Collection

The CloudWatch Logging Agent collects logs and additional metric data from different sources.

It can be installed on:

- 🐧 **Linux**
- 🪟 **Windows**

The agent requires **configuration** before it can begin collecting data.

---

## 🔗 AWS Systems Manager Integration

The CloudWatch Logging Agent works with **AWS Systems Manager (SSM)** to manage:

- 📄 Configuration files
- 🔐 Permissions

This helps ensure:

- 🔒 Secure data collection
- ⚡ Efficient data collection

---

## 📊 CloudWatch Logs

Collected data is stored in **CloudWatch Logs**.

CloudWatch Logs allows users to:

- 👀 Monitor logs in real time
- 🔍 Analyze log data
- 📏 Create metric filters
- 🚨 Set alarms based on log data

---

## 🗄️ Log Retention

CloudWatch Logs can store logs **indefinitely** by default.

Retention policies can be adjusted to:

- 📅 **1 day**
- 📅 Up to **10 years**

This allows retention to be configured based on specific needs.

---

## 🔎 CloudWatch Logs Insights

**CloudWatch Logs Insights** provides querying capabilities for **operational analysis**.

It allows users to analyze collected log data and turn it into:

- 📊 Actionable metrics
- 🚨 Data that can trigger alarms

---

## 🎯 Basic Flow

**EC2 / On-Premises Services → CloudWatch Logging Agent → CloudWatch Logs → Monitor & Analyze → Metric Filters / Alarms**

---

## ⚖️ Key Benefits

- 📥 Centralizes log collection from EC2 instances and on-premises services.
- 📊 Collects logs and additional metric data.
- 🐧 Supports Linux.
- 🪟 Supports Windows.
- ⚙️ Requires configuration before collecting data.
- 🔗 Works with AWS Systems Manager to manage configuration files and permissions.
- 🔒 Supports secure and efficient data collection.
- 👀 Allows real-time monitoring and analysis through CloudWatch Logs.
- 📏 Allows metric filters to be created from log data.
- 🚨 Allows alarms to be configured based on log data.
- 🗄️ Supports log retention from one day to ten years.
- 🔎 CloudWatch Logs Insights provides querying capabilities for operational analysis.
- 📊 Log data can be turned into actionable metrics that trigger alarms.

### 🧠 Key Idea

**CloudWatch Logging Agent = Collects logs and additional metric data**

**CloudWatch Logs = Stores and monitors collected log data**

**CloudWatch Logs Insights = Queries and analyzes log data**

**Metric Filters = Extract information from logs for monitoring**

**Alarms = Trigger based on metric data from logs**

---

# 🌐 CloudFront Access Logs

## 🧩 Definition

**Amazon CloudFront** is a **content delivery network (CDN)** by AWS that accelerates the distribution of:

- 📄 **Static content**
- 🔄 **Dynamic content**

CloudFront uses a **global network of edge locations** and routes requests to the **nearest edge location** to optimize performance.

---

## 📝 CloudFront Access Logs

**CloudFront access logs** record requests made by users to access content distributed through CloudFront.

The logs are stored in:

- 🪣 **Amazon S3**

Amazon S3 provides durability and persistence for the logs.

### 💰 Logging Costs

- ✅ Enabling CloudFront logging has **no direct charges**.
- 💰 Storage costs apply for logs stored in Amazon S3.

---

## 📍 Logging Process

CloudFront generates logs at the **edge location** on a **per-distribution basis**.

This means:

- 📂 Logs for different distributions are kept separate.
- 🌎 Multiple edge locations can be involved.
- 📄 A single log file is created for a distribution, even when multiple edge locations are involved.

---

## 📊 Log File Generation

The number of log files generated depends on:

- 📈 **Volume of requests**

CloudFront retains logs until they are ready to be delivered to Amazon S3.

Delivery can take:

- ⏱️ **1 to 24 hours**

---

## 🏷️ Log File Naming

CloudFront log files follow a standard naming convention based on:

- 🪣 **Bucket name**
- 📂 **Prefix**
- 🆔 **Distribution ID**

---

## 🔐 Enabling CloudFront Logging

To enable logging, users need specific permissions for the **Amazon S3 bucket** designated for logging.

Required permissions include:

- 🔐 **Full control on the ACL** for the bucket
- 📋 **S3 GetBucketAcl**
- ✏️ **S3 PutBucketAcl**

---

## 📄 Log Content

### 🌐 Web Distribution Logs

Web distribution logs contain **26 fields**.

These include information such as:

- 📅 Request date and time
- 📍 Edge location
- 🌐 Requester IP
- 🔄 HTTP method
- 🔢 Status codes
- 🔐 Encryption details

### 📺 RTMP Distribution Logs

RTMP distribution logs contain **13 fields**.

They capture similar information relevant to:

- 📺 Streaming events

---

## 🍪 Cookie Logging

CloudFront can log **cookie information** when cookie logging is enabled.

Cookie logging is useful when:

- 🌐 The origin is **not an S3 bucket**

Amazon S3 does not process cookie data.

---

## 🎯 Basic Flow

**User Request → CloudFront Edge Location → Content Distribution → Access Log Generated → Amazon S3**

---

## ⚖️ Key Benefits

- 🌐 Uses a global network of edge locations.
- ⚡ Accelerates the distribution of static and dynamic content.
- 📍 Routes requests to the nearest edge location.
- 📝 Records user requests through CloudFront access logs.
- 🪣 Stores access logs in Amazon S3.
- 📂 Keeps logs for different distributions separate.
- 📊 Generates log files based on request volume.
- ⏱️ Delivers logs to S3 within **1 to 24 hours**.
- 🏷️ Uses a standard log file naming convention.
- 🔐 Requires specific S3 permissions to enable logging.
- 📄 Web distribution logs contain **26 fields**.
- 📺 RTMP distribution logs contain **13 fields**.
- 🍪 Supports cookie logging when enabled.

### 🧠 Key Idea

**CloudFront = CDN that distributes content through a global network of edge locations**

**Edge Location = Location where CloudFront handles requests**

**Access Logs = Records of requests made through CloudFront**

**Amazon S3 = Stores CloudFront access logs**

**Cookie Logging = Records cookie information when enabled**