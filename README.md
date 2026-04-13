

# 🏢 Hybrid Active Directory Lab – Enterprise Identity & Security Architecture

<p align="center">

![image alt](https://github.com/kodjoballo/ActiveDirectory_HybridEnv/blob/main/hybrid_ad_architecture_modern.png?raw=true)

</p>


## 📌 Overview

This project demonstrates the design and implementation of a **Hybrid Active Directory environment**, integrating on-premises infrastructure with Microsoft Azure.

The lab simulates a real enterprise setup where identity, security, and application access are managed across both local and cloud environments.

Key focus areas include:

* Hybrid identity synchronization (On-Prem AD ↔ Azure AD)
* Enterprise security with Public Key Infrastructure (PKI)
* Secure application publishing
* Centralized user and access management

---

## 🧠 Why This Matters

Modern organizations operate in hybrid environments combining on-premises systems and cloud platforms.

This architecture enables:

* **Unified Identity Management** → Single sign-on across all systems
* **Enhanced Security** → Certificates, MFA, Conditional Access
* **Scalability** → Seamless extension to cloud services
* **Secure Remote Access** → Without traditional VPN dependency

---

## 🏗️ Architecture Overview

The environment is divided into two main layers:

### 🖥️ On-Premises Infrastructure

* Domain Controller (Windows Server 2022)
* DNS & DHCP services
* Public Key Infrastructure (Offline Root CA + Enterprise CA)
* IIS Web Server (internal applications)
* NDES Server (device certificate enrollment)
* Windows 11 Client machine

---

### ☁️ Cloud Infrastructure (Azure)

* Azure Active Directory (Azure AD)
* Azure AD Connect (identity synchronization)
* Azure AD Application Proxy (secure remote access)
* Azure Key Vault (certificate & secret storage)

---

## ⚙️ Core Implementations

### 👥 Identity & Access Management

* Active Directory domain setup (yourdomain.local)
* User and group management
* Group Policy configuration (security & compliance)
* Centralized authentication system

---

### 🔄 Hybrid Identity (Azure AD Connect)

* Configured Password Hash Synchronization (PHS)
* Synced users and groups from on-prem to Azure AD
* Demonstrated seamless login across environments

---

### 🔐 Public Key Infrastructure (PKI & AD CS)

* Deployed Offline Root CA and Enterprise CA
* Issued certificates to users, computers, and services
* Implemented certificate-based authentication scenarios

This reflects enterprise-grade security practices for:

* Secure communication (SSL)
* User authentication
* System trust and encryption

---

### 🌍 Application Publishing (Azure AD App Proxy)

* Published internal IIS web application securely
* Enabled remote access via Azure authentication
* Eliminated need for VPN access

---

## 🧪 Key Demonstrations

This lab includes real-world IT scenarios:

* User creation in on-prem AD → synchronized to Azure AD
* Login to Microsoft 365 with synchronized credentials
* Certificate issuance and validation
* Secure access to internal applications via Azure App Proxy

---

## 📸 Screenshots

*(Add your screenshots here)*

Suggested:

* Active Directory Users & Computers
* Certificate Authority configuration
* Azure AD Connect sync
* Azure portal (users / login)
* App Proxy access

---

## 🎥 Video Demonstration

Full walkthrough of the lab:

👉 (Insert your video link here)

---

## 🛠️ Technologies Used

* Windows Server 2022 / 2019
* Active Directory Domain Services (AD DS)
* Active Directory Certificate Services (AD CS)
* Azure Active Directory
* Azure AD Connect
* IIS Web Server
* PowerShell
* Hyper-V

---

## 🧠 Key Takeaways

* Designed and implemented hybrid identity infrastructure
* Integrated on-premises and cloud authentication systems
* Applied enterprise-level security using PKI and certificates
* Enabled secure remote access to internal resources
* Demonstrated real-world IT support and system administration scenarios

---

## 🚀 About Me

I am an IT Support & Systems Engineer specializing in:

* Active Directory & Windows Server environments
* Hybrid identity (Azure AD)
* Automation (Python & PowerShell)
* Troubleshooting and system optimization

I focus on building structured, secure, and scalable IT environments.

---

## 📫 Contact

* GitHub: [https://github.com/kodjoballo](https://github.com/kodjoballo)
* Upwork: [(https://www.upwork.com/freelancers/~014627f395c6a1484e?mp_source=share)]

---

