# 📝 Amazon S3 Server Access Logging  

## 🧩 Definition  
**Server Access Logging** records **detailed information about requests** made to an S3 bucket and its objects.  
This helps with **root-cause analysis, auditing, and compliance** purposes.  

---

## ⚙️ What Is Logged  
- Request type (GET, PUT, DELETE, etc.) 🔄  
- Resource accessed (bucket or object) 📦  
- Requester's IP address or IAM user 🌐  
- Time and date of the request ⏰  
- Response status and error code ✅❌  
- Object size 📏  

> ⚠️ Logging is **best-effort**, not guaranteed. Logs are typically sent every few hours, and **some requests might not be captured**.  

---

## ⚙️ How to Enable Logging  
1. Select the **bucket** in the S3 console  
2. Go to the **Properties** tab → **Server Access Logging** → **Enable** ✅  
3. Choose a **destination bucket** for the logs (must be in the same region)  
4. Configure **target prefix** and **log object key format**  

> 🔒 Notes:  
> - Destination bucket **cannot** have server logging, S3 Object Lock, or Requester Pays enabled  
> - Default encryption **SSE-S3** can be used; **SSE-KMS cannot**  

---

## 💰 Cost Implications  
- Enabling logging has **no direct cost**  
- **Storage costs** are incurred for storing log files  

---

## 🧠 Analogy: Server Access Logging  
Imagine you have a **diary** 📖 where you jot down every visitor who comes to your house, what time they arrived, what they did while they were there (like if they just dropped off a package or stayed for a chat), and when they left.  

Now, replace your **house** with an **Amazon S3 bucket**, and the **visitors** with requests made to that bucket.  

**Amazon S3 Server Access Logging** is like this diary, recording details about each request made to your S3 bucket:  
- Request type (GET, PUT, DELETE) 🔄  
- Requester's details (IP address or IAM user) 🌐  
- Time and date ⏰  
- Actions performed on the objects 📦  

This log helps you understand **who is accessing your bucket** and **what they are doing**, much like how your diary helps you keep track of visits to your house.

---

## 🛠️ S3 Logging Permissions  

When setting up **server access logging** for a source S3 bucket, logs are delivered to a **destination bucket**. Specific permissions are required on the **destination bucket** to allow this.  

### Automatic Permissions via Console  
- Using the **AWS Management Console** automatically sets the required permissions ✅  
- The **S3 logging service** needs **write access** to the destination bucket to deliver log files 📤  

### Bucket Policy Recommendations  
- AWS **no longer recommends using bucket ACLs** for access control ❌  
- Instead, use a **bucket policy** to grant the **S3 logging service principal** (`logging.s3.amazonaws.com`) **write access** using the `s3:PutObject` action ✍️  

### Manual Setup  
- When configuring **server access logging programmatically**, the **bucket policy must be created manually** 🛠️  

> Ensuring proper permissions is crucial for logs to be delivered successfully and for auditing purposes.

---

## 🧾 Amazon S3 Server Access Log Record Structure

Each **log entry** in an Amazon S3 server access log is **space-delimited**, meaning fields are separated by spaces.  
If certain data is **unknown or not applicable**, it’s represented with a **hyphen (-)**.

---

### 🧱 Key Fields Explained

- 🧍‍♂️ **Bucket Owner:** Canonical user ID of the bucket owner.  
- 🪣 **Bucket:** Name of the S3 bucket related to the request.  
- ⏰ **Time:** UTC timestamp of when the request occurred.  
- 🌐 **Remote IP Address:** IP address of the requester.  
- 🧩 **Requester:** IAM identity for authenticated users, or “–” for anonymous ones.  
- 🧾 **Request ID:** Unique identifier assigned to each request.  
- ⚙️ **Operation:** Type of operation performed (e.g., `GET`, `PUT`, `DELETE`).  
- 📁 **Key:** The object name involved in the request.  
- 🔗 **Request-URI:** The URI element from the HTTP request.  
- ✅ **HTTP Status:** Numeric HTTP status code returned (e.g., 200, 404).  
- ❌ **Error Code:** Error code if one occurred, otherwise “–”.  
- 📤 **Bytes Sent:** Number of bytes sent in the response.  
- 📦 **Object Size:** Size of the object in bytes.  
- ⏱️ **Total Time:** Time (in ms) from request receipt to final byte sent.  
- ⚡ **Turnaround Time:** Time taken by S3 to process the request.  
- 🔁 **Referrer:** HTTP referrer header value, if available.  
- 💻 **User-Agent:** Value of the HTTP user-agent header (e.g., browser info).  
- 🆔 **Version ID:** Version ID of the object, if versioning is enabled.  
- 🧮 **Host ID:** Extended S3 Request ID for troubleshooting.  
- 🔐 **Signature Version:** Signature version used for authentication.  
- 🧰 **Cipher Suite:** Cipher suite used if SSL was applied.  
- 🪪 **Authentication Type:** Type of authentication used.  
- 🌍 **Host Header:** Endpoint (hostname) used to connect to Amazon S3.  
- 🧱 **TLS Version:** Version of TLS protocol used by the client.  
- 🎯 **Access Point ARN:** ARN of the access point used (if applicable).  
- 🧱 **ACLRequired:** Indicates if an ACL was required for authorization.

---

## 🛡️ Controlling Access to Amazon S3 Resources

### 👤 Identity-Based Policies Overview
Identity-based policies are attached to **IAM identities**, such as **users**, **groups**, or **roles**, and define what actions these entities can perform on AWS resources.  
These policies are essential for managing **who can access what** in your AWS environment.

---

### 🧩 Types of Identity-Based Policies

#### 1. **Managed Policies**
- Stored in the **IAM library** and reusable across multiple entities.  
- Two main types:  
  - 🟦 **AWS Managed Policies** – Pre-created by AWS for common use cases.  
  - 🟨 **Customer Managed Policies** – Created by users for custom permissions and more granular control.

#### 2. **Inline Policies**
- Embedded **directly within** a single user, group, or role (one-to-one relationship).  
- Not stored in the IAM library, making them **less flexible** and harder to manage.  
- Best used for **unique permissions** that shouldn’t be shared or reused.

---

### ⚙️ Usage Considerations
- ✅ **Managed policies** are preferred for reusability and easier maintenance.  
- ⚠️ **Inline policies** should be used **sparingly**, typically for specific, one-off permission needs.

---

### 🧱 Policy Structure
Identity-based policies are written in **JSON** and typically include the following elements:
- `"Effect"` → Whether the policy **allows** or **denies** access.  
- `"Action"` → The **API actions** (like `s3:GetObject`, `s3:PutObject`) the policy controls.  
- `"Resource"` → The specific **AWS resources** (like a bucket or object) the policy applies to.

> **Note:** Identity-based policies do **not** include a `"Principal"` field because the policy is inherently linked to the IAM identity itself.

---

### 🗂️ Resource-Based Policies
Resource-based policies are **attached directly to AWS resources** (like an **S3 bucket**) and define **who** can access them and **what actions** they can perform.

- Common example: **S3 Bucket Policy** 🪣  
  - Specifies who can access the bucket and what permissions they have.  
  - Written in **JSON**, and must include a `"Principal"` element to specify the allowed or denied entities.

---

### 🔁 Difference Between Identity-Based and Resource-Based Policies

| Feature | Identity-Based Policy | Resource-Based Policy |
|----------|-----------------------|-----------------------|
| **Attached To** | IAM user, group, or role | AWS resource (e.g., S3 bucket) |
| **Includes Principal?** | ❌ No | ✅ Yes |
| **Scope** | Defines what the identity can access | Defines who can access the resource |

---

### 🤝 IAM Roles and Trust Policies
In the context of **IAM Roles**, a **trust relationship policy** is a type of **resource-based policy**.  
It defines **which principals** (users, accounts, or services) are allowed to **assume the role**.

---

### ⚖️ IAM Policies vs Bucket Policies

| Feature | **IAM Policies** | **Bucket Policies** |
|----------|------------------|---------------------|
| **Scope** | Can control access for multiple AWS services at once | Controls access **only** to S3 buckets and objects |
| **Management** | Centrally managed in IAM, allowing you to maintain all access policies in one place | Managed directly in the **S3 console** or via the bucket’s JSON policy |
| **Reusability** | You can use the same 1–2 IAM policies across multiple buckets | Typically, one bucket policy per bucket |
| **Cross-Account Access** | Requires creating and assuming IAM roles | Can directly grant cross-account access without IAM role setup |
| **Best Use Case** | When managing permissions across multiple AWS services and resources | When you want to keep **S3-specific** access controls within S3 itself |

---

✅ **Summary:**  
Use **IAM policies** for centralized, multi-service access control and consistency across buckets.  
Use **Bucket policies** when you need fine-grained, S3-specific permissions or cross-account access without additional IAM complexity.

---

## 🌐 Amazon S3 – Cross-Origin Resource Sharing (CORS)

### Overview
**Cross-Origin Resource Sharing (CORS)** in Amazon S3 allows resources (such as objects in a bucket) to be requested from a different domain than the one serving the web page.  
This is especially useful for **client-side web applications** that need to access or modify data stored in S3.

---

### 🔧 Configuration
To configure **CORS** for an S3 bucket:
1. Open the **Amazon S3 Console**.
2. Select your **bucket**.
3. Navigate to the **Permissions** tab.
4. Locate the **CORS Configuration** section.
5. Add a CORS policy that defines:
   - **Allowed origins**
   - **Allowed methods**
   - **Allowed headers**
   - **Exposed headers**
   - **MaxAgeSeconds** (how long preflight responses can be cached)

---

### 🧩 Example CORS Policy
Below is an example CORS configuration that allows `PUT`, `POST`, and `DELETE` requests from a specific origin (`https://example.com`):

```json
[
  {
    "AllowedHeaders": ["*"],
    "AllowedMethods": ["PUT", "POST", "DELETE"],
    "AllowedOrigins": ["https://example.com"],
    "ExposeHeaders": ["x-amz-server-side-encryption"],
    "MaxAgeSeconds": 3000
  }
]

```

---

