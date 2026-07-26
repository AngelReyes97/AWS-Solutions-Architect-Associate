# 🛡️ Architecture Basics Overview  

## 🧩 Definition
**Architecture basics** focus on technology stacks and design patterns relevant to building **multi-tier solutions** for associate certification.  

Key architecture approaches include:
- 🏗️ **LAMP Stack**
- 🏗️ **MEAN Stack**
- ☁️ **Serverless Architecture**
- 🧩 **Microservices Architecture**
- 🏢 **Multi-tier Architecture**

---

## ⚙️ Technology Stack Overview  

### 🐧 LAMP Stack
The **LAMP stack** consists of:

- 🐧 **Linux**
- 🌐 **Apache**
- 🗄️ **MySQL**
- 🐘 **PHP**

It is commonly used for building **web services**.

---

### 🟨 MEAN Stack
The **MEAN stack** includes:

- 🍃 **MongoDB**
- 🌐 **ExpressJS**
- 🅰️ **AngularJS**
- 🟩 **NodeJS**

These components are based on **JavaScript frameworks**.

---

## ☁️ Serverless Architecture  
**Serverless architecture** uses:

- 🌐 **Amazon API Gateway**
- ⚡ **AWS Lambda**

These services replace the **logic tier** in traditional multi-tier designs.

---

## 🧩 Microservices Architecture  
**Microservices architecture** consists of:

- 🔗 Decoupled components.
- 🚀 Independently deployed services.

It is often used when:

- 🔄 Refactoring **monolithic applications**.
- 🧩 Breaking applications into smaller, independent components.

---

## 🏢 Multi-tier Architecture  
**Multi-tier architecture** separates application services into different tiers:

1. 🎨 **Presentation Tier**
   - Handles the user interface layer.

2. ⚙️ **Logic Tier**
   - Handles application processing and business logic.

3. 🗄️ **Data Tier**
   - Handles data storage and management.

---

## ⚙️ Multi-tier Architecture Considerations  
- 📌 There is **no fixed number of tiers** required in an architecture design.
- 🛠️ The number of tiers depends on **application requirements**.
- 📈 Each tier can be managed and scaled independently.
- 🌍 Multi-tier architectures can be distributed across multiple **Availability Zones** for:
  - High availability.
  - Scalability.
  - Resilience.

---

## 🌎 Availability Zones  
**Availability Zones** are distinct data centers located in different geographical locations.  

They improve the resilience of multi-tier designs by providing:

- 🛡️ Higher availability.
- 📈 Better scalability.
- 🔄 Improved fault tolerance.

---

## ⚖️ Key Benefits  
- 🏗️ Provides structured approaches for designing application architectures.  
- 📈 Enables independent scaling and management of application components.  
- ☁️ Supports modern architectures such as serverless and microservices.  
- 🛡️ Improves application resilience by distributing resources across multiple Availability Zones.  
- 🔄 Allows applications to evolve by separating components and refactoring monolithic designs.

---

## 🧠 Analogy: Architecture Basics as a House Blueprint  

Imagine you are **building a house**. Before construction begins, an **architect creates a blueprint** that shows how everything will fit together, including:

- 🏠 Where the rooms are located.
- 🔌 How plumbing and electricity will run.
- 🧱 What materials will be used.

This blueprint ensures the house is:
- 🛡️ Sturdy.
- ⚙️ Functional.
- 👨‍👩‍👧 Designed to meet the needs of future residents.

Similarly, **architecture basics in technology** involve creating a **blueprint for applications and systems**.

- 🏠 In a **multi-tier architecture**, the system is separated into different **rooms or layers**:
  - 🛋️ **Presentation Tier** → Like the living room, where users interact with the system.
  - 🍳 **Logic Tier** → Like the kitchen, where processing and operations take place.
  - 🏚️ **Data Tier** → Like the basement, where information is stored.

- 🧩 Just like each room in a house has a specific purpose, each architecture tier has a specialized role.
- 📈 Separating these components makes the system more:
  - Organized.
  - Scalable.
  - Easier to maintain.

---

# 🛡️ Multi-Tier Architecture Overview  

## 🧩 Definition
**Multi-tier architecture** is a design approach that separates application services into different layers, allowing each layer to operate and scale independently.  

The main benefit of multi-tier architecture is the **independence of each layer**, providing greater flexibility, control, and scalability.  

---

## 🧠 Analogy: Multi-Tier Architecture as a Cake Design  

Imagine different types of cakes:

- 🎂 **Single-tier architecture** is like a **birthday cake** where all services (**icing colors**) are placed on a single layer.  
  - ✅ Simple design.
  - ⚠️ Less flexible because everything exists together on one layer.

- 🍰 **Multi-tier architecture** is like a **wedding cake** with separate layers for each service.  
  - Each layer has its own purpose.
  - Layers can be managed and adjusted independently.
  - Provides more flexibility and scalability.

- 🏗️ Similar to a wedding cake, multi-tier architecture separates application components into different layers, allowing specific layers to be scaled or controlled without affecting others.

---

## ⚙️ Features and Use Cases  

### 📈 Independent Scaling and Control
- 🧩 Each layer operates independently.
- ⚡ Allows specific layers to be scaled based on demand.
- 🎯 Provides greater control over individual services.

### ☁️ Cloud Environment Support
- 🌍 Multi-tier architecture is well-suited for cloud environments.
- 🚀 Allows services to run on scalable cloud infrastructure.

### 🏢 Three-Tier Architecture
A common implementation of multi-tier architecture consists of:

1. 🎨 **Presentation Tier**
   - Handles user interaction.

2. ⚙️ **Logic Tier**
   - Handles application processing.

3. 🗄️ **Data Tier**
   - Handles data storage and management.

---

## 🧩 Architecture Components  

1. **Presentation Tier**  
   - The layer responsible for user interaction.

2. **Logic Tier**  
   - The layer responsible for processing application operations.

3. **Data Tier**  
   - The layer responsible for storing and managing data.

---

## 🛠️ Implementation Options  
Services within each tier can run using different technologies, including:

- 🖥️ **Amazon EC2 instances**
- ⚡ **Serverless functions in AWS**

---

## ⚖️ Key Benefits  
- 📈 Enables independent scaling of application layers.  
- 🛠️ Provides greater flexibility and control over individual services.  
- ☁️ Works effectively with scalable cloud infrastructure.  
- 🛡️ Prevents one overwhelmed layer from affecting other layers.  
- ⚡ Allows resources to be adjusted independently based on demand. 

---

# 🛡️ Single-Tier vs Multi-Tier Architecture Overview  

## 🧩 Definition
**Single-tier architecture** involves running all application services on a **single machine or instance**.  

It is suitable for:
- 🛠️ Simple services.
- 🧪 Development environments.
- 🧪 Testing environments.
- 📱 Small applications that do not require scaling.

**Multi-tier architecture** separates application services into **decoupled tiers**, allowing each tier to scale and operate independently.

---

## 🧠 Analogy: Single-Tier vs Multi-Tier Architecture as a Workspace  

Imagine a small business office:

- 🏢 **Single-tier architecture** is like having every employee and department working in **one room**.
  - ✅ Simple to set up.
  - ⚠️ If the room becomes crowded or unavailable, everyone is affected.
  - 📈 Expanding usually means moving to a larger room.

- 🏬 **Multi-tier architecture** is like having separate departments in different rooms.
  - Each department has its own space and responsibilities.
  - 📈 Additional resources can be added to specific departments when needed.
  - 🛡️ If one department becomes busy, it does not prevent others from operating.

---

## ⚙️ Single-Tier Architecture Features  

### 🖥️ Scaling Approach
- 📈 Scaling typically requires **vertical scaling**.
- ⬆️ Vertical scaling means upgrading to a **larger machine** or instance.

### 🌍 AWS Resilience Options
Single-tier architecture can be made more resilient by using:

- 🌎 Multiple **Availability Zones**.
- ⚡ **Auto Scaling Groups** in AWS.

### ⚠️ Limitations
The main drawback of single-tier architecture is the lack of **decoupling**.

This results in:
- 📉 Limited ability to scale services independently.
- 🛡️ Increased availability risks if the server fails.

---

## 🏢 Multi-Tier Architecture Features  

### 🔗 Decoupled Tiers
- 🧩 Services are separated into independent tiers.
- 📈 Each tier can scale based on demand.

### ☁️ Cloud Environment Support
- 🌍 Multi-tier architecture is beneficial in cloud environments such as **AWS**.
- ⚡ Allows resources to be adjusted based on application requirements.

### 📊 Scaling Examples
Specific tiers can be scaled depending on workload, such as:

- 👥 Handling large numbers of user requests.
- 🧠 Processing intensive tasks.

---

## ⚖️ Key Benefits  

### 🖥️ Single-Tier Architecture
- ✅ Simple design for small applications.
- 🛠️ Useful for development and testing environments.
- 🌱 Suitable when scaling requirements are minimal.

### 🏢 Multi-Tier Architecture
- 📈 Enables independent scaling of application components.
- 🛡️ Improves high availability and fault tolerance.
- ☁️ Works well with cloud environments like AWS.
- ⚡ Allows specific tiers to scale based on demand.
- 🔄 Prevents one overloaded service from impacting other tiers.

---

## 🧠 Analogy: Single-Tier Architecture as a Single-Layer Cake  

Imagine **single-tier architecture** as baking a **single-layer cake**.  

- 🍰 All the ingredients—**flour, sugar, eggs, and icing**—are mixed and baked together in one pan.  
- 🧁 Everything you need is contained within that one cake layer.  
- 💻 Similarly, in **single-tier architecture**, all parts of an application:
  - 🎨 User interface.
  - ⚙️ Business logic.
  - 🗄️ Data storage.
  
  run together on **one machine**.  

- ⚡ This makes it simple and quick to set up, just like baking one cake layer is easier than creating a multi-layer cake.  
- ⚠️ However, if you need more cake or need to fix a problem, you must deal with the **entire cake at once** because everything is combined together. 

---

# 🛡️ Multi-Tier VPC Architecture Design Overview  

## 🧩 Definition
A **multi-tier architecture design** for web services focuses on using **AWS services** to create a structured application environment.  

A common design separates application components into different layers:
- 🎨 **Presentation Layer**
- ⚙️ **Logic Layer**
- 🗄️ **Database Layer**

These layers can be distributed across multiple **Availability Zones** to provide redundancy and improve resilience.

---

## 🧠 Analogy: Multi-Tier VPC Architecture as a Secure Building  

Imagine a **large secure building** with different floors, where each floor has a specific purpose.

- 🚪 The **Internet Gateway** is like the main doorway that allows people to enter and leave the building.
- 🛡️ Because the doorway provides access, security measures are needed to control who can enter.
- 🏢 The **public subnet** is like the lobby where visitors can enter and interact.
- 🔒 The **private subnets** are like restricted floors where sensitive operations and storage take place.
- 🛡️ **Security groups** act like security guards protecting individual rooms.
- 🧱 **Network ACLs** act like building-wide security rules protecting entire floors.
- 🗺️ **Routing tables** control how traffic moves between different areas of the building.

Similarly, a multi-tier VPC design separates application components while controlling access and traffic flow securely.

---

## ⚙️ VPC Design Patterns  
AWS VPC designs can follow four basic patterns, including:

- 🌐 Single public subnet designs.
- 🔀 Combinations of public and private subnets.

---

## 🏢 Three-Tier VPC Architecture  

A three-tier VPC design separates application layers into different subnet types:

### 🌐 Public Subnets
- Used for the **presentation layer**.
- Connected to an **Internet Gateway**.

### 🔒 Private Subnets
Used for:
- ⚙️ **Logic layer**.
- 🗄️ **Database layer**.

The design emphasizes:
- 🌍 Redundancy through multiple **Availability Zones**.
- 🛡️ Separation between public-facing and private components.

---

## 🌐 Subnet Types  

### 🌍 Public Subnet
- Contains access through an **Internet Gateway**.
- Allows communication with the internet.

### 🔒 Private Subnet
- Does not have access through an **Internet Gateway**.
- Used for internal application components.

---

## 🚪 Internet Gateway  
An **Internet Gateway** acts as an access point between the VPC and the internet.

- 🚪 Functions like a doorway into the VPC.
- 🛡️ Requires security controls to manage access.

---

## 🔐 Security Controls  

### 🛡️ Security Groups
- Control access at the **instance level**.
- Manage traffic permissions for individual resources.

### 🧱 Network Access Control Lists (ACLs)
- Provide protection at the **subnet level**.
- Control traffic entering and leaving subnets.

---

## 🛣️ Routing Configuration  
- 🗺️ Private subnets require **independent routing tables**.
- 🔄 Routing tables manage how traffic flows within the VPC.
- ⚙️ Proper routing configuration ensures traffic reaches the correct destinations.

---

## ⚖️ Key Benefits  
- 🏗️ Provides organized separation between application layers.  
- 🌍 Improves redundancy through multiple Availability Zones.  
- 🔒 Enhances security by separating public and private resources.  
- 🛡️ Provides multiple layers of protection using security groups and network ACLs.  
- 🛣️ Enables controlled traffic flow through routing table configuration.