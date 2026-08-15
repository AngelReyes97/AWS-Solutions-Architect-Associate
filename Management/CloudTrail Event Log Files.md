# 🛤️ AWS CloudTrail Trails Event Log Files

## 🧩 Definition

**CloudTrail Trails** are used to **capture, track, and retain events** across AWS accounts.

Without a trail, events can only be viewed in the **CloudTrail dashboard for up to 90 days**.

---

## 📜 Event Storage

Events captured by trails are sent to log files stored in:

- 🪣 **Amazon S3**
- 🗄️ **CloudTrail Lake**

These logs can be stored for **up to 7 years**. These logs are written in JSON format and contain detailed information about each event.

The log files are stored in **JSON format** and contain detailed information about each event.

### 🎯 Key Idea

**AWS Event → CloudTrail Trail → JSON Log File → S3 or CloudTrail Lake**

---

## 📝 CloudTrail Log File Elements

CloudTrail log files contain detailed information about each event.

Key elements include:

- `eventVersion`
- `userIdentity`
- `eventTime`
- `eventSource`
- `eventName`
- `awsRegion`
- `sourceIPAddress`
- `userAgent`
- `requestParameters`
- `responseElements`
- `additionalEventData`
- `eventID`
- `readOnly`
- `eventType`
- `managementEvent`
- `recipientAccountId`
- `eventCategory`
- `tlsDetails`

These elements provide information needed to **identify and understand the event**.

---

## ⏱️ Log File Creation

CloudTrail log files are created approximately **every five minutes**.

The logs are stored in a **structured format** within an S3 bucket.

The S3 structure includes folders for:

- 🆔 **AWS Account ID**
- ☁️ **Service**
- 🌎 **Region**
- 📅 **Date**

---

## 🗂️ Multi-Account Log Aggregation

CloudTrail allows logs from **multiple AWS accounts** to be aggregated into a **single S3 bucket**.

This simplifies:

- 📋 **Log management**
- 🔍 **Log tracking**
- 🗂️ **Centralized storage**

### ⚙️ Configuration Process

To aggregate logs from multiple accounts:

1. ☁️ **Enable CloudTrail**.
2. 🪣 **Update the S3 bucket policy**.
3. ⚙️ Configure trails in the other AWS accounts to use the **existing S3 bucket**.

### 🎯 Basic Flow

**Multiple AWS Accounts → CloudTrail Trails → Single S3 Bucket**

---

## 📊 Log Retention

| Without Trail | With Trail |
|---|---|
| 👀 Events viewable in CloudTrail dashboard | 📝 Events captured in log files |
| ⏱️ Up to **90 days** | 💾 Stored up to **7 years** |
| 🔍 Dashboard viewing | 🪣 S3 or 🗄️ CloudTrail Lake storage |

---

## ⚖️ Key Benefits

- 📝 Captures, tracks, and retains **CloudTrail events**.
- 💾 Stores logs in **Amazon S3 or CloudTrail Lake**.
- ⏱️ Allows logs to be stored for **up to 7 years**.
- 📄 Stores logs in **JSON format**.
- 🔍 Provides detailed information about each event.
- ⏰ Creates log files approximately **every five minutes**.
- 🗂️ Uses a structured S3 folder format.
- 🌎 Supports **multiple AWS accounts**.
- 🪣 Allows logs from multiple accounts to be aggregated into a **single S3 bucket**.
- 📋 Simplifies centralized **log management**.

### 🧠 Key Idea

**CloudTrail Trail = Capture AWS events → Store detailed JSON logs → Retain them beyond the 90-day dashboard history → Centrally manage logs across accounts.**