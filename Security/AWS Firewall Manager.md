# 🛡️ AWS Firewall Manager Overview

## 🧩 Definition

**AWS Firewall Manager** is a service designed to simplify **security management across multiple AWS accounts** by providing centralized protection for various resources.

It automatically applies and manages security policies for:

- 🆕 Existing resources.
- 🆕 Newly created resources.
- 🏢 Resources across multiple AWS accounts.

Resources are protected when they match the configured security policy settings.

---

## 🎯 Centralized Security Management

AWS Firewall Manager provides centralized management of security policies across multiple AWS accounts.

It can automatically:

- 🔐 Apply security policies to existing resources.
- 🆕 Apply security policies to newly created resources.
- 🏢 Manage security policies across multiple AWS accounts.
- ⚙️ Maintain security policies based on configured settings.

---

## 🔗 AWS Services Supported

AWS Firewall Manager integrates with:

- 🛡️ **AWS WAF**
- 🛡️ **AWS Shield Advanced**
- 🔥 **AWS Network Firewall**
- 🔐 **VPC Security Groups**
- 🌐 **Amazon Route 53 Resolver DNS Firewall**

---

## 🏢 AWS Organizations Requirement

**AWS Organizations** is a prerequisite for using AWS Firewall Manager.

AWS Organizations allows Firewall Manager to centrally manage security policies across multiple AWS accounts.

The AWS Organization must have:

- 🏢 Multiple AWS accounts as needed.
- ⚙️ **All Features enabled**.
- 🚫 Not just **Consolidated Billing**.

---

## 👤 Firewall Manager Administrator Account

To use AWS Firewall Manager, designate an AWS account as the **Firewall Manager Administrator account**.

The designated account is responsible for:

- 🛡️ Managing security policies.
- ⚙️ Configuring Firewall Manager.
- 🏢 Managing security across the AWS Organization.

---

## 📊 AWS Config Requirement

**AWS Config** must be enabled for:

- 👤 The Firewall Manager Administrator account.
- 🏢 Any other accounts where resource security management is needed.
- 🌎 All relevant AWS Regions.

This allows Firewall Manager to manage the security of resources across the organization.

---

## 🔄 AWS Resource Access Manager

You can optionally enable **sharing with AWS Organizations** in **AWS Resource Access Manager (RAM)**.

This can be used to apply security policies to:

- 🔥 **Network Firewalls**
- 🌐 **DNS Firewalls**

---

## 🌎 AWS Regions

Any AWS Regions that are **disabled by default** must be enabled in the **AWS Management Console** if you need to manage resources within those Regions.

This ensures Firewall Manager can manage resources in the required AWS Regions.

---

## ⚙️ Firewall Manager Prerequisites

Before configuring AWS Firewall Manager, ensure the following requirements are met:

1. 🏢 **AWS Organizations**
   - AWS Organizations must be configured.
   - **All Features** must be enabled.

2. 👤 **Firewall Manager Administrator**
   - Designate an AWS account as the Firewall Manager Administrator account.

3. 📊 **AWS Config**
   - Enable AWS Config for the administrator account.
   - Enable AWS Config for other accounts where resource security management is needed.
   - Enable it across all relevant Regions.

4. 🔄 **AWS Resource Access Manager**
   - Optionally enable sharing with AWS Organizations.
   - Required for applying security policies to Network Firewalls and DNS Firewalls.

5. 🌎 **AWS Regions**
   - Enable any Regions that are disabled by default if resources need to be managed there.

Once these prerequisites are met, you can begin configuring **AWS Firewall Manager and its security policies**.

---

## ✨ Features

- 🛡️ Provides centralized security management.
- 🏢 Manages security across multiple AWS accounts.
- 🔐 Automatically applies security policies to matching resources.
- 🆕 Applies policies to newly created resources.
- 🔄 Manages existing and newly created resources.
- 🔗 Integrates with AWS WAF.
- 🛡️ Integrates with AWS Shield Advanced.
- 🔥 Integrates with AWS Network Firewall.
- 🔐 Integrates with VPC Security Groups.
- 🌐 Integrates with Amazon Route 53 Resolver DNS Firewall.
- 🏢 Uses AWS Organizations for centralized account management.

---

## 🎯 Use Cases

- 🏢 Managing security policies across multiple AWS accounts.
- 🔐 Centrally managing security for resources across an AWS Organization.
- 🛡️ Applying AWS WAF policies across accounts.
- 🛡️ Managing AWS Shield Advanced protection.
- 🔥 Managing Network Firewall security policies.
- 🔐 Managing VPC Security Group policies.
- 🌐 Managing Route 53 Resolver DNS Firewall policies.
- 🆕 Automatically protecting newly created resources that match configured settings.

---

## ⚖️ Key Benefits

- 🛡️ Centralizes security management across multiple AWS accounts.
- ⚙️ Simplifies security policy management.
- 🔄 Automatically applies policies to existing and newly created resources.
- 🏢 Reduces the need to manage security policies individually across accounts.
- 🔐 Provides centralized protection for multiple AWS resources.
- 🌐 Supports security management across relevant AWS Regions.

---

# 🛡️ AWS Firewall Manager Policies Overview

## 🧩 Definition

**AWS Firewall Manager Policies** allow you to create and manage security policies across **multiple AWS accounts**.

Different policies are available for different resource types, with each policy having its own configuration.

Multiple policies can be created for the **same resource type**.

---

## 🔗 Supported Policy Types

AWS Firewall Manager supports policies for:

- 🛡️ **AWS WAF**
- 🛡️ **AWS Shield Advanced**
- 🔥 **AWS Network Firewall**
- 🔐 **VPC Security Groups**
- 🌐 **Amazon Route 53 Resolver DNS Firewall**

---

## ⚙️ Policy Creation Process

Creating an AWS Firewall Manager policy generally involves **five steps**:

1. 🌎 **Choose the Policy and Region**
- which policy you like in addition to the region.
2. 📝 **Describe the Policy**
- Define the details of the policy
3. 🎯 **Define the Policy Scope**
- Defines which resources and accounts are covered byu the policy that you're creating.
4. 🏷️ **Configure Policy Tags**
- optional step
5. 🔍 **Review and Create the Policy**

---

## 🛡️ AWS WAF Policy

**AWS WAF Policies** is a service that helps to prevent websites or web applicaions from malicious attacks and use **Web ACLs** to manage web requests.

They can include:

- 📋 **Web ACLs**
- 📦 **Rule Groups**

These components provide protection for web resources.

---

## 🛡️ Shield Advanced Policy

**Shield Advanced Policies** help protect resources against **DDoS (distributed denail of service) attacks**.

Creating a Shield Advanced Policy involves:

- 📝 Naming the policy.
- ⚙️ Defining the required actions.

---

## 🔥 Network Firewall Policy

**Network Firewall Policies** manage **firewall rules across VPCs**.

They provide centralized management of firewall rules across the applicable VPC resources.

---

## 🔐 VPC Security Group Policy

**VPC Security Group Policies** control traffic at the **instance level**.

They allow security policies to manage traffic associated with instances.

---

## 🌐 Route 53 Resolver DNS Firewall Policy

**Route 53 Resolver DNS Firewall Policies** help protect resources by blocking DNS queries to **malicious domains**.

---

## 🎯 Policy Scope

The **Policy Scope** determines which resources the Firewall Manager policy applies to.

Before creating a policy, it is important to understand:

- 🏢 The resources being protected.
- 🔗 The AWS services involved.
- 🎯 Which resources should fall within the policy scope.

---

## 💰 Policy Costs

AWS Firewall Manager policies can incur costs.

Costs can include charges associated with:

- 📊 **AWS Config Rules**

Consider the costs associated with the policies before creating them.

---

## 🆕 Automatic Protection for New Resources

Once a Firewall Manager policy is created, it can automatically protect **new resources** that fit within the defined policy scope.

This reduces the need for administrators to manually configure security protections for every newly created resource.

---

## 🔄 Policy Management Flow

```text
🛡️ Choose Policy & Region
        ↓
📝 Describe Policy
        ↓
🎯 Define Policy Scope
        ↓
🏷️ Configure Policy Tags
        ↓
🔍 Review & Create
        ↓
🆕 New Resources Matching Scope
        ↓
🛡️ Automatically Protected
```

---

## ✨ Features

- 🏢 Manages security policies across multiple AWS accounts.
- 🔗 Supports multiple AWS security services.
- 🔄 Allows multiple policies for the same resource type.
- 🛡️ Supports AWS WAF policies.
- 🛡️ Supports Shield Advanced policies.
- 🔥 Supports Network Firewall policies.
- 🔐 Supports VPC Security Group policies.
- 🌐 Supports Route 53 Resolver DNS Firewall policies.
- 🆕 Automatically protects new resources that fit the policy scope.

---

## 🎯 Use Cases

- 🏢 Managing security across multiple AWS accounts.
- 🛡️ Managing AWS WAF protection.
- 🛡️ Protecting resources against DDoS attacks with Shield Advanced.
- 🔥 Managing firewall rules across VPCs.
- 🔐 Controlling traffic at the instance level with VPC Security Groups.
- 🌐 Blocking DNS queries to malicious domains.
- 🆕 Automatically protecting newly created resources.

---

## ⚖️ Key Benefits

- 🏢 Centralizes security policy management across multiple accounts.
- ⚙️ Simplifies security configuration across resources.
- 🆕 Automatically protects new resources within the defined scope.
- 🔄 Reduces administrative effort.
- 🛡️ Supports multiple AWS security services.
- 🎯 Allows policies to be scoped to specific resources.