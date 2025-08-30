# Active Directory Hybrid Environnement

Active directory on premise with all tiers deployment, and users synced to the cloud 

<h1> Full description and Components</h1>

## 1. Introduction

This project demonstrates the deployment of a Hybrid Active Directory environment, where an on-premises Active Directory (AD) domain is seamlessly integrated with Azure Active Directory (Azure AD) through Azure AD Connect.

The lab showcases several key capabilities, including:

Identity synchronization → ensuring users have a single identity across on-premises and cloud resources.

Active Directory Certificate Services (AD CS) → enabling secure authentication, certificates, and encryption.

Hybrid application publishing → providing secure access to internal applications from anywhere.

### Why This Matters

Modern enterprises often operate across both on-premises datacenters and cloud platforms. A hybrid AD environment provides:

Unified identity management → one set of credentials for both local and cloud resources.

Improved security → stronger authentication, conditional access, and reduced attack surface.

Scalability & flexibility → extend on-premises infrastructure to the cloud without disrupting existing services.

This lab serves as a practical simulation of how IT teams can design, implement, and manage hybrid identity infrastructures that meet real-world enterprise needs.


## 2- High-Level Architecture

The lab environment is structured into two main layers: the On-Premises Layer and the Cloud Layer.

### On-Premises Layer

This simulates a traditional enterprise datacenter, hosting the following components:

Domain Controller (DC) → Core of Active Directory for identity and authentication.

DNS/DHCP → Provides name resolution and IP address management for the local network.

Public Key Infrastructure (PKI) → Issues certificates for secure communication and authentication.

IIS Web Server → Hosts internal applications and services for testing hybrid publishing.

NDES (Network Device Enrollment Service) → Supports certificate enrollment for devices.

Client Machine → Represents end-users logging in, authenticating, and accessing services.

### Cloud Layer (Azure)

This layer extends identity and application access to the cloud:

Azure AD → Cloud-based directory for centralized identity management.

Azure AD Connect → Synchronizes on-premises users, groups, and credentials with Azure AD.

Azure Key Vault → Securely stores certificates, secrets, and encryption keys.

Azure AD Application Proxy → Publishes internal apps securely for external access.




<p align="center">

![image alt](https://github.com/kodjoballo/ActiveDirectory_HybridEnv/blob/main/hybrid_ad_architecture_modern.png?raw=true)

</p>

## 3. On-Premises Deployment

### 🖥️ Domain Controller (Windows Server 2022 DC)

Installed AD DS → Created forest root domain (yourdomain.local).

Configured Group Policy Objects (GPOs) for password policy, lockout policy.

Provides central authentication for users.

### 🌐 DNS & DHCP

DNS configured for internal resolution (yourdomain.local).

DHCP scope assigned to client PCs dynamically.

Demonstrate client joining the domain.

### 🔐 Public Key Infrastructure (PKI)

Offline Root CA (WS2019): Secure trust anchor, only issues to subordinate CA.

Enterprise CA (WS2022): Issues certs to users, computers, IIS web apps.

Used for SSL, smartcard logon, and securing RDP/IIS.

### 🌍 IIS Web Server

Hosts internal apps and Certificate Enrollment Web Service.

Later published securely using Azure AD App Proxy.

### 📡 NDES Server (WS2019)

Provides certificate enrollment for devices not domain-joined (e.g., routers, IoT).

### 💻 Client (Windows 11)

Domain-joined workstation used to log in with on-prem credentials.

Tests SSO and certificate-based access.
<h2> Key Benefits </h2>
Unified Identity: Single sign-on (SSO) experience for both on-premises and cloud resources.

Security: PKI-backed authentication, Conditional Access, and secure app publishing.

Scalability: Foundation for future cloud migrations and modern authentication scenarios.


## 4. Hybrid Identity Integration

### 🔄 Azure AD Connect

Installed on DC.

Configured in Password Hash Sync (PHS) mode (simplest for labs).

Synced: users, groups, and selected attributes.

Demonstrate:

Create a user in on-prem AD → syncs to Azure AD.

Show user logging into Microsoft 365 portal with the same password.


## 5. Azure Cloud Components


### ☁️ Azure AD

Receives synced accounts.

Conditional Access policies enforced (MFA, device compliance).

### 🔑 Azure Key Vault (Optional but nice)

Secure storage for certificates and secrets.

Example: store SSL cert from Enterprise CA.

### 🔒 Azure AD App Proxy

Publishes on-prem IIS web app.

Remote user logs into app.yourdomain.com via Azure SSO, without VPN.

## 6. Key Demonstrations for the Video

To keep the lab walkthrough concise but impactful, the video highlights four core demonstrations:

✅ Step 1: Domain Join Process

Show how a client machine is joined to the on-premises Active Directory domain.

Demonstrates centralized identity management and policy enforcement.

✅ Step 2: User Creation & Synchronization

Create a new user in the on-premises Active Directory.

Sync the account to Azure AD using Azure AD Connect.

Log in with the synchronized account to Microsoft 365 services (e.g., Outlook or Teams).

✅ Step 3: PKI Certificate Issuance

Demonstrate certificate issuance via the internal PKI/AD CS infrastructure.

Example: issuing a user authentication certificate or an IIS server certificate.

Highlights secure communication and authentication in a hybrid setup.

✅ Step 4: Application Proxy Publishing

Use Azure AD Application Proxy to publish the on-premises IIS web application.

Access the internal app securely from the internet with Azure AD authentication.

Demonstrates hybrid app publishing and secure remote access.



 ### [Video Walkthrough upcoming...]()
  

<h2>Description</h2>
Project consists of a simple PowerShell script that walks the user through "zeroing out" (wiping) any drives that are connected to the system. The utility allows you to select the target disk and choose the number of passes that are performed. The PowerShell script will configure a diskpart script file based on the user's selections and then launch Diskpart to perform the disk sanitization.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Hyper V</b>
- <b>PowerShell & cmd</b> 
- <b>Diskpart</b>
- <b>RDC Manager</b> 
- <b>Windows server manager and Features</b>
- <b>NTDSutil</b> 
- <b>etc...</b>


<h2>Environments Used </h2>

- <b>Windows Server 2022 Datacenter as Domain controller</b> 
- <b>Windows Server 2019 Datacenter as Offline rootCA</b> 
- <b>Windows server 2022 Datacenter as Enterprise CA</b> 
- <b>Windows Server 2019 Datacenter as Web Server</b> 
- <b>Windows Server 2019 Datacenter as NDES Server</b>
- <b>Windows 11 as Client </b> (24H2)
- <b>Kali Linux machine not in the same network </b>



## 8. Conclusion / Value Proposition

This lab demonstrates an enterprise-relevant hybrid identity management environment, integrating on-premises Active Directory with Azure Active Directory.

#### Key value highlights include:

Security → Leveraging PKI, certificate services, and modern authentication (MFA, conditional access).

Scalability → Supporting growth from local infrastructure to cloud-based services without disruption.

Modern Access → Enabling secure remote access through Azure AD Application Proxy and unified identities.

#### By implementing this hybrid model, organizations establish a strong foundation for:

Zero Trust security architecture.

Cloud migration strategies where on-premises and cloud services coexist seamlessly.

Future-proof IT operations that balance control, flexibility, and resilience.

This lab not only showcases technical integration but also reflects the strategic direction of enterprise IT: secure, scalable, and cloud-ready.

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
