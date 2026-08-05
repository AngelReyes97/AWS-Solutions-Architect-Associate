# 🛡️ AWS Web Application Firewall (WAF) Overview

## 🧩 Definition

**AWS Web Application Firewall (WAF)** is a security service that helps protect web applications from malicious web traffic.

AWS WAF can protect web content delivered through:

- 🌐 **Amazon CloudFront**
- 🔌 **Amazon API Gateway**
- ⚖️ **Application Load Balancers (ALB)**
- 🔄 **AWS AppSync**

AWS WAF helps protect against common web attacks such as:

- 💉 **SQL Injection**
- 🖥️ **Cross-Site Scripting (XSS)**

These attacks are included in the **OWASP Top 10** list.

---

## 🛡️ Security Protection

AWS WAF provides an **additional layer of security** by filtering web traffic before it reaches associated AWS services.

This helps reduce risks caused by malicious traffic, including:

- 💰 **Financial risks**
- 📉 **Reputational risks**
- 🛡️ **Security vulnerabilities**

Implementing security controls such as AWS WAF at the **network perimeter** helps reduce vulnerability risks.

---

## ⚡ AWS WAF Deployment

AWS WAF is designed to be **easier and quicker to deploy** compared to standard WAF solutions.

There are two versions:

- 🏛️ **AWS WAF Classic**
- 🆕 **AWS WAF**

The newer **AWS WAF** is the current version of the service.

---

## 🌐 HTTP and HTTPS Request Filtering

AWS WAF works by filtering:

- 🌐 **HTTP requests**
- 🔐 **HTTPS requests**

AWS WAF evaluates incoming web requests and determines whether they should be allowed to continue.

Only legitimate requests are allowed to be processed by the associated AWS services.

---

## 🏗️ AWS WAF Components

The main components of AWS WAF include:

- 📋 **Web ACLs**
- 📜 **Rules**
- 📦 **Rule Groups**

These components work together to determine whether web requests should be:

- ✅ **Allowed**
- 🚫 **Blocked**
- 🔢 **Counted**

---

## 📋 Web Access Control Lists (Web ACLs)

**Web Access Control Lists (Web ACLs)** are a fundamental component of **AWS Web Application Firewall (WAF)** used to manage and control access to web resources.

Web ACLs can be associated with supported resources such as:

- ☁️ **Amazon CloudFront Distributions**
- 🔌 **Amazon API Gateway REST APIs**
- ⚖️ **Application Load Balancers**
- 🔄 **AWS AppSync GraphQL APIs**

---

## 📜 Web ACL Rules

Web ACLs contain **Rules** that specify criteria for assessing web requests.

Rules determine whether requests should be:

- ✅ **Allowed** - the request is forwarded onto the resource.
- 🚫 **Blocked** - the request is dropped and a response is sent back to the requester.
- 🔢 **Counted** - counts the numbers of matching requests.

Rules contain:

- 📝 **Statements** — Inspect web requests against specific criteria.
- ⚙️ **Actions** — Determine what happens when the criteria are met.

---

## ⚙️ Default Action

Each Web ACL has a **default action** that applies to requests that do not meet any rule criteria.

The default action can be:

- ✅ **Allow**
- 🚫 **Block**

---

## 📦 Rule Groups

**Rule Groups** are collections of rules that can be applied to different Web ACLs.

Rule Groups can include:

- ☁️ **AWS-managed Rule Groups**
- 🏢 **Third-party vendor Rule Groups**

This allows collections of rules to be applied across different Web ACLs.

---

## 🌐 Web ACL Traffic Flow

The logical architecture involves:

```text
👤 User Request
       ↓
☁️ CloudFront Distribution
       ↓
🛡️ WAF Web ACL
       ↓
📜 Rules / Rule Groups
       ↓
✅ Allow or 🚫 Block
       ↓
☁️ CloudFront Environment
```

The request is received by the CloudFront Distribution and then forwarded to the associated WAF Web ACL for filtering before traversing the CloudFront environment.

---

## 🛡️ Network Perimeter Security

AWS WAF should be implemented at the **network perimeter** to help reduce vulnerability risks.

Placing security controls at the perimeter allows malicious traffic to be filtered before reaching the environment.

This provides:

- 🛡️ An additional security layer.
- 🚫 Filtering of malicious traffic.
- 🔐 Protection against common web attacks.
- 📉 Reduced vulnerability risks.

---

## 🆚 AWS WAF Components

| Component | Purpose |
|---|---|
| 📋 **Web ACL** | Main configuration component containing rules that assess web requests |
| 📜 **Rule** | Inspects requests using statements and applies an action |
| 📦 **Rule Group** | Collection of rules that can be applied to different Web ACLs |

---

## ✨ Features

- 🛡️ Protects web applications from malicious traffic.
- 🌐 Filters HTTP and HTTPS requests.
- ☁️ Integrates with Amazon CloudFront.
- 🔌 Integrates with Amazon API Gateway.
- ⚖️ Integrates with Application Load Balancers.
- 🔄 Integrates with AWS AppSync.
- 💉 Helps protect against SQL injection.
- 🖥️ Helps protect against cross-site scripting.
- 📋 Uses Web ACLs to configure request filtering.
- 📜 Uses Rules to inspect web requests.
- 📦 Uses Rule Groups to organize collections of rules.
- ⚙️ Supports Allow, Block, and Count actions.

---

## 🎯 Use Cases

- 🌐 Protecting web applications from malicious traffic.
- ☁️ Protecting web content delivered through CloudFront.
- 🔌 Protecting API Gateway applications.
- ⚖️ Protecting applications behind Application Load Balancers.
- 🔄 Protecting AppSync applications.
- 💉 Protecting against SQL injection.
- 🖥️ Protecting against cross-site scripting.
- 🛡️ Filtering malicious traffic at the network perimeter.

---

## ⚖️ Key Benefits

- 🛡️ Provides an additional layer of web application security.
- 🚫 Filters malicious HTTP and HTTPS requests.
- 🔐 Helps protect against common web attacks.
- ⚡ Is easier and quicker to deploy than standard WAF solutions.
- 💰 Helps reduce financial risks from malicious traffic.
- 📉 Helps reduce reputational risks.
- 🌐 Allows security controls to be implemented at the network perimeter.
- 🔄 Allows rules and rule groups to be reused across different Web ACLs.

---

## 🧠 Analogy: AWS WAF as a Security Guard

Imagine **AWS WAF** as a **security guard at the entrance of a building**, where the building represents your **web application**.

The guard checks everyone who tries to enter, looking for:

- ⚠️ Suspicious behavior.
- 🚫 Known troublemakers.

### 📋 Rules as a Security Checklist

The guard uses a **list of rules**, similar to a checklist, to decide what to do with each visitor.

The guard can:

- ✅ **Allow** someone to enter.
- 🚫 **Block** someone from entering.
- 🔢 **Count** someone for monitoring.

This is similar to how AWS WAF uses **Rules** to inspect web requests and determine whether they should be allowed, blocked, or counted.

### 📦 Rule Groups as Collections of Instructions

The guard can also receive **new instructions or updated lists of people to watch out for**.

Similarly, AWS WAF can be updated with:

- 📜 New **Rules**.
- 📦 New **Rule Groups**.

These help protect against new threats.

### 🛡️ Protecting the Building

The goal is to ensure that only **safe and legitimate visitors** are allowed into the building.

Similarly, AWS WAF filters web traffic to help keep web applications secure from **unwanted and malicious intruders**.


---

# Understanding Rules and Rule Groups

## 🧩 Definition

**Rules and Rule Groups** are important components of **AWS WAF Web ACLs** that determine whether web traffic should be:

- ✅ **Allowed**
- 🚫 **Blocked**
- 🔢 **Counted**

They help ensure that web traffic is properly evaluated for **security and effectiveness**.

---

## 📦 Managed Rule Groups

**Managed Rule Groups** are predefined collections of rules created by:

- ☁️ **AWS**
- 🏢 **Other Vendors**

They are designed to protect against **specific vulnerabilities**.

Managed Rule Groups can save:

- ⏱️ Time
- 🛠️ Effort

Instead of creating custom rules from scratch, predefined rule groups can be used to protect against known vulnerabilities.

---

## 📊 Web ACL Capacity Units (WCUs)

Each Rule Group has a **capacity rating** measured in **Web ACL Capacity Units (WCUs)**.

WCUs represent the resources required by AWS WAF to process the rules.

The total WCU limit for a Web ACL is:

> **1,500 WCUs**

Exceeding the WCU limit can cause failures.

---

## 🛠️ Custom Rules

Custom rules can be created using:

- 🌐 **IP Sets**
- 🧰 **Rule Builders**
- 📦 **Rule Groups**

---

## 🌐 IP Sets

**IP Sets** allow rules to be configured based on **source IP addresses**.

They can be used to define rules based on the IP address making the request.

---

## 🧰 Rule Builders

**Rule Builders** provide ways to create more complex rules.

They include:

- 🖱️ **Visual Editor**
- 📝 **JSON Editor**

These tools can be used to create and configure custom rules.

---

## ⏱️ Rate-Based Rules

**Rate-Based Rules** count requests coming from a **single IP address over a five-minute period**.

When the configured request limit is exceeded, the rule can trigger actions such as:

- 🚫 **Block**
- 🔢 **Count**

Rate-based rules can therefore help identify IP addresses making excessive requests.

---

## 🔄 Regular Rules

Regular rules use **if/then logic** to determine what action should be taken.

For example:

> **IF** a request matches specific criteria, **THEN** perform an action.

Possible actions include:

- ✅ **Allow**
- 🚫 **Block**
- 🔢 **Count**

---

## 📦 Rule Groups

**Rule Groups** are collections of rules that can be used with Web ACLs.

Rule Groups:

- 📦 Contain multiple rules.
- ⚙️ Must be created **outside of Web ACLs**.
- 📊 Require a **maximum WCU capacity** to be set.
- 🔒 Have a maximum WCU capacity that **cannot be changed later**.
- 📈 Can be monitored using **CloudWatch metrics**.

---

## 📊 Rule Group WCU Capacity

When creating a Rule Group, a **maximum WCU capacity** must be specified.

This capacity:

- 📊 Defines the maximum WCU capacity for the Rule Group.
- 🔒 Cannot be changed after the Rule Group is created.

---

## 📈 Monitoring Rule Groups

Rule Groups can be monitored using **CloudWatch metrics**.

This allows the Rule Groups to be monitored based on their activity.

---

## 🔢 Rule Priority

**Rule Priority** is important because AWS WAF rules are executed **in order**.

The order of rules determines which rule is evaluated first.

A typical priority order is:

1. ✅ **Whitelist trusted IP addresses**
2. 🚫 **Block blacklisted IP addresses**
3. 🛡️ **Block bad signatures related to attack patterns**

The rule order is important because AWS WAF evaluates the rules sequentially.

---

## 🔄 Rule Evaluation Example

A Web ACL may evaluate traffic in the following order:

```text
🌐 Incoming Request
        ↓
1️⃣ Check Whitelisted IPs
        ↓
✅ Allow trusted IP
        ↓
2️⃣ Check Blacklisted IPs
        ↓
🚫 Block known bad IP
        ↓
3️⃣ Check Bad Signatures
        ↓
🛡️ Block attack patterns
```

---

## 🧠 Analogy: AWS WAF Rules and Rule Groups as Concert Security

Imagine you are organizing security at the entrance of a **concert**.

You have several **security guards (Rules)**, each with a specific job:

- 🎟️ One guard checks **tickets**.
- 🪪 Another guard checks **IDs**.
- 🚫 Another guard looks for **prohibited items**.

Each guard performs an individual security check.

---

### 👮 Rules as Individual Security Guards

Each **Rule** is like an individual security guard with a specific responsibility.

For example:

- 🎟️ Check tickets.
- 🪪 Check IDs.
- 🚫 Check for prohibited items.

Similarly, AWS WAF Rules perform individual checks, such as checking:

- 🌐 Country
- 🌍 IP address
- 🛡️ Other request criteria

---

### 👥 Rule Groups as Security Teams

You can group security guards into **teams (Rule Groups)** based on their tasks.

For example:

- 🎟️ **Ticket Validation Team**
  - 👮 Guard checks ticket.
  - 👮 Guard verifies ticket information.

- 🛡️ **Safety Check Team**
  - 👮 Guard checks for prohibited items.
  - 👮 Guard performs additional safety checks.

Each team contains multiple guards performing related checks.

---

### 🚪 Web ACL as the Main Security Gate

The **Web ACL** is like the **main security gate** at the concert.

You can assign different **Rule Groups** to the Web ACL.

When someone tries to enter:

1. 👤 A person arrives at the entrance.
2. 🚪 The request reaches the main security gate.
3. 👥 Each Rule Group applies its checks.
4. 👮 Individual Rules perform their specific checks.
5. 🚫 If a guard finds an issue, the person might be denied entry.
6. ✅ If the person passes the required checks, they can enter.

Similarly, in AWS WAF:

- 📜 **Rules** = Individual security checks.
- 📦 **Rule Groups** = Collections of related security checks.
- 📋 **Web ACL** = Main security gate controlling access.

This structure allows AWS WAF to organize multiple security checks and use them together to control who gets access to web resources.