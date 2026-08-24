# 💰 AWS Budgets Overview

## 🧩 Definition

**AWS Budgets** is a tool designed to help users **manage and control AWS spending** by setting custom budget thresholds.

Budgets can monitor:

- 💵 **Costs**
- 📊 **Usage**
- 📦 **Reserved Instance coverage**
- 📦 **Reserved Instance utilization**

AWS Budgets provides **proactive alerts** when spending approaches or exceeds defined limits.

---

## 💵 Budget Types

Users can create different types of budgets, including:

- 💰 **Cost budgets**
- 📊 **Usage budgets**
- ⚡ **Savings Plans budgets**
- 📦 **Reserved Instances budgets**

---

## 📈 Budget Methods

AWS Budgets supports different methods for monitoring spending:

### 📌 Fixed

Uses a defined budget amount.

### 📅 Planned

Allows budgets to be planned based on spending patterns over time.

### 🤖 Auto-Adjusting

Automatically adjusts the budget based on spending patterns over time.

---

## 🔗 Integration with Trusted Advisor

AWS Budgets can be linked with **AWS Trusted Advisor**.

This allows spending thresholds to become **actionable checks**.

The integration can help:

- 🔍 Identify resources driving cost increases.
- ⚠️ Detect potential cost problems.
- 💰 Proactively control costs.
- 📉 Optimize spending before costs escalate.

---

## 🔔 Alerts and Notifications

AWS Budgets can send alerts through:

- 📧 **Email**
- 📢 **Amazon SNS**
- 💬 **Chat tools such as Slack**

Alerts can be configured for different spending thresholds, such as:

- **50% of budget**
- **80% of budget**

Alerts can be based on:

- 📊 **Actual spending**
- 🔮 **Forecasted spending**

---

## 🎯 Budget Customization

Budgets can be customized using filters based on:

- ⚙️ Specific services
- 🏢 Linked accounts
- 🌎 Regions
- 🏷️ Cost categories
- 🏷️ Tagged resources

### ⚙️ Advanced Options

Advanced options allow users to:

- 📊 Aggregate costs
- 💳 Include credits
- 🏷️ Include discounts
- 🧾 Include taxes

---

## 📋 Budget Reports

**AWS Budget Reports** provide a high-level overview of **budget performance**.

They help users:

- 📊 Review budget performance
- 🔮 Plan future costs
- 📈 Forecast future spending

Reports can be scheduled for:

- 📅 Daily
- 📆 Weekly
- 🗓️ Monthly

---

## 🤖 Budget Actions

AWS Budgets can automatically respond when budget thresholds are reached.

Budget actions can include:

- 🔐 Attaching **IAM policies**
- 🛡️ Applying **Service Control Policies (SCPs)**
- 🛑 Shutting down instances

These actions help prevent **unnecessary spending**.

---

## ⚖️ Key Benefits

- 💰 Helps control AWS spending.
- 🎯 Allows custom spending thresholds.
- 📊 Supports cost and usage budgets.
- 📦 Supports Savings Plans and Reserved Instances.
- 🔔 Provides proactive alerts.
- 📧 Supports email, SNS, and Slack notifications.
- 🔮 Supports actual and forecasted spending alerts.
- 🔗 Integrates with AWS Trusted Advisor.
- 🏷️ Supports filtering by services, accounts, Regions, cost categories, and tags.
- 📋 Provides scheduled Budget Reports.
- 🤖 Supports automated Budget Actions.
- 🛑 Can help prevent unnecessary spending.

### 🧠 Key Idea

**AWS Budgets = Set spending thresholds and monitor AWS costs**

**Alerts = Notify when actual or forecasted spending approaches the budget**

**Trusted Advisor = Helps identify resources driving cost increases**

**Budget Reports = Review and forecast budget performance**

**Budget Actions = Automatically respond to budget thresholds**

---

## 🏠 Analogy

Imagine **AWS Budgets as a smart thermostat** for your home’s heating system.

Just like you set a temperature limit to keep your house comfortable and avoid wasting energy, with **AWS Budgets**, you set spending limits to keep your cloud costs under control.

If the temperature (**your spending**) starts to rise and gets close to your set limit, the thermostat (**AWS Budgets**) sends you an alert—like a warning beep—so you can take action before things get too hot (**before you overspend**).

You can even automate responses, such as turning off the heater (**stopping certain AWS resources**), to make sure you stay within your comfort zone (**budget**).

---

# 🚨 AWS Budget Alerts and Actions

## 🧩 Budget Alerts

**AWS Budget Alerts** provide information when spending approaches or exceeds a defined threshold.

However, an alert by itself does not address the spending issue. **Follow-up actions are required**.

Actions can be:

- 👤 **Manual**
- 🤖 **Automated using Budget Actions**

---

## 👤 Manual Actions

Manual actions can include:

- 📧 Sending emails
- 🔍 Reviewing the resources causing increased spending
- 🛠️ Taking corrective action

---

## 🤖 Automated Budget Actions

AWS Budgets supports three types of automated actions:

### 🔐 IAM Policies

Budget Actions can **change IAM policies** to adjust user permissions.

### 🛡️ Service Control Policies

Budget Actions can modify **Service Control Policies (SCPs)** at the **AWS Organizations** level.

### 🛑 Stop Resources

Budget Actions can stop:

- 🖥️ **EC2 instances**
- 🗄️ **RDS instances**

when budget thresholds are crossed.

---

## ✅ Approval Options

Automated actions can be configured to:

- 🤖 **Apply automatically**
- 👤 **Require manual approval**

This allows organizations to decide whether actions should happen immediately or require confirmation.

---

## ⚙️ Configuring a Budget Action

To add an automated response to a budget alert:

1. 🔐 Select an **IAM role** with the required permissions.
2. 🎯 Choose the desired action.
3. 🌎 Select the **Region**.
4. 🖥️ Select the resource, such as an EC2 instance.
5. ✅ Choose whether the action requires **manual approval** or is applied **automatically**.

For example:

**Budget Threshold → Select IAM Role → Stop EC2 Instance → Automatic or Manual Approval**

---

## 🚨 When the Threshold Is Exceeded

When the budget threshold is exceeded:

1. ⚠️ A budget alert is triggered.
2. 🔔 Notifications are sent.
3. 🤖 The configured Budget Action can execute.
4. 🛑 Resources or permissions can be modified based on the configured action.

---

## ⚖️ Key Benefits

- 🔔 Budget alerts notify users about spending issues.
- 👤 Actions can be performed manually.
- 🤖 Budget Actions automate responses.
- 🔐 IAM policies can be modified.
- 🛡️ SCPs can be modified.
- 🛑 EC2 and RDS instances can be stopped.
- ✅ Actions can require manual approval or happen automatically.
- 🎯 Helps prevent continued spending after a budget threshold is crossed.

### 🧠 Key Idea

**Budget Alert = Tells you spending has reached a threshold**

**Manual Action = User responds to the alert**

**Budget Action = Automatically responds to the alert**

**IAM Policy = Adjust user permissions**

**SCP = Adjust permissions across AWS Organizations**

**EC2/RDS Action = Stop instances to prevent additional spending**