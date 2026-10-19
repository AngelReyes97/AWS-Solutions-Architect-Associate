# 🔐 What is AWS Key Management Service (KMS)?

## 🧩 Definition

**AWS Key Management Service (KMS)** is a managed service designed to **securely store and generate encryption keys**.

It integrates with various AWS services to enable **encryption for data protection**.

---

## 🔑 Key Use Cases

AWS KMS supports encryption for various AWS services, including:

- 🪣 **Amazon S3:** Supports Server-Side Encryption using KMS, also known as **SSE-KMS**.
- 🗄️ **Amazon RDS:** Supports encryption for databases.
- ☁️ **Other AWS Services:** Commonly used by AWS services that offer encryption capabilities.

### 🎯 Key Idea

**AWS KMS → Encryption Key Management → Data Protection Across AWS Services**

---

## 🛡️ Security and Responsibility

AWS KMS helps customers securely manage their encryption keys.

Key considerations include:

- 🔒 AWS administrators and employees do not have access to customer keys stored in KMS.
- 👤 Customers are responsible for managing their encryption keys.
- 🔑 Customers control how their encryption keys are used.

---

## 🧱 Core Components of KMS

### 1. 🔐 AWS KMS Keys

**Symmetric KMS keys** use the same key for both encryption and decryption.

**Key Characteristics:**
- ⭐ The default key type created in KMS.
- 🔢 Uses **256-bit AES-GCM encryption keys**.
- 🔑 Uses the same key for encryption and decryption.
- 🛡️ Keys never leave the KMS service and are stored securely in **Hardware Security Modules (HSMs)**.
- ☁️ Used by AWS services for server-side encryption.

**Examples:**
- 🪣 Amazon S3 SSE-KMS.
- 🗄️ Amazon RDS encryption.

**### 🎯 Key Idea**

**One Key → Encryption + Decryption**

### 2. 🔐 Asymmetric KMS Keys

**Data Key Pairs** are asymmetric cryptographic keys consisting of two mathematically linked keys:

- 🌎 **Public Key:** Used for encryption.
- 🔒 **Private Key:** Used for decryption.

They are primarily designed for use **outside of AWS Key Management Service (KMS)**, including client-side cryptography, digital signing, and verification.

---

## 🔑 1. Key Types Supported by KMS

AWS KMS supports several types of asymmetric data key pairs.

### 1. 🔐 RSA Key Pairs

Supported key types:

- `RSA_2048`
- `RSA_3072`
- `RSA_4096`

**Use Case:**
- 📜 Commonly used for certificates.

### 2. 🔏 Elliptic Curve Key Pairs

Supported key types:

- `ECC_NIST_P256`
- `ECC_NIST_P384`
- `ECC_NIST_P521`
- `ECC_SECG_P256K1`

**Use Cases:**
- ✍️ `ECC_NIST_P256`, `ECC_NIST_P384`, and `ECC_NIST_P521` are used for digital signatures.
- ₿ `ECC_SECG_P256K1` is used in cryptocurrencies.

### 3. 🌏 SM Key Pairs

- 🔑 **SM2:** A key pair type specific to China Regions.

---

## 🛡️ 2. Key Management

Data Key Pairs have the following key management characteristics:

- 🔒 **Private Key:** Securely stored within KMS and encrypted using a symmetric KMS key.
- 🌎 **Public Key:** Generated alongside the private key and used for encryption.
- 📝 **Plaintext Private Key:** During creation, a plaintext private key and its encrypted version are generated.
- 🔐 **Optional Plaintext Key:** Specific KMS operations allow the plaintext private key to be omitted.

---

## 🔄 3. Encryption and Decryption Process

### 🔒 Encryption

1. 📝 Start with the original plaintext data.
2. 🌎 Use the public key with an encryption algorithm.
3. 🔐 The algorithm converts the plaintext into ciphertext.

**Flow:**

**Plaintext → Public Key + Encryption Algorithm → Ciphertext**

### 🔓 Decryption

1. 💾 Retrieve the encrypted private key.
2. 🔑 Use the original KMS key to decrypt the encrypted private key.
3. 🔓 Retrieve the plaintext private key.
4. 🔐 Use the plaintext private key to decrypt the ciphertext.
5. 📝 Recover the original plaintext.
6. 🧹 Remove the plaintext private key from memory after use.

**Flow:**

**Encrypted Private Key → KMS Key → Plaintext Private Key**

**Ciphertext → Private Key + Decryption Algorithm → Original Plaintext**

---

## 🧱 4. Key Material

**Key material** refers to the string of bits used in cryptographic algorithms.

For asymmetric data key pairs:

- 🌎 **Public Key Material:** Used for encryption.
- 🔒 **Private Key Material:** Must remain protected for decryption.

---

## 🎯 Key Takeaway

**Data Key Pairs = Public and Private Keys for Cryptographic Operations Outside KMS**

Remember these key points:

- 🌎 **Public Key:** Used for encryption.
- 🔒 **Private Key:** Used for decryption and must remain protected.
- 🔐 **RSA Key Pairs:** Commonly used for certificates.
- ✍️ **Elliptic Curve Key Pairs:** Used for digital signatures and other specific applications.
- 🌏 **SM2 Key Pairs:** Specific to China Regions.
- 🛡️ **Key Security:** The private key is stored securely within KMS and encrypted using a symmetric KMS key.
- 💻 **Primary Use:** Client-side cryptography, digital signing, and verification outside KMS.

---

### 2. 👤 Customer Managed Keys

**Customer Managed Keys (CMKs)** are encryption keys created and managed by customers within **AWS Key Management Service (KMS)**.

They provide the **highest level of control and flexibility** compared to other key types.

**Key Features:**

- 🔐 **Control:** Customers have full administrative control over these keys, including permissions, policies, and management.
- 🔑 **Permissions:** Key policies, IAM policies, and grants can be configured to restrict access to authorized users or services.

**Administrative Functions:**

Customers can:
- ✅ Enable or disable keys.
- 🔄 Manage key rotation to enhance security.
- 🏷️ Add tags for better organization.
- 🔗 Create aliases for easier identification.
- 🗑️ Schedule and manage key deletion.

**Usage:**

- ☁️ CMKs can be used with various AWS services to encrypt data.
- 🔐 Customers can specify CMKs when configuring services for encryption, providing more control over data security.

**Cost:**

- 💰 CMKs are charged per version, meaning costs increase with the creation of new keys or new versions of existing keys.

**Asymmetric Keys:**

- 🔐 Customers can create asymmetric CMKs for encryption and signing operations.
- 🌎 These are especially useful when encryption is required outside AWS or by users who cannot directly call KMS.

**Data Encryption Keys (DEKs):**

- 🔑 CMKs can generate **Data Encryption Keys (DEKs)**.
- 📦 DEKs are used outside KMS for encrypting and decrypting data.

**Comparison with Other Key Types:**

- ☁️ **AWS Managed Keys:** Automatically created and managed by AWS for specific services. CMKs provide more granular control.
- 🌐 **AWS Owned Keys:** Abstracted and not visible to customers. CMKs are fully accessible and manageable by customers.

### 🎯 Key Idea

**Customer Managed Keys = Greater Control, Flexibility, and Customization**

Customers control key permissions, policies, rotation, aliases, tags, and deletion settings while choosing how their keys are used to protect data.

---

### 3. ☁️ AWS Managed Keys

**AWS Managed Keys** are encryption keys automatically created and managed by AWS services that integrate with **AWS Key Management Service (KMS)**.

These keys are designed to protect data and perform **encryption and decryption operations**.

---

## 🔑 Key Characteristics

- 🔐 **Symmetric Keys:** AWS Managed Keys use the same key for both encryption and decryption.
- ☁️ **Service-Specific:** They are explicitly created by specific AWS services and are only used by those services.
- 🤖 **Automatic Management:** AWS automatically manages these keys, so customers do not have administrative responsibilities such as key rotation or deletion.

---

## 🔍 Key Identification

- 🖥️ AWS Managed Keys can be viewed in the **AWS KMS console**.
- 🏷️ They follow the naming convention `aws/servicename`.

**Example:**
- 🗄️ `aws/rds` — Amazon RDS.

---

## ⚙️ Usage

- ☁️ When configuring encryption options in AWS services, users can choose between **AWS Managed Keys** and **Customer Managed Keys**.
- 🤖 AWS Managed Keys are convenient for users who prefer AWS to handle encryption key management and maintenance.
- 🔒 These keys help AWS services perform encryption and decryption operations to protect data.

---

## ⚠️ Limitations

- 👀 Customers can view AWS Managed Keys in the KMS console.
- 📋 Customers can view their associated key policies.
- 🚫 Customers cannot directly manage or modify these keys.
- 🔧 They provide less customization and control than Customer Managed Keys.

---

## ⚖️ AWS Managed Keys vs. Customer Managed Keys

| Feature | ☁️ AWS Managed Keys | 👤 Customer Managed Keys |
|---|---|---|
| Creation | Automatically created by AWS services | Created by customers |
| Management | Managed by AWS | Managed by customers |
| Key Rotation | Managed by AWS | Customers can manage rotation |
| Permissions and Policies | Customers cannot directly modify or manage the keys | Customers can configure permissions and policies |
| Customization | Limited | Greater control and flexibility |
| Convenience | AWS handles management and maintenance | Customers handle key administration |

---

### 4. 🌐 AWS Owned Keys

**AWS Owned Keys** are encryption keys fully managed and controlled by AWS.

These keys are used by AWS services to **encrypt data across multiple AWS accounts** and are not directly accessible or manageable by customers.

---

## 🔑 Key Characteristics

- 🤖 **Automatic Management:** AWS handles the creation, rotation, and management of these keys.
- 🚫 **No Customer Access:** Customers cannot view, manage, or delete AWS Owned Keys.
- 🌐 **Shared Across Accounts:** These keys are shared across multiple AWS accounts.
- 🔒 **Default Encryption:** AWS Owned Keys are used for encryption by default in many AWS services.

---

## ⚙️ Use Cases

- ☁️ AWS Owned Keys are typically used by services where customers do not need direct control over encryption keys.
- ✅ They are ideal for scenarios where **simplicity and ease of use** are prioritized over granular control of encryption.

---

## 🛡️ Security and Compliance

- 🔒 AWS ensures the security of these keys through robust internal processes.
- 🏛️ Customers relying on AWS Owned Keys benefit from AWS's compliance with various security standards and certifications.

---

## ⚖️ AWS Owned Keys vs. Other KMS Key Types

| Feature | 🌐 AWS Owned Keys | ☁️ AWS Managed Keys | 👤 Customer Managed Keys |
|---|---|---|---|
| Management | Fully managed by AWS | Managed by AWS for specific services | Managed by customers |
| Customer Visibility | Not visible to customers | Can be viewed in the KMS console | Accessible and manageable by customers |
| Customer Control | No direct control | Limited control | Greater control and flexibility |
| Key Administration | Handled by AWS | Handled by AWS | Handled by customers |
| Sharing | Shared across multiple AWS accounts | Used by the service that created them | Can be used with specific AWS services |
| Main Advantage | Simplicity and ease of use | Convenient service integration | Granular control and customization |

---

### 5. 🔑 Data Keys

**Data Keys** are cryptographic keys generated by AWS Key Management Service (KMS) Customer Master Keys (CMKs) and are primarily designed for use **outside of KMS**.

They are used to **encrypt and decrypt data** in client-side applications or other AWS services.

---

## 🔄 1. Types of Data Keys

### 1. 🔑 Symmetric Data Keys

**Symmetric Data Keys** use a single key for both encryption and decryption.

When generated using the `GenerateDataKey` operation, two versions of the same key are created:

- 📝 **Plaintext Data Key:** Used to encrypt data with an encryption algorithm.
- 🔒 **Encrypted Data Key:** Stored securely and associated with the encrypted data.

### ⚙️ How Symmetric Data Keys Work

1. 🔑 **Generate:** KMS generates a plaintext data key and an encrypted version of that key.
2. 🔓 **Encrypt:** The plaintext data key is used to encrypt the data.
3. 🧹 **Remove:** After encryption, the plaintext key is removed from memory.
4. 💾 **Store:** The encrypted data key is stored securely and associated with the encrypted data.
5. 🔄 **Decrypt:** When the data needs to be decrypted, the encrypted data key is sent back to KMS.
6. 🔓 **Return:** KMS decrypts the encrypted data key using the original CMK and returns the plaintext data key.
7. 📄 **Recover:** The plaintext data key is used to decrypt the data.

### 🎯 Key Idea

**KMS → Plaintext Data Key + Encrypted Data Key → Encrypt Data → Remove Plaintext Key → Store Encrypted Data Key**

### 🔐 `GenerateDataKeyWithoutPlaintext`

- Creates an encrypted data key without generating a plaintext version.

---

### 2. 🔐 Asymmetric Data Key Pairs

**Asymmetric Data Key Pairs** consist of two different keys:

- 🌎 **Public Key:** Used for encryption.
- 🔒 **Private Key:** Used for decryption.

### 🔑 Key Characteristics

- 🔒 The private key is securely stored in KMS and encrypted by a symmetric KMS key.
- 📝 During creation, a plaintext private key, an encrypted private key, and a public key are generated.
- 🔐 Alternatively, a data key pair can be created without generating a plaintext private key.

### ⚙️ Use Cases

Asymmetric Data Key Pairs are used for:

- 💻 Client-side cryptography.
- ✍️ Signing.
- 🔍 Verification.
- 📜 Certificates, such as RSA key pairs.
- 🔏 Digital signatures, such as Elliptic Curve key pairs.
- 🌐 Encryption outside of KMS.

### 🎯 Key Idea

**Public Key → Encryption**

**Private Key → Decryption**

---

## 📊 2. Symmetric Data Keys vs. Asymmetric Data Key Pairs

| Feature | 🔑 Symmetric Data Keys | 🔐 Asymmetric Data Key Pairs |
|---|---|---|
| Key Structure | One key | Public-private key pair |
| Encryption and Decryption | Same key | Separate keys |
| Key Types Generated | Plaintext and encrypted versions of the same key | Public key, plaintext private key, and encrypted private key |
| Primary Use | Encrypting and decrypting data | Client-side cryptography, signing, verification, and encryption outside KMS |
| Key Operations | `GenerateDataKey`, `GenerateDataKeyWithoutPlaintext` | Data key pair generation operations |

---

## 🛡️ 3. Key Characteristics

### 🔑 Key Material

- Key material is a **string of bits** that forms the core element of a cryptographic key.
- Key material is unique unless using **Multi-Region KMS Keys**.

### 🔄 Key Rotation

- Key rotation is recommended as a security best practice.
- It involves periodically replacing key material.

### 🔐 Data Key Formats

- **Symmetric Data Keys:** Have plaintext and encrypted versions of the same key.
- **Asymmetric Data Key Pairs:** Use separate public and private keys for cryptographic operations.

---

## 🌐 4. Use Cases

### 💾 Data Keys

Data Keys are used for encrypting data in:

- 💻 Client-side applications.
- ☁️ AWS services.
- 🪣 Amazon S3, including SSE-KMS.

### 🔐 Data Key Pairs

Data Key Pairs are used for:

- 💻 Client-side cryptography.
- ✍️ Signing.
- 🔍 Verification.
- 🌐 Encryption outside of KMS.
- 📜 Certificates and digital signatures.

---

## 🔒 5. Security Measures

- 🧹 **Plaintext Key Removal:** Plaintext data keys are removed from memory after use.
- 💾 **Encrypted Key Storage:** Encrypted data keys are stored securely.
- 🔑 **Controlled Decryption:** Encrypted data keys can only be decrypted by KMS using the original CMK.
- 🛡️ **Access Control:** Key policies and grants control access to KMS keys and help ensure secure usage.
- 🔄 **Key Rotation:** Periodically replacing key material is recommended as a security best practice.

---

## ⚖️ Key Benefits

- 🔑 Generates cryptographic keys for use outside KMS.
- 💾 Supports data encryption and decryption in applications and AWS services.
- 🔐 Supports symmetric data keys and asymmetric data key pairs.
- 🧹 Helps protect plaintext keys by removing them from memory after use.
- 🔒 Allows encrypted data keys to be stored securely.
- ☁️ Supports encryption use cases involving Amazon S3 and SSE-KMS.
- ✍️ Supports client-side cryptography, signing, and verification through asymmetric data key pairs.
- 🛡️ Supports access control through key policies and grants.

---

## 🎯 Key Takeaway

**Data Keys = Cryptographic Keys Generated by KMS for Use Outside KMS**

Remember these key points:

- 🔑 **Symmetric Data Keys:** Use one key for encryption and decryption.
- 📝 **Plaintext Data Key:** Used to encrypt or decrypt data.
- 🔒 **Encrypted Data Key:** Stored securely and sent back to KMS when decryption is needed.
- ⚙️ **`GenerateDataKey`:** Generates plaintext and encrypted versions of a data key.
- 🔐 **`GenerateDataKeyWithoutPlaintext`:** Generates only an encrypted data key.
- 🌎 **Asymmetric Data Key Pairs:** Use public and private keys for cryptographic operations.
- 🛡️ **Security:** Plaintext keys are removed from memory after use, while encrypted keys are stored securely.

---

### 6. 🛡️ HMAC Keys

**HMAC (Hash-based Message Authentication Code)** is a type of message authentication code (MAC) that combines a **cryptographic hash function** with a **secret cryptographic key**.

HMAC helps ensure:

- 🔍 **Integrity:** The data has not been altered.
- 🛡️ **Authenticity:** The message is from the intended sender.

In AWS KMS, **HMAC keys are symmetric keys** used to create and verify HMAC codes.

---

## ⚙️ How HMAC Works

The HMAC algorithm combines a message with the key material of the HMAC key to generate a **unique, fixed-size tag** associated with the data.

### 🔄 Process

1. 📝 **Message:** The original data that needs verification.
2. 🔑 **Secret Key:** The HMAC key material used in the process.
3. ⚙️ **Hashing:** The message and secret key are processed in a specific sequence.
4. 🏷️ **HMAC Tag:** A fixed-size tag is generated and associated with the data.
5. 🔍 **Verification:** The tag can be verified to check the integrity and authenticity of the data.

### 🎯 Key Idea

**Message + Secret Key → HMAC Algorithm → HMAC Tag**

- 🔄 If even a single character in the data or key changes, the resulting tag will differ.
- 🛡️ This allows changes to the data to be detected.

---

## 🔐 HMAC in AWS KMS

HMAC keys in AWS KMS have the following characteristics:

- 🔑 **Symmetric Keys:** Used to create and verify HMAC codes.
- 📏 **Key Lengths:** Created at varied lengths.
- 📋 **Standards:** These keys conform to the RDS 2104 standards.
- 🔒 **Key Security:** The key material within HMAC keys never leaves the KMS service unencrypted.

---

## 🔄 Operations with HMAC Keys in KMS

### 1. 🏷️ `GenerateMac`

- Used to create the HMAC tag for a given message.
- Combines the message with the HMAC key material to generate the tag.

### 2. 🔍 `VerifyMac`

- Used to verify the integrity and authenticity of data.
- Compares the received tag with a newly calculated tag.

### 🎯 Key Idea

**GenerateMac → Create HMAC Tag**

**VerifyMac → Verify HMAC Tag**

---

## 🌐 Applications of HMAC

HMAC can be used to:

- 🛡️ Authenticate the sender of a message.
- 🔍 Verify that a message has not been tampered with.
- 🔢 Include additional data, such as sequence numbers.
- ⏰ Include timestamps to help prevent replay attacks or detect lost or inserted messages.

---

## 🔑 Key Assumptions

HMAC relies on the assumption that **only the sender and recipient know the shared symmetric key**.

This is critical for verifying the authenticity of a message.

---

## 🛡️ Security Features

- 🔒 Combines a cryptographic hash function with a secret key.
- 🔍 Helps detect changes to data.
- 🛡️ Supports message integrity and authenticity.
- 🔑 Uses shared symmetric key material.
- 🔐 Keeps HMAC key material within the KMS service in unencrypted form only as described by the service's key-protection process.
- 🛡️ Is more cryptographically secure than basic MAC functions due to its construction using hash functions.
- 🔍 Is resistant to attacks that exploit simpler methods of combining keys and messages.

---

## 🎯 Key Takeaway

**HMAC = Message Integrity and Authenticity Using a Secret Symmetric Key**

Remember these key points:

- 🔑 **HMAC Keys:** Symmetric keys used to create and verify HMAC codes.
- 🏷️ **GenerateMac:** Creates an HMAC tag for a message.
- 🔍 **VerifyMac:** Verifies a tag to check data integrity and authenticity.
- 🛡️ **Integrity:** Helps detect whether data has been altered.
- 👤 **Authenticity:** Helps verify that a message comes from someone who knows the shared secret key.
- 🔒 **AWS KMS Security:** HMAC key material remains within the KMS service in protected form.

---

## 📊 Types of Keys in AWS KMS

| Key Type | Description |
|---|---|
| 🔐 AWS KMS Keys | Used for encrypting, decrypting, and generating keys for external use. |
| 👤 Customer Managed Keys | Fully controlled by customers, including permissions. |
| ☁️ AWS Managed Keys | Created and managed by AWS services for specific integrations. |
| 🌐 AWS Owned Keys | Managed by AWS and shared across multiple accounts. |
| 🔑 Data Keys | Used outside KMS to encrypt data and other keys. |
| 🛡️ HMAC Keys | Symmetric keys used to create and verify hash-based message authentication codes. |

---

## 🔒 Encryption Scope

AWS KMS supports **encryption at rest**, but it does not handle encryption for **data in transit**.

### 💾 Data-at-Rest

- KMS supports encryption for stored data.
- It helps protect data across supported AWS services.

### 🌐 Data-in-Transit

- KMS does not handle encryption for data in transit.
- Methods such as **SSL** are required for in-transit encryption.
- Data encrypted at rest with KMS remains in ciphertext during transit.

### 🎯 Key Idea

**KMS → Encryption at Rest**

**SSL → Encryption for Data in Transit**

---

## 📋 Compliance and Auditing

AWS KMS integrates with **AWS CloudTrail** to track and audit encryption key usage.

### 🔍 Key Usage Tracking

CloudTrail records API calls related to KMS key usage, including:

- 🔓 `Decrypt`
- 🔒 `Encrypt`
- 🔑 `GenerateDataKey`

### 📝 Audit Logs

- 💾 Logs are stored in **Amazon S3**.
- 🌐 Logs capture metadata such as source IP addresses.
- 🏛️ These records support compliance and governance purposes.

### 🎯 Key Idea

**AWS KMS API Calls → AWS CloudTrail → Logs in Amazon S3 → Auditing and Compliance**

---

## ⚖️ Key Benefits

- 🔐 Securely stores and generates encryption keys.
- ☁️ Integrates with various AWS services.
- 🪣 Supports Amazon S3 encryption using SSE-KMS.
- 🗄️ Supports encryption for Amazon RDS databases.
- 👤 Allows customers to manage encryption keys and control their usage.
- 🔑 Supports customer managed keys