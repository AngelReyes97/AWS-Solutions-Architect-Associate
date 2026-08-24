# 🌐 VPC Flow Logs Overview

## 🧩 Definition

**VPC Flow Logs** capture **IP traffic information between network interfaces** within a **Virtual Private Cloud (VPC)**.

They are useful for:

- 🔧 Troubleshooting network communication issues
- 🔐 Enhancing security
- 🚨 Identifying unauthorized traffic

---

## 📊 Data Storage and Configuration

Unlike:

- 🪣 **Amazon S3 access logs**
- 🌐 **CloudFront access logs**

VPC Flow Logs data is sent to:

- 📊 **CloudWatch Logs**

### ⚙️ Flow Log Modification

Once a VPC Flow Log is created:

- 🚫 It cannot be modified.
- 🗑️ It must be deleted and recreated to make changes.

---

## 🎯 Flow Log Resources

VPC Flow Logs can be configured for:

- 🔌 Individual **network interfaces**
- 📂 **Subnets**
- 🌐 Entire **VPCs**

The log data is sent to:

- 📊 **CloudWatch log groups**

Each network interface uses:

- 📋 A different **log stream**

---

## 🚫 Limitations

VPC Flow Logs have several limitations.

### 🔗 Peered VPCs

Flow logs are limited to:

- 🔗 **Peered VPCs within the same account**

### 🖥️ EC2-Classic

VPC Flow Logs do not capture traffic from:

- 🚫 **EC2-Classic environments**

### 🚫 Traffic Not Logged

Certain traffic is not captured, including:

- 📡 **DHCP traffic**
- 🌐 **Amazon DNS Server traffic**
- 🖥️ Traffic to specific IP addresses, such as:
  - Instance metadata
  - Amazon Time Sync Service

---

## 📄 Log Entry Details

Each VPC Flow Log entry includes information such as:

- 🔢 **Version**
- 🆔 **Account ID**
- 🔌 **Interface ID**
- 📤 **Source IP**
- 📥 **Destination IP**
- 🔢 **Source and destination ports**
- 🌐 **Protocol**
- 📦 **Packet count**
- 📊 **Byte count**
- ⏱️ **Timestamps**
- ✅ **Action**
  - Accepted
  - Rejected
- 📋 **Log status**
  - `OK`
  - `NoData`
  - `SkipData`

---

## 🔍 Filter Types

When configuring VPC Flow Logs, you can define the traffic to capture using:

- 📊 **All**
- ✅ **Accept**
- ❌ **Reject**

This allows users to focus on the traffic relevant to their monitoring and security needs.

---

## 🛠️ Use Cases

VPC Flow Logs are useful for:

### 🔧 Network Troubleshooting
- Monitor network traffic.
- Investigate network communication issues.

### 🔐 Security
- Identify unauthorized traffic.
- Review whether traffic was accepted or rejected.

### ⚖️ Security Compliance
- Review actions taken on network traffic.
- Monitor accepted and rejected traffic.

---

## 🔐 Permissions

Specific **IAM permissions** are required to:

- ➕ Create flow logs
- 🗑️ Delete flow logs
- 🔍 Describe flow logs
- 📊 Access log data

An **IAM role with appropriate permissions** is required for delivering log data to CloudWatch.

---

## ⚙️ Implementation

Setting up VPC Flow Logs involves:

1. 🎯 **Select the resource**
   - Network interface
   - Subnet
   - VPC

2. 🔍 **Define the filter type**
   - All
   - Accept
   - Reject

3. 🔐 **Assign a role**
   - Provide the required permissions.

4. 📊 **Specify the destination**
   - CloudWatch log group

### 🎯 Basic Flow

**Network Interface / Subnet / VPC → VPC Flow Logs → Filter Traffic → IAM Role → CloudWatch Log Group**

---

## ⚖️ Key Benefits

- 🌐 Captures IP traffic information between network interfaces.
- 🔧 Helps troubleshoot network communication issues.
- 🔐 Helps identify unauthorized traffic.
- 📊 Sends flow log data to CloudWatch Logs.
- 🎯 Can be configured for network interfaces, subnets, or entire VPCs.
- 📋 Provides detailed information about network traffic.
- 🔍 Supports All, Accept, and Reject filters.
- ⚖️ Helps review accepted and rejected traffic for security compliance.
- 🔐 Uses IAM permissions and roles to control flow log creation and delivery.

### 🧠 Key Idea

**VPC Flow Logs = Capture IP traffic information for network monitoring and security**

**Destination = CloudWatch Logs**

**Resources = Network Interface, Subnet, or VPC**

**Filters = All, Accept, or Reject**

**Action = Accepted or Rejected**

**Log Status = OK, NoData, or SkipData**