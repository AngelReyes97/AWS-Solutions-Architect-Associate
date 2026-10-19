# 🔐 KMS Key Policies Overview

## 🧩 Definition

**KMS Key Policies** are resource-based policies attached to individual AWS KMS keys. They control who can access and manage each key, including administration, cryptographic operations, and temporary access through grants.

Each KMS key has **one key policy**, written in JSON format.

### 📝 Key Policy Elements

Key policies include elements such as:

- 🎯 **Resource:** Specifies the resource the policy applies to.
- ⚙️ **Action:** Defines the permitted operations.
- ✅ **Effect:** Specifies whether access is allowed or denied.
- 👤 **Principal:** Identifies who can access the key.
- 🔎 **Condition:** Defines conditions that must be met for the policy to apply.

---

## 🔑 1. IAM Policies and Key Policies

**IAM policies alone cannot grant access to KMS keys unless the key policy explicitly allows IAM policies to grant that access.**

Key points:

- 🔐 **Default Key Policy Statement:** Grants the root account permission to manage access through IAM policies.
- 👤 **IAM-Based Permissions:** IAM policies can grant access when permitted by the KMS key policy.
- ⚠️ **Removing the Default Statement:** Disables IAM-based permission management through that default authorization mechanism.

---

## 🛡️ 2. Key Administrators

**Key Administrators** are IAM users or roles authorized to manage a KMS key.

### 🔧 Responsibilities

Key administrators can:

- ⚙️ Update key settings.
- 🗑️ Delete or schedule deletion of keys.
- 🔓 Enable or disable keys.
- 📝 Modify the key policy.

### ⚠️ Important Consideration

- Key administrators **cannot perform cryptographic operations** merely because they have administrative permissions.
- They can modify the key policy to grant themselves permission to use the key.

---

## 🔐 3. Key Users

**Key Users** are principals authorized by the key policy to perform cryptographic operations using a KMS key.

### 🔑 Common Operations

Key users can perform operations such as:

- 🔒 Encryption.
- 🔓 Decryption.
- 🔄 Re-encryption.
- 🗝️ Data key generation.

### 👥 Administrator and User Roles

- The same IAM user or role can be both a **Key Administrator** and a **Key User**.
- Administrative permissions and cryptographic permissions are separate and can be assigned as needed.

---

## 🎟️ 4. Grants for Temporary Access

**KMS Grants** delegate specific permissions to another principal without requiring changes to the KMS key policy.

### 🔑 Key Characteristics

- ⏳ **Temporary Delegation:** Grants provide specific permissions to another principal.
- ⚙️ **Programmatic Creation:** Grants are created using AWS KMS APIs.
- 🔐 **Key-Specific:** Each grant is tied to a single KMS key.
- ☁️ **AWS Service Integration:** AWS services, such as Amazon EBS, can use grants to perform encryption operations on behalf of users.

---

## ⚠️ 5. Grant Considerations

### ✅ Allow Operations Only

- Grants can authorize **Allow** operations.
- Grants cannot be used to create **Deny** permissions.

### ⚡ Grant Tokens

A **Grant Token** can provide immediate access to a newly created grant while waiting for eventual consistency.

### 🆔 GrantToken and GrantID

When a grant is created, AWS KMS returns:

- 🎟️ **GrantToken:** Can be used to make the grant's permissions available immediately while waiting for eventual consistency.
- 🆔 **GrantID:** Identifies the grant.

These allow the grantee or application to work with the grant programmatically.

---

## ⚖️ Key Benefits

- 🔐 Controls access to individual KMS keys.
- 👤 Separates key administration from cryptographic usage.
- 📝 Supports fine-grained permissions through JSON key policies.
- 🔗 Allows IAM policies to manage access when authorized by the key policy.
- 🎟️ Enables specific permissions to be delegated through grants without modifying the key policy.
- ☁️ Supports AWS service integrations that require access to KMS keys.

---

## 🎯 Key Takeaway

**KMS Key Policies = The Primary Resource-Based Policies That Control Access to KMS Keys**

Remember these key points:

- 📝 **Key Policy:** Every KMS key has one JSON key policy.
- 🔑 **IAM Policies:** Cannot independently grant KMS key access unless the key policy permits it.
- 🛡️ **Key Administrators:** Manage the key but do not automatically have permission to perform cryptographic operations.
- 🔐 **Key Users:** Perform authorized cryptographic operations.
- 🎟️ **Grants:** Delegate specific permissions without modifying the key policy.
- ⚡ **Grant Tokens:** Help provide immediate access while waiting for eventual consistency.
- ⚠️ **Allow vs. Deny:** Grants authorize Allow operations, not Deny operations.