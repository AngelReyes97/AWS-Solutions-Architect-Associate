# 🔐 Client-Side Encryption with Amazon S3

## 🧩 Definition

**Client-Side Encryption** ensures that data is encrypted before it leaves the customer's environment and is uploaded to Amazon S3.

It provides additional security by encrypting data before transmission and allows customers to manage the encryption process themselves.

### 🔑 Key Characteristics

- 🔒 **Encryption Before Upload:** Data is encrypted before leaving the customer's environment.
- 🛡️ **Additional Security:** Protects data before it reaches Amazon S3.
- ☁️ **S3 Storage:** Amazon S3 treats client-side encrypted objects as regular data and does not detect or manage their encryption.
- ⚙️ **Server-Side Encryption:** Client-side encryption can be used without requiring S3 server-side encryption.

---

## 🔐 1. S3 Encryption Client

The **S3 Encryption Client** facilitates client-side encryption by generating a unique symmetric plaintext data encryption key for each object.

It uses **Envelope Encryption** to protect the data key.

### 🗝️ Envelope Encryption

**Envelope Encryption** is a process in which:

- 🔑 A plaintext data key encrypts the object data.
- 🔒 A wrapping key encrypts the data key.
- 🗝️ The encrypted data key is stored alongside the encrypted object data.

This allows the object data to be encrypted while protecting the data key used for encryption.

---

## 🔑 2. Wrapping Key Options

The S3 Encryption Client supports two wrapping key options.

### 1. ☁️ CSE-KMS (AWS KMS-Provided Keys)

- 🔗 Uses AWS Key Management Service (KMS).
- 🔐 KMS manages the wrapping key.
- 🗝️ The wrapping key encrypts the data encryption key.

### 2. 👤 CSE-C (Customer-Provided Keys)

- 🔑 Customers provide their own wrapping keys.
- 🔐 Supports customer-provided raw AES-GCM or RSA keys.
- 🗝️ The wrapping key encrypts the data encryption key.

---

## 🔄 3. Client-Side Encryption Process

The S3 Encryption Client encrypts the object data before uploading it to Amazon S3.

### 📋 Step-by-Step Process

1. 🗝️ **Generate a Data Key**
   - The S3 Encryption Client generates a unique plaintext data encryption key.

2. 🔒 **Encrypt the Data Key**
   - A copy of the data key is encrypted using the wrapping key, managed through KMS or provided by the customer.

3. 🔐 **Encrypt the Object**
   - The plaintext data key encrypts the object data.

4. 🧹 **Delete the Plaintext Key**
   - The plaintext data key is deleted from memory after encryption.

5. ☁️ **Upload to Amazon S3**
   - The encrypted object data and encrypted data key are uploaded to S3 for storage.

### 🔁 Encryption Flow

**Original Object → Generate Data Key → Encrypt Object Data → Encrypt Data Key → Upload Encrypted Object and Data Key to S3**

---

## 🔓 4. Client-Side Decryption Process

The S3 Encryption Client decrypts the object after retrieving it from Amazon S3.

### 📋 Step-by-Step Process

1. 📥 **Retrieve Encrypted Data**
   - The client retrieves the encrypted object data and encrypted data key from S3.

2. 🔑 **Decrypt the Data Key**
   - The encrypted data key is sent to the wrapping key mechanism, using KMS or the customer's key, to obtain a plaintext data key.

3. 🔓 **Decrypt the Object**
   - The plaintext data key decrypts the object data.

4. 🧹 **Delete the Plaintext Key**
   - The plaintext data key is deleted from memory after decryption.

### 🔁 Decryption Flow

**Retrieve Encrypted Object and Data Key → Decrypt Data Key → Decrypt Object Data → Delete Plaintext Data Key**

---

## 💻 5. Programming Language Support

The S3 Encryption Client supports multiple programming languages, including:

- ☕ **Java**
- 🐹 **Go**
- 🐘 **PHP**

---

## ⚖️ 6. Client-Side vs. Server-Side Encryption

| Feature | Client-Side Encryption | Server-Side Encryption |
|---|---|---|
| **Where Encryption Occurs** | Before data is uploaded to S3 | Within Amazon S3 |
| **Who Encrypts the Data** | The client application | Amazon S3 |
| **Key Management** | Customer-controlled or integrated with KMS | Managed through S3 or KMS, depending on the encryption type |
| **S3 Awareness** | S3 treats encrypted objects as regular data | S3 performs the server-side encryption process |
| **Primary Benefit** | Data is encrypted before leaving the customer's environment | Simplifies encryption of objects stored in S3 |

---

## ⚖️ Key Benefits

- 🔒 Encrypts data before it leaves the customer's environment.
- 🛡️ Provides additional protection for data before upload.
- 🗝️ Uses envelope encryption to protect data encryption keys.
- 🔑 Supports KMS-managed and customer-provided wrapping keys.
- ☁️ Stores encrypted object data and encrypted data keys in S3.
- 💻 Supports multiple programming languages, including Java, Go, and PHP.

---

## 🎯 Key Takeaway

**Client-Side Encryption = Encrypt Data Before Uploading It to Amazon S3**

Remember these key points:

- 🔐 **S3 Encryption Client:** Generates a unique symmetric plaintext data key for object encryption.
- 🗝️ **Envelope Encryption:** Uses a wrapping key to encrypt the data encryption key.
- ☁️ **CSE-KMS:** Uses a wrapping key managed by AWS KMS.
- 👤 **CSE-C:** Uses customer-provided AES-GCM or RSA wrapping keys.
- 🧹 **Plaintext Data Key:** Deleted from memory after encryption or decryption.
- ☁️ **Amazon S3:** Stores the encrypted object and encrypted data key without detecting client-side encryption.
- 🔓 **Decryption:** Requires the encrypted data key to be decrypted before the object data can be decrypted.