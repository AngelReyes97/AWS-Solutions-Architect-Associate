# 🔐 Amazon Cognito Overview

## 🧩 Definition
**Amazon Cognito** simplifies **user authentication** for applications, including **mobile and web applications**.

It addresses the challenges of managing user information and allows users to authenticate using **existing corporate credentials**.

---

## 👤 User Authentication
**User authentication** is a crucial part of building applications, but it can often be **tedious**.

Traditionally, applications stored user information in **relational databases**.

These databases could be hosted:
- 🏢 **Onsite**
- ☁️ **In the cloud**

Managing these databases required significant **setup and maintenance**.

---

## 🗄️ AWS Database Options
In AWS, user information might be stored in databases hosted on:

- 🗃️ **Amazon RDS**
- 🖥️ **EC2 instances**

Both options involve considerable **management effort**.

---

## 🏢 Corporate Credentials
Corporate environments often use **directory services**, such as **Microsoft Active Directory**.

Instead of requiring users to create new credentials for an application, it is preferable for them to log in using their **existing corporate credentials**.

---

## 🔐 How Amazon Cognito Helps
**Amazon Cognito** addresses these authentication challenges by:

- 🔐 Simplifying **user authentication**.
- 🏢 Allowing integration with **existing corporate credentials**.
- 👤 Helping manage **user sign-in, authentication, and access**.
- ⚙️ Reducing the time and effort required to manage authentication.

---

## ⚖️ Key Benefits
- 🔐 Simplifies **user authentication** for mobile and web applications.
- 🗄️ Reduces the need to manage user information through databases.
- ⚙️ Helps reduce the **setup and maintenance effort** associated with authentication.
- 🏢 Allows integration with **existing corporate credentials**.
- 👤 Manages **user sign-in, authentication, and access**.
- ⏱️ Saves time and effort so developers can focus on their applications.

---

## 🧠 Analogy: Amazon Cognito as a Professional Doorman

Imagine you’re organizing a **big party**. You want to make sure only **invited guests** can enter, and you don’t want to spend all your time checking invitations at the door.

- 📝 In the past, you might have kept a **handwritten guest list** and checked each person yourself. This is **time-consuming and easy to make mistakes**.
- 🛡️ Now, imagine you hire a **professional doorman (Amazon Cognito)**.
- 🎟️ The doorman **checks invitations and verifies identities**.
- 🌐 The doorman can even let guests use their **existing club memberships**, such as **Facebook or Google accounts**, to get in.
- 🏢 If your guests are from a company, the doorman can check their **work badges (Active Directory)** too.
- 🔐 You don’t have to worry about security or keeping the list updated—the **doorman handles it all**.
- 🎉 This lets you focus on **making your party great**.

That’s what **Amazon Cognito** does for your applications: it manages **user sign-in, authentication, and access**, saving you **time and effort**.

---

# 🔐 Amazon Cognito User Pools Overview

## 🧩 Definition
**Amazon Cognito User Pools** are a key component of **Amazon Cognito**, designed to manage **user authentication and directory services** for **web and mobile applications**.

They provide a directory of users and help developers manage **user sign-up, sign-in, and authentication**.

---

## 👤 User Sign-Up and Sign-In
User Pools facilitate **user sign-up and sign-in processes**.

- 📝 Allow users to **sign up** for an application.
- 🔐 Allow users to **sign in** using their credentials.
- 📚 Create a **directory of users**.
- ⚙️ Allow developers to manage **user authentication**.

---

## 🌐 Third-Party Identity Providers
Amazon Cognito User Pools support integration with **third-party identity providers**.

Supported providers include:
- 🍎 **Apple**
- 📘 **Facebook**
- 🔵 **Google**
- 🛒 **Amazon**
- 🔐 **SAML identity providers**

This enables:
- 🌐 **Social sign-in**
- 🔑 **Single sign-on (SSO)**

---

## 📝 Customizable User Attributes
Developers can customize the **user attributes** collected during sign-up.

- 📋 Define **mandatory fields** such as:
  - 📧 **Email**
  - 🏠 **Address**
- ➕ Create **custom attributes** as needed.
- ⚙️ Customize what information users provide during registration.

---

## 🛡️ Security Features
User Pools provide **security features** designed to help protect applications.

### 🔑 Password Policies
Developers can use **password policies** to help manage user authentication.

### 📱 Multi-Factor Authentication (MFA)
User Pools support **multi-factor authentication (MFA)**.

MFA is especially important for applications that handle **sensitive information**.

---

## 🔄 Account Recovery
Amazon Cognito User Pools include built-in **account recovery features**.

Recovery options include:
- 📧 **Email recovery**
- 📱 **Phone recovery**

These features are available **without requiring additional backend services**.

---

## 🔗 Cognito Identity Pools Integration
Amazon Cognito User Pools can work together with **Amazon Cognito Identity Pools**.

Together, they can provide comprehensive solutions for:
- 👤 **User management**
- 🔐 **Access control**

---

## ⚖️ Key Benefits
- 👤 Manages **user authentication and directory services**.
- 📝 Supports **user sign-up and sign-in**.
- 🌐 Integrates with **third-party identity providers**.
- 🔑 Supports **social sign-in and single sign-on**.
- 📝 Allows developers to customize **user attributes**.
- 🛡️ Provides **password policies and MFA**.
- 🔄 Includes built-in **account recovery** options.
- 🔗 Can work with **Amazon Cognito Identity Pools** for comprehensive **user management and access control**.

---

## 🧠 Analogy: Amazon Cognito User Pools as a Secure Guest List and Check-In Desk

Imagine **Amazon Cognito User Pools** as a **secure guest list and check-in desk at a private event**.

- 🎟️ When someone wants to attend your event (**use your app**), they first **sign up by providing details** like their name, email, or even a photo—just like registering at the entrance.
- 📝 You can decide what information is required, such as an **ID, invitation, or special code**.
- 🔐 Once registered, guests can check in easily next time—they just **show their credentials**.
- 🛡️ You can make the check-in stricter by asking for extra proof, like a **password and a code sent to their phone (multi-factor authentication)**.
- 🌐 If a guest prefers, they can use their **social media account (like Facebook or Google)** to check in, similar to showing a **VIP pass from another trusted event**.
- 🎨 The check-in desk can also be **customized to match your event’s branding**.
- 🤖 You can **automate actions**, such as sending a welcome email when someone checks in.
- 🔐 In short, **Cognito User Pools manage who gets in, how they prove their identity, and make the whole process smooth and secure**.

---

# 🔐 Amazon Cognito Pools Authentication Flow Overview

## 🧩 Definition
The **Amazon Cognito Pools Authentication Flow** involves two main components:

- 👤 **User Pools** — Handle **user sign-up and sign-in**.
- 🔑 **Identity Pools** — Provide **temporary AWS credentials** for authenticated users or unauthenticated guests to access AWS services.

Together, they help manage **authentication and authorization** while providing secure access to AWS resources.

---

## 👤 User Pools

**User Pools** are used for **user sign-up and sign-in processes**.

Users can authenticate using:

- 🔐 Credentials from the **User Pool itself**
- 🍎 **Apple**
- 📘 **Facebook**
- 🔵 **Google**
- 🔑 **SAML-backed services**

### 🔄 Authentication Process

The authentication process works as follows:

1. 📱 The **application initiates an authentication request**.
2. 🔍 Cognito processes the authentication request.
3. ✅ If authentication is successful, Cognito provides a **token**.
4. ⚠️ Alternatively, Cognito may provide a **challenge for further verification**.

---

## 🔑 Identity Pools

**Identity Pools** provide **temporary AWS credentials** for:

- 👤 **Authenticated users**
- 👥 **Unauthenticated guests**

These credentials allow users to access **AWS services**.

Examples include:
- 🪣 **Amazon S3**
- 🗄️ **Amazon DynamoDB**

---

## 🔄 User Pool → Identity Pool Flow

After a user authenticates through a **User Pool**, the authentication flow continues:

1. 👤 The user authenticates through a **User Pool**.
2. 🎫 An **Identity Token** is generated.
3. 📤 The Identity Token is sent to the **Identity Pool**.
4. 🔄 The Identity Pool uses the Identity Token to create an **STS Token**.
5. 🔐 The STS Token grants access to AWS services such as **S3 or DynamoDB**.

### 📊 Simplified Flow

**User → User Pool → Identity Token → Identity Pool → STS Token → AWS Services**

---

## 🔄 Standardized Authentication Flow

The authentication flow ensures that **all tokens are standardized**, regardless of the authentication method used.

This allows for:

- 🔗 **Seamless integration** with AWS services.
- 🔌 Integration with **AWS APIs**.
- 🔐 Consistent access to AWS resources regardless of how the user authenticated.

---

## ⚙️ Offloading Authentication Complexity

Amazon Cognito is designed to **offload the complexity of authentication and authorization from developers**.

Instead of developers having to manage the entire authentication and authorization process themselves:

- 🔐 Cognito handles the authentication flow.
- 🎫 Cognito manages the tokens involved in the process.
- 🔑 Identity Pools provide temporary AWS credentials.
- 👨‍💻 Developers can focus on **application functionality**.
- 🛡️ Applications can maintain **secure access to resources**.

---

## ⚖️ Key Benefits
- 👤 **User Pools** handle user **sign-up and sign-in**.
- 🔑 **Identity Pools** provide **temporary AWS credentials**.
- 🌐 Users can authenticate through **User Pools or third-party identity providers**.
- 🎫 Authentication results in tokens or challenges for further verification.
- 🔄 **Identity Tokens** can be passed from User Pools to Identity Pools.
- 🔐 **STS Tokens** provide access to AWS services such as **S3 and DynamoDB**.
- 🔗 Standardized tokens enable seamless integration with **AWS services and APIs**.
- 👨‍💻 Offloads authentication and authorization complexity from developers.

---

## 🧠 Analogy: Amazon Cognito as an Event Check-In and Access System

Imagine **Amazon Cognito** as a security system for a large event.

### 👤 User Pool — The Check-In Desk

The **User Pool** is like the event's **check-in desk**.

- 🎟️ Guests can sign in using their **event credentials**.
- 🌐 They can also use trusted passes from other organizations, such as **Apple, Facebook, Google, or SAML-backed services**.
- 📱 The application is like the guest approaching the check-in desk and requesting entry.
- ✅ If everything checks out, the guest receives a **token**.
- ⚠️ If additional verification is needed, the guest receives a **challenge**.

### 🔑 Identity Pool — The Access Pass Office

The **Identity Pool** is like a separate office that provides **temporary access passes**.

- 🎫 After the guest successfully checks in, their **Identity Token** is sent to the Identity Pool.
- 🔄 The Identity Pool uses that token to create an **STS Token**.
- 🔐 The STS Token acts as a temporary pass that allows the guest to access specific resources, such as **S3 or DynamoDB**.

### 🏢 The Complete Process

Think of the process like this:

**Check In → Receive Identity Token → Exchange for Temporary Access Pass → Access AWS Services**

The entire system handles the complicated authentication and authorization process for you, allowing the **event organizers (developers)** to focus on running the event (**building the application**) while ensuring guests have **secure access to the appropriate resources**.

---

## 🧠 Analogy: Amazon Cognito Authentication Flow as Entering a Secure Building

Imagine you’re **entering a secure building**:

1. 🏢 **Reception Desk (Login Screen)**
   - You arrive at the front desk and present your **ID**.
   - Your ID represents your **credentials**, such as a username and password or a badge from a partner company.

2. 🛡️ **Security Check (InitiateAuth)**
   - The receptionist checks your ID.
   - If everything looks good, you are either:
     - 🎫 Given a **pass (token)**.
     - ❓ Asked extra questions (**a challenge**, such as a CAPTCHA or security question) to make sure you are not an imposter.

3. ❓ **Answering Questions (RespondToAuthChallenge)**
   - If you receive a challenge, you must **answer it**.
   - ✅ If you answer correctly, you receive your **pass**.
   - 🔄 If not, you might receive another question or be **denied entry**.

4. 🎫 **Access Granted (Tokens)**
   - Once you have your **pass (token)**, you can enter the building and **use its services**.

🔐 This flow ensures that **only the right people get access**, while allowing **extra checks** to be added when suspicious activity requires additional verification.

---

# 🔑 Amazon Cognito Identity Pools Overview

## 🧩 Definition
**Amazon Cognito Identity Pools**, also known as **Federated Identities**, provide **temporary AWS credentials** to users or guests who need access to **AWS services**.

Identity Pools work together with **Amazon Cognito User Pools** to allow users to access specific AWS features.

---

## 🔗 Integration with User Pools
Amazon Cognito Identity Pools can work in conjunction with **Amazon Cognito User Pools**.

- 👤 User Pools handle **user sign-up and sign-in**.
- 🔑 Identity Pools provide **temporary AWS credentials**.
- ☁️ These credentials allow users to access specific **AWS services and features**.

---

## 🌐 Identity Provider Federation
Identity Pools support federation with different types of identity providers.

### 🌍 Public Identity Providers
Identity Pools support public identity providers such as:

- 🛒 **Amazon**
- 📘 **Facebook**
- 🔵 **Google**

### 🏢 Custom Identity Providers
Identity Pools also support custom identity providers such as:

- 🔐 **SAML**
- 🔗 **OpenID Connect**

---

## 👤 Types of Identities
Identity Pools define two types of identities:

### 1. 🔐 Authenticated Identities
**Authenticated identities** are users who have been verified by a **public login provider**.

- ✅ Require verification.
- 🎫 Receive access based on their assigned permissions.
- ☁️ Can access AWS services according to their associated role and policies.

### 2. 👥 Unauthenticated Identities
**Unauthenticated identities** allow users to access AWS resources without being authenticated.

- 👤 Useful for **guest access**.
- 👀 Can provide **preliminary resource visibility**.
- 🔒 Provide **limited access**.

---

## 🛡️ Roles and Permissions
Each identity type is associated with **roles**.

These roles contain **policies** that determine what the identity can access within AWS.

- 🔐 **Roles** define the access assigned to an identity.
- 📜 **Policies** dictate the permissions.
- 👀 Permissions establish what users can **see**.
- ✏️ Permissions establish what users can **modify**.
- 🚧 These permissions create boundaries around what users are allowed to access.

---

## ⚖️ Identity Pools vs. User Pools

| Feature | 👤 User Pools | 🔑 Identity Pools |
|---|---|---|
| Primary Purpose | User **sign-up and sign-in** | Authentication and **access control for AWS services** |
| Application Access | Manage users for applications | Provide access to **AWS services** |
| Credentials | Handle user authentication | Provide **temporary AWS credentials** |
| Identity Types | User accounts | **Authenticated and unauthenticated** identities |
| Permissions | Manage user authentication | Roles and policies determine AWS permissions |

### 🧠 Key Distinction

> **User Pools = Who are you?** 👤  
> **Identity Pools = What AWS resources can you access?** 🔑

---

## ⚙️ Identity Pool Access Flow

The basic process can be summarized as:

1. 👤 A user or guest requests access.
2. 🔍 The Identity Pool determines whether the identity is **authenticated or unauthenticated**.
3. 🔐 The appropriate **role** is associated with the identity.
4. 📜 The role's **policies** determine what the user can access.
5. 🎫 The user receives **temporary AWS credentials**.
6. ☁️ The credentials allow access to permitted **AWS services**.

---

## ⚖️ Key Benefits
- 🔑 Provides **temporary AWS credentials**.
- 👤 Supports both **authenticated and unauthenticated identities**.
- 🌐 Supports federation with public identity providers such as **Amazon, Facebook, and Google**.
- 🔐 Supports custom identity providers such as **SAML and OpenID Connect**.
- 🛡️ Uses **roles and policies** to control AWS permissions.
- 👥 Supports **guest access** through unauthenticated identities.
- ☁️ Allows users to access specific **AWS services and features**.
- 🔗 Works together with **Amazon Cognito User Pools**.

---

## 🧠 Analogy: Amazon Cognito Identity Pools as a Theme Park Guest Pass System

Imagine **Amazon Cognito Identity Pools** as a **guest pass system at a theme park**.

- 🎟️ When visitors arrive, some already have **tickets (authenticated users)**, while others do not (**unauthenticated users**).
- 🎫 The park gives everyone a **wristband**, which represents their **temporary credentials**.
- 🟢 Visitors with tickets receive a **special wristband** that lets them access all the rides (**AWS services**) they are allowed to use.
- 🟡 Guests without tickets receive a **basic wristband** that only allows access to certain areas (**limited AWS resources**).
- 🔍 The park (**Cognito Identity Pool**) checks who you are and gives you the **appropriate wristband**.
- 🛡️ The wristband ensures you can only access what you are **permitted to use**.
- 👥 This allows both **registered visitors and guests** to enjoy the park while giving them **different levels of access**.

### 🎯 Remember

**User Pool = Sign up and sign in** 👤

**Identity Pool = Temporary AWS credentials and access to AWS services** 🔑

---

# 🔐 Amazon Cognito Authentication and Token Flow

## 🧩 Definition
The **Amazon Cognito authentication process** allows users to sign in through **Cognito User Pools** and then access back-end services, APIs, or other AWS services.

The process uses different tokens depending on the service being accessed:

- 🎫 **Cognito User Pool (CUP) Token** — Used for authentication and authorization with back-end services or APIs.
- 🔑 **STS Token** — Generated through an Identity Pool when accessing services that do not accept CUP tokens.

---

## 👤 User Sign-In

The authentication process begins when users **sign in through Cognito User Pools**.

Users can authenticate through:

- 🔐 **Cognito User Pools**
- 🌐 **Social sign-ins**
- 🏢 **SAML-backed services**

---

## 🎫 Identity Token → CUP Token

After the user authenticates:

1. 👤 The user signs in through an **Identity Provider (IDP)**.
2. 🎫 An **Identity Token** is sent from the **IDP to the Cognito User Pool**.
3. 🔄 The Identity Token is converted into a standardized **Cognito User Pool (CUP) Token**.

### 📊 Simplified Flow

**Identity Provider → Identity Token → Cognito User Pool → CUP Token**

---

## 🔗 CUP Token for Back-End Services and APIs

The **CUP Token** is used for **authentication and authorization** with back-end services or APIs.

Examples include:

- 🌐 **API Gateway**
- ⚡ **Lambda**

### 📊 Flow

**CUP Token → Back-End Service / API → Access**

---

## 🪣 CUP Token → Identity Pool → STS Token

Some AWS services do **not accept CUP tokens**, such as:

- 🪣 **Amazon S3**
- 🗄️ **Amazon DynamoDB**

For these services, the CUP token is sent to the **Identity Pool**.

The process is:

1. 🎫 The **CUP Token** is sent to the **Identity Pool**.
2. 🔄 The Identity Pool generates an **STS Token**.
3. 🔑 The STS Token provides **AWS credentials**.
4. 🛡️ The credentials are linked to an **AWS role**.
5. ☁️ The application can access other **AWS services on behalf of the user**.

### 📊 Simplified Flow

**CUP Token → Identity Pool → STS Token → AWS Credentials → AWS Role → AWS Services**

---

## 🔄 Complete Authentication Flow

The complete process can be summarized as:

**User → Identity Provider → Identity Token → Cognito User Pool → CUP Token**

From there, the flow depends on the service:

### 🌐 Back-End Services / APIs

**CUP Token → API Gateway / Lambda**

### ☁️ AWS Services That Do Not Accept CUP Tokens

**CUP Token → Identity Pool → STS Token → AWS Credentials → AWS Role → AWS Services**

---

## ⚖️ Key Benefits
- 🔐 Supports authentication through **Cognito User Pools**.
- 🌐 Supports **social sign-ins and SAML-backed services**.
- 🔄 Converts Identity Provider tokens into a standardized **CUP Token**.
- 🔗 Allows CUP Tokens to authenticate and authorize access to **back-end services and APIs**.
- 🪣 Supports access to services such as **S3 and DynamoDB** through an Identity Pool.
- 🔑 Uses **STS Tokens** to provide AWS credentials.
- 🛡️ Links AWS credentials to an **AWS role**.
- ☁️ Allows applications to access AWS services **on behalf of the user**.

---

## 🧠 Analogy: Amazon Cognito as a Secure Office Building Access System

Imagine you’re visiting a **secure office building**.

- 🏢 **Step 1 — Check In at the Front Desk**
  - First, you check in at the front desk with your **ID**.
  - This is like signing in with **Cognito User Pools** or using a **social login**.
  - The receptionist verifies your identity.

- 🎫 **Step 2 — Receive a Visitor Badge**
  - After verifying your identity, the receptionist gives you a **visitor badge**.
  - This represents the **Cognito User Pool Token (CUP Token)**.
  - The CUP Token can be used to authenticate and authorize access to back-end services or APIs.

- 🔐 **Step 3 — Request Special Access**
  - Now, imagine you want to access special rooms, such as **AWS services like S3 or DynamoDB**.
  - These rooms require a **special access card**.
  - You take your visitor badge (**CUP Token**) to the **security office (Identity Pool)**.

- 🎟️ **Step 4 — Exchange the Badge for a Temporary Access Card**
  - The security office exchanges your visitor badge for a **temporary access card (STS Token)**.
  - The STS Token provides **AWS credentials** linked to an **AWS role**.

- 🚪 **Step 5 — Access Permitted Resources**
  - The temporary access card lets you open the doors to the **resources you are allowed to access**, based on your assigned role.

### 🔄 Complete Flow

**Check In → Receive Visitor Badge → Exchange Badge for Special Access Card → Access Permitted Resources**

**Authenticate → CUP Token → Identity Pool → STS Token → AWS Credentials → AWS Services**

The key idea is that you first **authenticate and receive a CUP Token**, then exchange that token through the **Identity Pool** when you need AWS credentials to access services such as **S3 or DynamoDB**.

---

# 🔐 AWS Identity Federation Overview

## 🧩 Definition
**AWS Identity Federation** is a method that allows users to **authenticate with one provider** and access **resources from another provider**.

It uses a **trust relationship** between:

- 👤 **Identity Provider (IdP)** — The provider that authenticates the user.
- 🏢 **Service Provider (SP)** — The provider that gives the user access to resources.

---

## 🔑 Single Sign-On (SSO)

**Identity Federation** enables **Single Sign-On (SSO)**.

SSO allows users to:

- 🔐 **Log in once**.
- 🚪 Access **multiple services**.
- ❌ Avoid re-entering their credentials for every service.

This is achieved through **assertions**.

### 📜 Assertions
**Assertions** contain **user metadata** and are sent from the:

**Identity Provider (IdP) → Service Provider (SP)**

The assertion allows the Service Provider to use information about the authenticated user.

---

## ☁️ AWS Identity Federation Services

AWS provides several services for implementing **identity federation**:

- 🔐 **AWS Single Sign-On (SSO)**
- 🛡️ **AWS Identity and Access Management (IAM)**
- 👤 **Amazon Cognito**

Each service supports federated access in different scenarios.

---

## 🔐 AWS Single Sign-On (SSO)

**AWS SSO** allows users to access **multiple AWS accounts within an organization** using a **single identity provider**.

It supports:

- 📚 **Built-in user directories**
- 🏢 External identity providers such as **Microsoft Active Directory**

### 🎯 Key Idea

**One Identity Provider → Multiple AWS Accounts**

This allows users to use a **single identity** when accessing multiple AWS accounts within an organization.

---

## 🛡️ AWS IAM Federation

**AWS IAM** supports **federated access** using different identity providers for each AWS account.

IAM federation uses authentication standards such as:

- 🔐 **SAML 2.0**
- 🔗 **OpenID Connect**

### 🎯 Key Idea

Different AWS accounts can use **different identity providers** for federated access.

---

## 👤 Amazon Cognito Federation

**Amazon Cognito** is designed for **secure authentication and access control** for:

- 🌐 **Web applications**
- 📱 **Mobile applications**

Cognito supports:

- 🔐 **SAML 2.0**
- 🌐 **Web identity federation**

Amazon Cognito can also **scale to millions of users**.

---

## ⚖️ AWS SSO vs. AWS IAM vs. Amazon Cognito

| Service | Primary Use | Federation |
|---|---|---|
| 🔐 **AWS SSO** | Access multiple AWS accounts within an organization using a single identity provider | Built-in directories and external providers such as Microsoft Active Directory |
| 🛡️ **AWS IAM** | Federated access for AWS accounts | SAML 2.0 and OpenID Connect |
| 👤 **Amazon Cognito** | Authentication and access control for web and mobile applications | SAML 2.0 and web identity federation |

---

## 🧠 Key Differences

### 🔐 AWS SSO
Allows you to create a Single sign-on approach to access **multiple AWS accounts** within an **AWS Organization** using a single identity provider for all.

### 🛡️ AWS IAM
Supports **federated access** for AWS accounts using identity providers and standards such as **SAML 2.0 and OpenID Connect**.

### 👤 Amazon Cognito
Enables **secure authentication to your web or mobile applications** using both SMAL 2.0 and web identity federation.

---

## ⚖️ Key Benefits
- 🔐 Enables **Single Sign-On (SSO)**.
- 👤 Allows users to authenticate with one provider and access resources from another.
- 🔗 Establishes a **trust relationship** between identity providers and service providers.
- 📜 Uses **assertions containing user metadata** to support federated access.
- ☁️ Provides multiple AWS services for implementing **identity federation**.
- 🏢 **AWS SSO** supports access to multiple AWS accounts within an organization.
- 🛡️ **AWS IAM** supports federation using **SAML 2.0 and OpenID Connect**.
- 📱 **Amazon Cognito** provides authentication and access control for **web and mobile applications**.
- 📈 Amazon Cognito can **scale to millions of users**.