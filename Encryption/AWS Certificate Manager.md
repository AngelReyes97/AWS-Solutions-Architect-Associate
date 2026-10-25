# 🔐 What is AWS Certificate Manager (ACM)?

## 🧩 Definition

**Digital Certificates** establish trust in online communications by validating public keys used for secure communication and digital signature verification.

They support:

- 🔒 **Secure Connections:** Enable secure communication between systems.
- 👤 **Authentication:** Help verify the identity of a party.
- ✍️ **Non-Repudiation:** Support proof of who performed a digitally signed action.
- 🛡️ **Integrity Checks:** Help detect unauthorized changes to data.
- 🔐 **Encryption:** Support secure communications using cryptographic keys.

**AWS Certificate Manager (ACM)** simplifies the provisioning, management, and renewal of digital certificates used with AWS services and applications.

---

## 🏛️ 1. Certificate Authorities (CAs)

A **Certificate Authority (CA)** is an entity that issues digital certificates to establish trust in public keys.

There are two main types of CAs:

### 1. 🌐 Public Certificate Authorities

**Public CAs** issue certificates that are trusted by most operating systems.

They are commonly used for public-facing services, such as websites.

#### 📋 Certificate Issuance Process

1. 🔑 Generate a public-private key pair.
2. 📝 Create a **Certificate Signing Request (CSR)**.
3. 🌐 Validate ownership of the domain.
4. 📜 Obtain the certificate from the public CA.

#### 🔑 Key Characteristics

- 🌐 Trusted by most operating systems.
- 🖥️ Used for public-facing websites and services.
- 💰 Typically charge a fee for certificate issuance.

### 2. 🏢 Private Certificate Authorities

**Private CAs** issue certificates for internal organizational use.

#### 🔑 Key Characteristics

- 🏢 Used within an organization.
- ⚙️ Require manual configuration for trust by importing the CA's root certificate into the operating system.
- 🛡️ Organizations manage their own CA infrastructure.
- 💾 Organizations are responsible for security and backups.
- 📋 Organizations manage Certificate Revocation Lists (CRLs).
- 🆓 Certificates issued by private CAs are free, but are not automatically trusted by external users or services.

---

## ⚖️ 2. Public CA vs. Private CA

| Feature | Public CA | Private CA |
|---|---|---|
| **Primary Use** | Public-facing services | Internal organizational services |
| **Trust** | Trusted by most operating systems | Requires manual trust configuration |
| **Infrastructure Management** | Provided by the CA | Managed by the organization or its provider |
| **Certificate Cost** | Typically charges a fee | Certificates are free to issue |
| **CRL Management** | Managed through the CA's processes | Organization manages CRLs |
| **External Trust** | Generally trusted by external users and systems | Not automatically trusted externally |

---

## ⚠️ 3. Challenges with Digital Certificates

Managing certificates can create operational overhead for organizations.

### Common Challenges

- 📝 **Certificate Requests:** Managing certificate requests and issuance.
- 🔄 **Renewals:** Renewing certificates before they expire.
- ♻️ **Replacement:** Replacing expiring certificates.
- 💰 **Costs:** Paying for public CA certificates.
- 🛡️ **CA Security:** Securing private CA infrastructure.
- 💾 **Backups:** Maintaining backups for CA infrastructure.
- 📋 **CRL Management:** Maintaining Certificate Revocation Lists.

**Key Concern:** Expired certificates can cause service disruptions if they are not renewed or replaced in time.

---

## ☁️ 4. AWS Certificate Manager (ACM)

**AWS Certificate Manager (ACM)** simplifies certificate management by automating certificate provisioning, deployment, and renewal for supported use cases.

### 🔑 Key Features

- 🔒 **Free Public Certificates:** Provides free SSL/TLS certificates from a trusted public CA for use with supported AWS services.
- 🏢 **Private CA Support:** Allows users to set up and manage private CAs.
- ⚙️ **Infrastructure Management:** AWS handles infrastructure management for ACM Private CA, including high availability, backups, and day-to-day operations.
- 🔑 **Key Pair Generation:** Automates key pair generation.
- 📝 **CSR Creation:** Automates Certificate Signing Request creation.
- 🔄 **Automatic Renewal:** Renews eligible certificates to help prevent service disruptions caused by expiration.

### 🌐 Supported AWS Service Integrations

ACM provides certificates for supported AWS services, including:

- ⚖️ **Elastic Load Balancing**
- 🌍 **Amazon CloudFront**
- 🔗 **Amazon API Gateway**

---

## 🔄 5. How ACM Simplifies Certificate Management

ACM reduces the manual effort required to manage digital certificates.

### 📋 Management Process

1. 🔒 **Request a Certificate:** Request a public or private certificate.
2. 🔑 **Automate Key Management Tasks:** ACM automates key pair generation and CSR creation where applicable.
3. 🌐 **Validate the Certificate Request:** Complete the required validation process.
4. ☁️ **Deploy the Certificate:** Use the certificate with a supported AWS service.
5. 🔄 **Renew the Certificate:** ACM automates renewal for eligible certificates.

### 🎯 Main Benefits

- ⏱️ Reduces manual certificate management.
- 🔄 Helps prevent expiration-related service disruptions.
- 🛡️ Reduces operational overhead.
- 🔗 Simplifies certificate use with supported AWS services.
- 🏢 Supports both public and private certificate management.

---

## ⚖️ 6. ACM Public Certificates vs. Private CAs

| Feature | ACM Public Certificates | ACM Private CA |
|---|---|---|
| **Purpose** | Secure supported public-facing services | Issue certificates for internal organizational use |
| **Trust** | Issued by a trusted public CA | Requires appropriate trust configuration |
| **Cost** | Free for supported ACM public certificates | Private CA infrastructure and usage may incur charges |
| **Infrastructure Management** | ACM manages certificate provisioning and eligible renewals | AWS manages the underlying private CA infrastructure |
| **Common Use** | Websites and public-facing AWS services | Internal systems and applications |

---

## ⚖️ Key Benefits

- 🔒 Provides free SSL/TLS public certificates for supported AWS services.
- 🔄 Automates renewal of eligible certificates.
- 🔑 Automates key pair generation and CSR creation where applicable.
- 🏢 Supports private certificate authorities.
- 🛡️ Reduces the operational burden of managing CA infrastructure.
- 💾 AWS handles infrastructure management, high availability, and backups for ACM Private CA.
- ☁️ Integrates with services such as Elastic Load Balancing, CloudFront, and API Gateway.

---

## 🎯 Key Takeaway

**AWS Certificate Manager (ACM) = Simplified Provisioning, Management, and Renewal of Digital Certificates**

Remember these key points:

- 🏛️ **Public CA:** Issues certificates generally trusted by operating systems and commonly used for public-facing services.
- 🏢 **Private CA:** Issues certificates for internal use and requires appropriate trust configuration.
- ⚠️ **Certificate Challenges:** Include requests, renewals, expiration, costs, CA security, backups, and CRL management.
- 🔒 **ACM Public Certificates:** Free SSL/TLS certificates for supported AWS services.
- 🛡️ **ACM Private CA:** Allows organizations to manage private certificate issuance while AWS handles the underlying infrastructure.
- 🔄 **Automatic Renewal:** Helps prevent service disruptions caused by expired certificates.
- ☁️ **AWS Integration:** Supports services such as Elastic Load Balancing, Amazon CloudFront, and API Gateway.

---

# 🔐 AWS Certificate Manager (ACM) Overview

## 🧩 Definition

**AWS Certificate Manager (ACM)** is a regional AWS service used to request and manage digital certificates that secure AWS services and applications.

Certificates must generally be requested in the AWS Region where they will be used.

### 🌎 Regional Considerations

- 🌐 **Regional Service:** Certificates are requested in the Region where the supported AWS service uses them.
- ☁️ **Amazon CloudFront Exception:** CloudFront certificates must be requested in the **North Virginia (`us-east-1`)** Region.

---

## 📝 1. Requesting a Public Certificate

To request a public certificate, use the AWS Certificate Manager console.

### 📋 Request Process

1. ☁️ Open the **AWS Certificate Manager** console.
2. 📝 Select **Request a certificate**.
3. 🔐 Choose between a public certificate and a private certificate.
   - The private certificate option is available only if a private certificate authority has been created.
4. 🌐 Enter the fully qualified domain names (FQDNs) to protect, such as `www.example.com`.
5. ✅ Select a domain validation method:
   - **DNS validation**
   - **Email validation**

---

## 🌐 2. Domain Validation Methods

ACM requires domain validation to verify that the requester controls the domain.

### 1. 🌐 DNS Validation

DNS validation verifies domain ownership using a DNS record.

#### 📋 Process

1. 📝 ACM provides a CNAME record for each domain in the certificate request.
2. 🌐 Add the CNAME record to the domain's DNS zone.
3. 🔍 ACM checks the DNS record to validate domain ownership.
4. ✅ After successful validation, the certificate can be issued.

#### 🔑 Key Notes

- 🌐 A CNAME record must be added for each domain listed in the request.
- ☁️ If using Amazon Route 53 with the appropriate permissions, ACM can automatically create the required CNAME records.
- ⚙️ DNS validation can be automated through Route 53.

### 2. 📧 Email Validation

Email validation verifies domain ownership through emails sent to registered domain contacts.

#### 📋 Process

1. 📧 ACM sends validation emails to eligible domain contacts listed in the WHOIS database.
2. 👤 The domain contacts receive the validation request.
3. ✅ Respond to one of the validation emails within **72 hours** to validate the domain.
4. 🔐 After successful validation, ACM can issue the certificate.

#### 🔑 Key Notes

- 📧 Emails are sent to registered contacts, including the registrant, technical, and administrative contacts.
- ⏳ The validation email must be answered within 72 hours.
- 👤 Email validation requires a manual response from a domain contact.

---

## ⚖️ 3. DNS Validation vs. Email Validation

| Feature | DNS Validation | Email Validation |
|---|---|---|
| **Validation Method** | Add a CNAME record to DNS | Respond to a validation email |
| **Automation** | Can be automated using Route 53 with appropriate permissions | Requires a manual response |
| **Validation Location** | Domain's DNS zone | Registered domain contacts |
| **Time Limit** | No 72-hour email response requirement | Respond within 72 hours |
| **Main Requirement** | Ability to create the required DNS record | Access to a valid domain validation email |

---

## 🔒 4. Certificate Issuance

After successful domain validation, ACM issues the public certificate.

### 📋 Process

1. 🌐 Request a public certificate.
2. ✅ Complete DNS or email validation.
3. 🔐 ACM issues the certificate after successful validation.
4. ☁️ Use the issued certificate with a supported AWS service.

---

## ⚖️ 5. Using an ACM Certificate with an Application Load Balancer

An issued ACM certificate can be configured on an Application Load Balancer (ALB) to secure incoming HTTPS connections.

### 📋 Configuration Steps

1. ☁️ Open the **EC2 dashboard**.
2. ⚖️ Select the **Application Load Balancer**.
3. 🎧 Add a secure listener:
   - Select the **HTTPS** protocol.
   - Specify the HTTPS listener port.
   - Select the target group.
   - Choose the issued ACM certificate from the certificate dropdown menu.
4. 🔒 Optionally remove the HTTP listener to enforce HTTPS traffic.

### 🔄 Traffic Flow

**Client → HTTPS Listener (ALB + ACM Certificate) → Target Group → Application**

---

## ⚠️ 6. Key Notes

- 🌎 **Regional Service:** ACM certificates must be requested in the Region where they will be used.
- ☁️ **CloudFront Exception:** Request CloudFront certificates in `us-east-1` (North Virginia).
- 🌐 **DNS Validation:** Requires a CNAME record and can be automated using Route 53 with appropriate permissions.
- 📧 **Email Validation:** Requires a domain contact to respond within 72 hours.
- 🔐 **Certificate Issuance:** ACM issues the certificate after successful domain validation.
- ⚖️ **ALB Integration:** An ACM certificate can be selected when configuring an HTTPS listener.

---

## 🎯 Key Takeaway

**AWS Certificate Manager = Request, Validate, Issue, and Use Digital Certificates to Secure AWS Services**

Remember these key points:

- 📝 **Request:** Enter the fully qualified domain names to protect.
- 🌐 **DNS Validation:** Add CNAME records or allow Route 53 to create them with appropriate permissions.
- 📧 **Email Validation:** Respond to a validation email within 72 hours.
- 🔐 **Issuance:** ACM issues the certificate after successful validation.
- ⚖️ **Application Load Balancer:** Configure an HTTPS listener and select the ACM certificate.
- 🌎 **Regional Requirement:** Request certificates in the Region where they will be used.
- ☁️ **CloudFront:** Certificates must be requested in `us-east-1`.