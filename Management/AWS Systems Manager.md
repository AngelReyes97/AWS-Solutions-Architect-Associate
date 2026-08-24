# ⚙️ AWS Systems Manager Overview

## 🧩 Definition

**AWS Systems Manager** is a comprehensive suite of **fully managed services** designed to automate the configuration and ongoing management of systems at scale.

It supports:

- 🐧 **Linux systems**
- 🪟 **Windows systems**

These systems can run on:

- ☁️ **Amazon EC2**
- 🏢 **Your own data center**
- 🌐 **Other cloud platforms**

---

## 🤖 Automation and Management

AWS Systems Manager enables automated:

- ⚙️ **Configuration**
- 🛠️ **Management**
- 🔧 **Maintenance**

It can be used for tasks such as:

- 📋 **Software inventory collection**
- 🩹 **Patch management**
- 🔄 **Resource configuration changes**

---

## 📊 Systems Manager Explorer

**Systems Manager Explorer** provides a customizable **operations dashboard**.

It allows users to view:

- 📊 Operational data
- 📋 Work items
- 🏢 Information across multiple accounts
- 🌎 Information across multiple Regions

---

## 🔗 Integration

AWS Systems Manager integrates with other AWS services, including:

- 📊 **Amazon CloudWatch**
- 🔐 **AWS Identity and Access Management (IAM)**

These integrations provide:

- 👀 Enhanced monitoring
- 🔒 Access control

---

## 🤖 Systems Manager Agent

AWS Systems Manager requires an **agent** to be installed on each instance that needs to be managed.

The agent is:

- ✅ Pre-installed on **Amazon Linux AMIs**
- ✅ Pre-installed on **AWS Windows AMIs**
- 🔧 Available for manual installation on other systems

---

## 🔐 Managed Instance Roles

Each managed instance requires an **IAM role**.

This IAM role facilitates communication between:

**Managed Instance → AWS Systems Manager**

AWS provides predefined **managed policies** to simplify this setup.

---

## 🖥️ Fleet Manager

**Fleet Manager** provides visibility into **managed instances**.

It helps users view and manage their systems through AWS Systems Manager.

---

## 💻 Session Manager

**Session Manager** allows secure and interactive **shell access** to instances.

It does not require:

- 🚫 Open inbound ports
- 🚫 Bastion hosts

This provides a secure way to access managed instances.

---

## 📈 Scalability and Security

AWS Systems Manager is built for **cloud scalability**.

It allows users to manage:

- 🖥️ Large fleets of instances
- 🔐 Securely
- ⚡ Efficiently

It does not require complex licensing models.

---

## 🎯 Use Cases

AWS Systems Manager is useful for:

- 🏗️ **Architects**
- 👨‍💻 **Developers**
- 🛠️ **System operators**

It provides a unified, scalable, and secure way to automate:

- 🔧 Machine maintenance
- ⚙️ System configuration
- 🛠️ Management workflows

Across multiple environments.

---

## 🎯 Basic Flow

**Systems → Systems Manager Agent + IAM Role → AWS Systems Manager → Automate Configuration and Management**

---

## ⚖️ Key Benefits

- 🤖 Automates system configuration and ongoing management.
- 🐧 Supports Linux systems.
- 🪟 Supports Windows systems.
- ☁️ Supports Amazon EC2 environments.
- 🏢 Supports systems running in your own data center.
- 🌐 Supports systems running on other cloud platforms.
- 📋 Supports software inventory collection.
- 🩹 Supports patch management.
- 🔄 Supports resource configuration changes.
- 📊 Provides operational visibility through Systems Manager Explorer.
- 🔗 Integrates with Amazon CloudWatch and IAM.
- 🤖 Uses the Systems Manager Agent to manage instances.
- 🔐 Uses IAM roles to facilitate communication with managed instances.
- 🖥️ Fleet Manager provides visibility into managed instances.
- 💻 Session Manager provides secure shell access without open inbound ports or bastion hosts.
- 📈 Supports managing large fleets of instances at scale.
- 🔒 Provides a unified and secure approach to managing systems.

### 🧠 Key Idea

**AWS Systems Manager = Centralized automation and management of systems at scale**

**Systems Manager Agent = Installed on systems that need to be managed**

**IAM Role = Allows managed instances to communicate with Systems Manager**

**Fleet Manager = Visibility into managed instances**

**Session Manager = Secure shell access without open inbound ports or bastion hosts**

---

## 🧠 Analogy: AWS Systems Manager as a Central Control Room

Imagine **AWS Systems Manager** as the **central control room of a large building complex**.

In this control room, you have a dashboard that lets you:

- 👀 Monitor every room
- ⚙️ Configure every room
- 🛠️ Manage every room

Each room represents a:

- 🖥️ Server
- 💻 Instance

These rooms can be located:

- ☁️ In the cloud
- 🏢 On-premises
- 🌐 On other platforms

Instead of sending maintenance staff to each room individually, you can use the central control room to:

- 🔧 Schedule repairs
- 🔄 Update software
- 📋 Check inventory
- 👀 Monitor systems
- ⚙️ Ensure everything is running smoothly

All from **one central location**.

You don't need separate keys or special access for each room because the control room handles **secure connections** for you.

---

# ⚙️ AWS Systems Manager Features and Resource Management

## 🧩 Overview

AWS Systems Manager includes various features that help manage AWS instances effectively.

These features include:

- 🖥️ **Fleet Manager**
- 💻 **Session Manager**
- 📄 **Documents**
- 🗓️ **Maintenance Windows**
- ➕ Other Systems Manager features

These tools work together to help manage and operate AWS instances.

---

## 🛠️ Systems Management Capabilities

AWS Systems Manager can be used for:

- 📋 **Inventory management**
- 🩹 **Patching**
- 💻 **Running commands**
- 🔐 **Secure connections to EC2 instances**

---

## 📄 Documents and Maintenance Windows

AWS Systems Manager uses:

- 📄 **Documents**
- 🗓️ **Maintenance Windows**

These help manage AWS instances effectively.

---

## 📂 Resource Grouping

Resources can be grouped in several ways for better management and visibility.

Resources can be grouped:

- ✋ **Manually**
- 🏷️ **By instance tags**
- 📂 **Using Resource Groups**

Proper grouping makes it easier to manage and operate on related resources.

---

## 🗂️ Resource Groups

**Resource Groups** are collections of AWS resources within the **same Region**.

Resources can be grouped using:

- 🏷️ **Tags**
- 🏗️ **CloudFormation stacks**

Resource Groups help improve:

- 👀 Resource visibility
- ⚙️ Resource management

---

## 🖥️ AWS Management Console

The **AWS Management Console** organizes resources by:

- 📂 **Service category**

This helps users locate and manage AWS resources.

---

## 🏷️ Tag Editor

The **Tag Editor** facilitates:

- ✏️ Bulk editing
- 🏷️ Bulk tagging

This helps simplify the management of multiple AWS resources.

---

## 🏷️ Importance of Tagging

Proper tagging is important for leveraging AWS Systems Manager features.

Tags make it easier to:

- 📂 Group resources
- 👀 Improve visibility
- ⚙️ Manage related resources
- 🛠️ Operate on grouped resources

---

## 🎯 Basic Flow

**AWS Resources → Tags or Resource Groups → Group Related Resources → Use Systems Manager Features → Manage and Operate on Resources**

---

### 🧠 Key Idea

**AWS Systems Manager = Tools for managing and operating AWS instances**

**Documents = Used by Systems Manager features to manage instances**

**Maintenance Windows = Used to manage AWS instances**

**Resource Groups = Collections of AWS resources in the same Region**

**Tags = Help group and organize resources**

**Tag Editor = Helps perform bulk editing and tagging**

---

## 🧠 Analogy: Resource Groups as Rooms in a House

Managing **Resource Groups** is like organizing your home into different rooms, each with a specific purpose.

Imagine your house has:

- 🍳 A kitchen
- 🛋️ A living room
- 🛏️ Bedrooms

You keep related items together:

- 🍳 Cooking tools and food → Kitchen
- 📺 Entertainment devices → Living room
- 👤 Personal items → Bedrooms

This way, everything is grouped logically, making it easier to:

- 🔍 Find items
- 🛠️ Manage items
- 🧹 Clean up

Similarly, in cloud environments, **Resource Groups** let you organize related resources into logical containers.

These resources can include:

- 🖥️ Servers
- 🗄️ Databases
- 💾 Storage

Grouping related resources makes it easier to:

- 👀 Monitor resources
- ⚙️ Manage resources
- 🔄 Update resources
- 🗑️ Delete resources related to a specific project or function

Instead of searching for resources scattered everywhere, you can manage everything related to a specific group together—just like cleaning or renovating an entire room instead of searching throughout the house for individual items.

---

# 🖥️ AWS Systems Manager Managed Instances and Session Manager

## 🧩 Managed Instances

AWS Systems Manager requires the installation of the **SSM Agent** on instances in order to manage them as **managed instances**.

The SSM Agent is:

- ✅ Pre-installed on **Amazon Linux AMIs**
- ✅ Pre-installed on **AWS Windows AMIs**
- 🔧 Available for other platforms
- 🖥️ Available for **physical servers**
- 💻 Available for **virtual machines**

---

## 🔐 IAM Role for Managed Instances

Managed instances need an **IAM role** to interact with AWS Systems Manager.

AWS provides:

- 📋 **Predefined policies**
- ⚙️ Easier configuration of the required permissions

### 🎯 Basic Flow

**Managed Instance → SSM Agent → IAM Role → AWS Systems Manager**

---

## 🌐 Hybrid Environments

AWS Systems Manager can manage systems outside of EC2.

To register:

- 🖥️ Non-EC2 servers
- 💻 Virtual machines

You can create a **hybrid activation**.

This allows these systems to be registered and managed through Systems Manager.

---

## 🖥️ Fleet Manager

**Fleet Manager** provides visibility into managed instances.

It displays information such as:

- 🆔 **Instance ID**
- 💻 **Platform Type**
- 🖥️ **Operating System**

This provides visibility into the managed instances within the environment.

---

## 💻 Session Manager

**Session Manager** provides secure, interactive **browser-based shell access** to managed instances.

It does not require:

- 🚫 Open inbound ports
- 🚫 Additional client software

This allows users to securely connect to managed instances through Systems Manager.

---

## 🔐 Session Manager Security

Session Manager uses:

- 🔒 **TLS 1.2** for secure communication
- 🔑 **AWS Key Management Service (KMS) keys** for enhanced security

---

## 📝 Session Logging and Auditing

Session Manager provides:

- 📋 Full logging
- 🔍 Session auditing

Session outputs can be sent to:

- 🕵️ **AWS CloudTrail**
- 📊 **Amazon CloudWatch**
- 🪣 **Amazon S3**

Access control is managed through:

- 🔐 **AWS Identity and Access Management (IAM) policies**

---

## ⚖️ Key Benefits

- 🤖 Allows instances to be managed through Systems Manager using the SSM Agent.
- 🖥️ Supports Amazon Linux and AWS Windows AMIs.
- 💻 Supports other platforms, physical servers, and virtual machines.
- 🔐 Uses IAM roles for managed instances to interact with Systems Manager.
- 🌐 Supports hybrid environments through hybrid activation.
- 🖥️ Fleet Manager provides visibility into managed instances.
- 💻 Session Manager provides secure interactive browser shell access.
- 🚫 Session Manager does not require open inbound ports.
- 🚫 Session Manager does not require additional client software.
- 🔒 Uses TLS 1.2 for secure communication.
- 🔑 Supports KMS keys for enhanced security.
- 📝 Supports full session logging and auditing.
- 📊 Session outputs can be sent to CloudTrail, CloudWatch, or Amazon S3.
- 🔐 IAM policies control access to Session Manager.

### 🧠 Key Idea

**SSM Agent = Allows an instance to be managed by Systems Manager**

**Managed Instance = An instance registered for management through Systems Manager**

**IAM Role = Allows the managed instance to interact with Systems Manager**

**Hybrid Activation = Registers non-EC2 servers and virtual machines**

**Fleet Manager = Provides visibility into managed instances**

**Session Manager = Secure browser-based shell access without open inbound ports or additional client software**

**Session Logging = Sends session outputs to CloudTrail, CloudWatch, or Amazon S3**