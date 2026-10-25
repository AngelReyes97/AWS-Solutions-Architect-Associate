# 🔐 What is an AWS KMS Custom Key Store?

## 🧩 Definition

A **Key Store** is a secure storage location for cryptographic keys used to encrypt and decrypt data in AWS.

AWS Key Management Service (KMS) provides default key stores managed by AWS and stored on AWS-managed Hardware Security Modules (HSMs). Customers do not have direct control over these HSMs.

For organizations that require stricter compliance and greater control over their key material, AWS allows the creation of **Custom Key Stores** backed by AWS CloudHSM clusters.

---

## 🧠 Overview

AWS KMS and AWS CloudHSM can work together to provide AWS service integration while allowing customers to maintain control over their cryptographic key material.

### 🔑 Key Store Types

- ☁️ **Default KMS Key Store:** Uses AWS-managed HSMs, which customers do not directly control.
- 🔐 **Custom Key Store:** Managed through KMS but uses a customer's CloudHSM cluster to store and protect key material.

---

## 🔐 1. Custom Key Store Features

A **Custom Key Store** allows customers to use KMS while storing their key material within their own CloudHSM cluster.

### 🔑 Key Characteristics

- 🏗️ **CloudHSM Integration:** KMS manages the custom key store while CloudHSM protects the key material.
- 🔒 **Key Material Control:** Provides greater control over key material, including key creation, rotation, access management, and policy configuration.
- 🔑 **CMK Support:** Customer Master Keys (CMKs) created in a custom key store are 256-bit, non-exportable AES symmetric keys.
- 🛡️ **Key Protection:** Key material does not leave the HSM unencrypted.
- ⚙️ **Cryptographic Operations:** Operations using these CMKs occur within the CloudHSM cluster.

---

## ☁️ 2. Integration with AWS Services

AWS KMS integrates with various AWS services to enable server-side encryption with minimal configuration.

### 🔗 Benefits of Integration

- ☁️ **AWS Service Integration:** Uses KMS integration capabilities across supported AWS services.
- 🔐 **Custom Key Store Integration:** Allows organizations to use KMS while keeping their key material within their CloudHSM cluster.
- ⚙️ **Simplified Encryption:** Combines KMS's ease of integration with CloudHSM's hardware-based key protection.

---

## 🏗️ 3. Requirements for Custom Key Store Setup

Several requirements must be met before a custom key store can be configured.

### 📋 Setup Requirements

1. 🌎 **Same AWS Region**
   - The CloudHSM cluster and KMS must be in the same AWS Region because KMS is a regional service.

2. 🔗 **One Custom Key Store per HSM Cluster**
   - Each HSM cluster can be associated with only one custom key store.

3. 🏗️ **At Least Two Activated HSMs**
   - The cluster must have at least two activated HSMs in different Availability Zones for redundancy.

4. 📜 **Trust Anchor Certificate**
   - A trust anchor certificate generated during cluster initialization must be uploaded to KMS.

5. 👤 **Dedicated Crypto User**
   - Create a dedicated Crypto User (CU) named `kmsuser` in the HSM cluster.
   - This user must be created without two-factor authentication.
   - KMS uses this user to perform operations and rotate its password.

---

## ⚖️ 4. Benefits of Using CloudHSM with KMS

Combining KMS with CloudHSM provides AWS service integration alongside dedicated hardware for protecting cryptographic key material.

### 🛡️ Key Benefits

- 🔗 **AWS Integration:** Uses KMS integration with supported AWS services.
- 🔐 **Dedicated Hardware:** Leverages CloudHSM's single-tenant, tamper-resistant hardware.
- 🗝️ **Greater Key Control:** Allows customers to maintain control over their cryptographic key material.
- 📜 **Compliance Support:** Helps meet stringent compliance requirements.
- ⚙️ **Simplified Management:** Combines KMS management capabilities with CloudHSM key protection.

---

## 🔍 5. KMS vs. CloudHSM

| Feature | AWS KMS | AWS CloudHSM |
|---|---|---|
| **Primary Purpose** | Key management and AWS service integration | Dedicated hardware for cryptographic operations and key protection |
| **Key Control** | Default key stores use AWS-managed HSMs | Customers retain control over their HSMs |
| **Custom Key Store** | Manages the custom key store | Stores and protects key material in the HSM cluster |
| **AWS Service Integration** | Broad integration with AWS services | Can integrate with KMS through custom key stores |
| **Primary Benefit** | Ease of use and integration | Greater control over key material and hardware |

---

## ⚠️ 6. Key Considerations

- 🔗 **Complementary Services:** KMS provides broad AWS service integration, while CloudHSM provides greater control over the hardware protecting key material.
- 🔐 **Custom Key Stores:** Allow organizations to use KMS while keeping their key material within their CloudHSM cluster.
- 🌎 **Regional Requirement:** KMS and the CloudHSM cluster must be in the same AWS Region.
- 🏗️ **Redundancy:** At least two activated HSMs in different Availability Zones are required.
- 👤 **Dedicated User:** The HSM cluster must contain the `kmsuser` Crypto User configured as required.

---

## 🎯 Key Takeaway

**KMS Custom Key Store = AWS KMS Integration + Customer-Controlled CloudHSM Key Material**

Remember these key points:

- ☁️ **Default Key Store:** Uses AWS-managed HSMs.
- 🔐 **Custom Key Store:** Uses a customer's CloudHSM cluster to protect key material.
- 🔑 **CMKs:** Are 256-bit, non-exportable AES symmetric keys.
- 🏗️ **HSM Requirements:** At least two activated HSMs in different Availability Zones.
- 🌎 **Regional Requirement:** KMS and CloudHSM must be in the same AWS Region.
- 📜 **Trust Anchor:** The certificate generated during cluster initialization must be uploaded to KMS.
- 👤 **`kmsuser`:** A dedicated Crypto User used by KMS for operations and password rotation.
- ⚖️ **Main Advantage:** Combines KMS's AWS service integration with CloudHSM's dedicated hardware and greater control over key material.