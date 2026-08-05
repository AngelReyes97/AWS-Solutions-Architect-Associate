# 🔐 AWS IAM Policy Evaluation Logic

## 🧩 Definition

**IAM Policy Evaluation** determines whether a request to access an AWS resource is **allowed or denied**.

The process begins with **authentication**, which verifies the user's identity.

After authentication, AWS determines the **context of the request** to identify the relevant policies that need to be evaluated.

---

## 🔑 Authentication

The first step when accessing AWS resources is **authentication**.

Authentication:

- 👤 Verifies the user's identity.
- 🔐 Confirms who is making the request.
- ➡️ Allows AWS to continue evaluating the request.

---

## 🧠 Request Context

After authentication, AWS determines the **context of the request**.

The request context helps AWS identify:

- 👤 Who is making the request.
- 🗄️ Which resource is being accessed.
- ⚙️ What action is being requested.
- 📜 Which policies are relevant to the request.

---

## ⚖️ Policy Evaluation

AWS evaluates multiple policy types to determine whether access should be allowed.

By default:

> 🚫 **All access is denied unless explicitly allowed by a policy.**

However:

> ❌ **An explicit Deny takes precedence over an Allow.**

Therefore, even if one policy allows an action, an explicit Deny in another applicable policy will prevent access.

---

## 🛡️ Explicit Deny

An **explicit Deny** in any applicable policy takes precedence over an Allow.

For example:

- ✅ One policy allows access to an S3 resource.
- ❌ Another policy explicitly denies the same access.
- 🚫 The request is **denied**.

The explicit Deny overrides the Allow.

---

## 🔄 Policy Evaluation Order

Policies are evaluated in the following order:

1. 🏢 **Organizational Service Control Policies (SCPs)**
2. 🗄️ **Resource-Based Policies**
3. 🚧 **IAM Permission Boundaries**
4. 👤 **Identity-Based Policies**

AWS evaluates these policy types to determine whether the requested action is allowed.

---

## 🪣 Example: Stuart Uploading an S3 Object

Imagine a user named **Stuart** requests permission to **upload an object to an Amazon S3 bucket**.

AWS evaluates the request by checking the applicable policies.

### 1. 🏢 Organizational Service Control Policies

AWS checks whether an SCP contains an explicit Deny for the requested action.

- ❌ No Deny exists.
- ➡️ Evaluation continues.

### 2. 🗄️ Resource-Based Policies

AWS checks the applicable resource-based policies.

- ❌ No Deny exists.
- ➡️ Evaluation continues.

### 3. 🚧 IAM Permission Boundaries

AWS checks the applicable permission boundary.

- ❌ No Deny exists.
- ➡️ Evaluation continues.

### 4. 👤 Identity-Based Policies

AWS checks Stuart's identity-based policies.

- ✅ The policy grants Stuart permission to upload the object.
- ➡️ The requested action is allowed.

---

## 🔄 Evaluation Flow

```text
👤 Stuart makes request
        ↓
🔑 Authentication
        ↓
🧠 Determine request context
        ↓
🏢 Organizational SCPs
        ↓
🗄️ Resource-Based Policies
        ↓
🚧 IAM Permission Boundaries
        ↓
👤 Identity-Based Policies
        ↓
🔍 Check for Explicit Deny
        ↓
✅ Explicit Allow exists
        ↓
🪣 Request Allowed
```