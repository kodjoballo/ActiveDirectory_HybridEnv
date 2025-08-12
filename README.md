# Active Directory Hybrid Environnement

Active directory on premise with all tiers deployment, and users synced to the cloud 

<h1> Full description and Components</h1>

This deployment simulates a hybrid identity infrastructure integrating an on-premises Active Directory domain with Azure Active Directory via Azure AD Connect for seamless identity synchronization.

<p align="center">

![image alt](https://github.com/kodjoballo/ActiveDirectory_HybridEnv/blob/main/hybrid_ad_architecture_modern.png?raw=true)

</p>

<h2>On-Premises Components</h2>
<h3>Domain Controller (DC) </h3>

Hosts the Active Directory Domain Services (AD DS) forest root domain.

Provides centralized authentication and policy management.

<h3> Client Workstation </h3>

Domain-joined Windows client for user login, GPO testing, and application access.

<h3> DNS & DHCP Server </h3>

DNS: Resolves domain names for internal services and supports AD DS replication.

DHCP: Dynamically assigns IP addresses and network configurations to clients.

<h3> Public Key Infrastructure (PKI) </h3>

Offline Root Certificate Authority: Air-gapped, root trust anchor for issuing subordinate CA certificates.

Enterprise Subordinate CA: Issues user, computer, and service certificates within the domain.

<h3> IIS Web Server </h3>

Hosts internal web applications and certificate enrollment web portals.

<h3> NDES (Network Device Enrollment Service) </h3>

Enables certificate enrollment for network devices and non-domain-joined endpoints.

<h2> Hybrid Identity Integration </h2>
<h3> Azure AD Connect </h3>

Configured in Password Hash Synchronization (PHS) or Pass-through Authentication (PTA) mode.

Synchronizes on-premises AD users, groups, and selected attributes to Azure AD.

Supports hybrid single sign-on for Microsoft 365 and Azure-based applications.

<h2>Azure Cloud Components</h2>

<h3> Azure Active Directory </h3>

Receives synchronized user accounts for cloud authentication.

Enforces Conditional Access Policies for enhanced security.

<h3> Azure Key Vault (Value-Added) </h3>

Centralized secrets, certificates, and key management for hybrid workloads.

<h3> Azure AD Application Proxy (Value-Added) </h3>

Securely publishes on-premises IIS-hosted applications to remote users without exposing them directly to the internet.

<h2> Key Benefits </h2>
Unified Identity: Single sign-on (SSO) experience for both on-premises and cloud resources.

Security: PKI-backed authentication, Conditional Access, and secure app publishing.

Scalability: Foundation for future cloud migrations and modern authentication scenarios.

 ### [Video Walkthrough](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
Project consists of a simple PowerShell script that walks the user through "zeroing out" (wiping) any drives that are connected to the system. The utility allows you to select the target disk and choose the number of passes that are performed. The PowerShell script will configure a diskpart script file based on the user's selections and then launch Diskpart to perform the disk sanitization.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Hyper V/b>
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



<h2>Program walk-throughnot :</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
