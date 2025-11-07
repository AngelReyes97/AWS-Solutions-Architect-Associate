# 📝 AWS Networking Concepts – SAA Exam Summary  

This summary covers the **key networking topics** you need to know for the **AWS Solutions Architect Associate (SAA) exam**.  

---

## 🔹 Virtual Private Cloud (VPC)  

- **VPCs** are isolated virtual networks in AWS.  
- Understand the difference between **public** and **private subnets**.  
- Know **NACLs** (subnet-level, stateless firewalls) vs **Security Groups** (instance-level, stateful firewalls).  

---

## 🔹 Internet and NAT Gateways  

- **Internet Gateway (IGW):** Allows communication between **public subnets** and the internet.  
- **NAT Gateway:** Enables **private subnets** to access the internet securely without exposing instances.  

---

## 🔹 Connectivity Options  

- **VPN Gateway:** Secure, encrypted connection from on-premises to AWS over the internet.  
- **AWS Direct Connect:** Dedicated, private network connection to AWS for **low latency and high bandwidth**.  
- Know **differences and use cases** for VPN vs Direct Connect.  

---

## 🔹 VPC Endpoints  

- Enable **private access** to AWS services **without using the internet**.  
- **Interface Endpoints:** ENIs inside a subnet for AWS PrivateLink services.  
- **Gateway Endpoints:** Route traffic to S3 or DynamoDB without ENIs; added to route tables.  

---

## 🔹 Networking Components  

- **Elastic Network Interfaces (ENIs):** Virtual network cards for EC2 instances.  
- **Elastic IPs (EIPs):** Static public IPv4 addresses for EC2 instances.  
- **Enhanced Networking Adapters (ENAs):** High-performance network interfaces for EC2, supporting high throughput.  

---

## 🔹 AWS Global Accelerator  

- Improves **network performance and availability** for end users.  
- Uses **static IPs** and **optimized routing** across AWS global network.  

---

## 🔹 Route 53  

- **Scalable DNS service** for domain name management.  
- Supports **various routing policies**: simple, weighted, failover, latency-based, geolocation, geo-proximity, and multi-value answer.  
- **Traffic Flow** and **Application Recovery Controller** provide advanced routing and failover management.  

---

## 🔹 Amazon CloudFront  

- **Content Delivery Network (CDN)** to cache content closer to users.  
- Reduces **latency** for static and dynamic content.  
- Integrates with **S3, ALB, and Lambda** for fast and secure content delivery.  

---

## 🏁 Exam Focus Tips  

- Be familiar with **VPC design**: public vs private subnets, NACLs vs Security Groups.  
- Understand **internet connectivity** methods: IGW, NAT, VPN, Direct Connect.  
- Know how **VPC endpoints** work and when to use **interface vs gateway endpoints**.  
- Be able to explain **Route 53 routing policies** and **Traffic Flow basics**.  
- Understand **CloudFront caching strategies** and **Global Accelerator routing benefits**.  

---

💡 **Tip:** AWS networking questions often test **connectivity scenarios, security layers, and routing decisions** — focus on **how traffic flows** and **which service to use in each case**.  