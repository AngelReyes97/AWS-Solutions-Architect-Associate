# 📌 Decoupling Applications with Queuing Services (Part 1)

## 🧠 Overview
- 📬 **Amazon SQS (Simple Queue Service)** is a messaging queue system
- 🔓 Designed to help decouple applications
- 📈 Provides a reliable, scalable, and fully managed service
- 📩 Enables sending, storing, and receiving messages between software components
- 🛡️ Decoupling ensures each application component operates **independently**
- 🔗 Changes or failures in one component do **not** affect others
- ⚠️ In tightly coupled applications, failure in one layer can impact subsequent layers
- 💥 This can impair the entire application

---

## 🔄 Achieving Decoupling with Messaging

- 📩 Introduce a **messaging mechanism**
- 🔁 Messages are sent and received between different layers
- 🎯 The messaging model needs to be a 1 to 1 message passing
    - **1 message is generating by an existing layer**
    - **That message is put into a queue**
    - **That 1 message picked up by the next processing layer**
- ⏳ Enables **asynchronous communication**
- 🧩 Each layer operates independently while communicating through messages

---

## 📬 Amazon SQS (Simple Queue Service)

- 📮 Used to implement the messaging mechanism
- 📧 Acts like an **email system** for application layers
- 🗂️ Maintains message copies even if no consumers are available
- 🔓 Enables loose coupling between layers

---

## 🏗️ Architecture with SQS

- 📦 SQS queues are placed between application layers
- 🖥️ EC2 instances process messages from the queue
- 📈 EC2 instances can scale based on demand
- 🔁 If an EC2 instance fails to process a message:
  - The message remains in the queue  
  - Another instance can process it  

---

## 👥 Producers and Consumers

- ✉️ **Producers** — Applications that send messages to a queue  
- 📥 **Consumers** — Applications that pick up messages from a queue  

---

## 🔒 Visibility Timeout / Flow

- ✉️ An application (**producer**) sends a message to an SQS queue  
- 👂 A consumer application listens (polls) the queue for new messages  

### 🔄 When a Consumer Receives a Message

- 🔐 The message is locked using a **visibility timeout**
- 👻 The message becomes **invisible** to other polling consumers
- 🚫 Prevents multiple consumers from processing the same message simultaneously  

---

### 🔁 If Processing Fails

- ❌ If the message is not processed successfully:
  - 👁️ It becomes visible again after the visibility timeout expires  
  - 🔄 It can be picked up and reprocessed by another consumer  

---

### ⏱️ Visibility Timeout Settings

- 🕒 Default visibility timeout: **30 seconds**
- ⚙️ Adjustable up to **12 hours**
- 🎯 Ensures messages are processed within the required time before deletion  
- 🗑️ Once processed successfully, the message is deleted from the queue    

---

## ⏲️ Delay Queues

- ⏳ Allow delaying message delivery
- 🕒 Default delay: **0 seconds**
- ⏱️ Maximum delay: **15 minutes**

---

## ⚠️ Long Processing Considerations

- ⏳ If processing time exceeds **12 hours**
- 🔄 Alternatives such as **Step Functions** should be considered  

---

## 🧠 Analogy: Decoupling with Queuing Services

### 🍽️ Busy Restaurant Kitchen

Imagine a busy restaurant kitchen:

- 🧾 Customers place orders  
- 🧑‍🍳 Waiters write each order on a slip  
- 📋 The slips are placed in a queue on the kitchen counter  
- 🔥 Chefs pick up orders from the queue and prepare the food  

---

### 🔄 How It Works

- 🤝 Waiters and chefs do **not** need to talk directly  
- ⏳ If a chef is busy, orders wait in the queue  
- 🚀 If a chef finishes early, they grab the next order  
- 🔁 Everyone works independently at their own pace  

---

### 🧩 How This Relates to Queuing Services

- 👥 Different parts of your system act like waiters and chefs  
- 📩 They communicate through a **queue**
- ⏱️ Each part works at its own speed  
- 🛡️ The overall system becomes more reliable  
- 🔓 The architecture becomes more flexible

---

# 📌 Decoupling Applications with Queuing Services (Part 2)

## ⏳ Short Polling

- 🔄 Default method for listening to messages in a queue  
- 📩 The consumer sends a **ReceiveMessage** request  
- ⚡ SQS responds immediately — even if no messages are available  

### ⚙️ When It Occurs
- WaitTimeSeconds parameter is set to **0**
- Or the queue’s **ReceiveMessageWaitTimeSeconds** attribute is **0** (default)

### ⚠️ Considerations
- 📭 Can result in many empty responses  
- 🚫 May lead to an **OverLimit** error  
- 📦 OverLimit occurs when the maximum number of in-flight messages is reached  
  - Standard queue limit: **120,000 in-flight messages**

---

## ⏱️ Long Polling

- ⌛ The consumer waits for messages to become available  
- 🕒 Wait time must be **greater than 0** (up to **20 seconds**)  
- 📬 **SQS responds when**:
  - A message becomes available  
  - The wait time expires  

### ⚙️ When It Occurs
- WaitTimeSeconds parameter is set to a value **greater than 0**
- Or the queue’s **ReceiveMessageWaitTimeSeconds** attribute is set to a value **greater than 0**

### ✅ Benefits
- 📉 Reduces empty responses  
- 🚫 Helps avoid OverLimit errors  
- 📊 Reduces the number of API requests  
- 💰 More efficient message retrieval  

---

## 📦 Message Size Limits

- 📏 Default maximum message size in SQS: **256 KB**
- 📚 The **Amazon SQS Extended Client Library for Java** allows processing messages up to **2 GB**
- 🗄️ Larger messages are stored using **Amazon S3**

---

## 📨 Standard vs FIFO Queues

### 📬 Standard Queues

- 🔁 Ensure **at-least-once delivery**
- 🚫 Do **not** guarantee message order
- 📦 Support up to **120,000 in-flight messages**
- 🚀 Higher throughput compared to FIFO

---

### 📑 FIFO Queues

- 🔢 Guarantee **message order**
- ✅ Ensure **exactly-once delivery**
- 📉 Lower in-flight message limit: **20,000**
- 🐢 Perform slower than standard queues

---

## 🪦 Dead Letter Queues (DLQs)

- ⚠️ Handle unprocessed messages caused by:
  - Application failure  
  - Message corruption  
- 📥 Capture messages that exceed the **maximum receive count**
- 🔄 Prevent problematic messages from blocking processing

### ⚠️ Important Considerations

- 🔢 Dead letter queues can disrupt FIFO order  
- 📊 Must monitor DLQs regularly  
- 📢 SNS can be used for notifications  
- 🤖 Can support automated remediation workflows  

---

## 🔁 Redrive Policy

- 🧭 Defines how messages move between:
  - Source queue  
  - Dead letter queue  
- 🔎 Critical to examine DLQ messages promptly  
- 🛠️ Ensures proper message handling and system reliability