# 📌 Decoupled & Event-Driven Architecture

## 🧠 Overview
- 🏗️ The lecture explains **decoupled** and **event-driven** architectures  
- 🔄 Both are contrasted with traditional **monolithic architectures**  
- 🎯 Focus on improving flexibility, resilience, and ease of change  

---

## 🧱 Monolithic Architecture
- 🔗 Components are **tightly coupled**
- ⚠️ Strong dependencies exist between components  
- 💥 Changes in one component can disrupt other services  
- 🎼 If one part fails or changes, the entire system can be affected  

---

## 🔓 Decoupled Architecture
- 🧩 Consists of **independent components**
- 🔌 Components communicate through **constant interfaces**
- 🚀 Enables faster and more efficient development  
- 🔄 Changes to one component do **not** affect others  
- 🌱 Promotes innovation and progress  
- 🛠️ The lecture mentions **Amazon SQS** as a service used in decoupled architectures  

---

## ⚡ Event-Driven Architecture

### 🔎 What It Is
- 🔗 Related to decoupled architecture  
- 🎯 Triggered by **events** within the infrastructure  
- 🔄 An event represents a **change of state**

### 📍 Examples of Events
- 📦 Resource status change  
- 🛒 Order placement  

---

## 🧩 Core Components of Event-Driven Architecture
- 🎤 **Producer** — Is the element within the infrastructure that will push an event to the event router.
- 🧭 **Event Router** — then prcoesses the event and takes the necessary action in pushing the outcome to the consumers.
- 👂 **Consumers** — executes the appropiate action as requested.

### 🔄 Role of the Event Router
- 🧠 Processes incoming events  
- 🔓 Decouples producers from consumers  
- ✅ Maintains the benefits of decoupled architecture  

### 🛠️ AWS Services Referenced
- 📢 **Amazon SNS**  
- 🌊 **Amazon Kinesis**  
- ⚡ **AWS Lambda**  

---

# 🧠 Analogy

## 🎼 Monolithic Architecture = Traditional Orchestra
- 🎶 Every musician follows the conductor’s every move  
- ⏱️ If the conductor changes tempo, everyone must adjust instantly  
- ❌ If one musician makes a mistake, it can disrupt the entire performance  

---

## 🎷 Decoupled Architecture = Jazz Festival
- 🎤 Multiple independent bands play on different stages  
- 🎵 Each band has its own style and tempo  
- 🔄 If one band changes its setlist or a musician leaves, others continue unaffected  
- 📅 Bands communicate only through a shared schedule (interface)  
- 🚫 They do not constantly check on each other  

---

## 🎧 Event-Driven Architecture = Dance Party
- 🎧 The DJ (event producer) plays a song (event)  
- 💃 People (consumers) start dancing when they hear it  
- 🧍 Each person decides how to react to the song  
- 🎶 The DJ does not need to know who is dancing or how  
- 🔓 The DJ simply plays the music and the crowd responds  

---

## 🎯 The Big Idea
- 🔓 Separation and independence increase flexibility  
- 🛡️ Systems become more resilient  
- 🔄 Easier to make changes without affecting the entire system  