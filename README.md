# Azure Active Directory Lab

## Project Overview

This hands-on Azure lab demonstrates how I deployed multiple Windows Server virtual machines, configured Active Directory Domain Services and DNS, created a Windows domain, and joined additional servers to that domain.

The goal of this project was to build practical experience with Azure administration, Windows Server, Active Directory, DNS, networking, and troubleshooting.

---

## Lab Environment

- Microsoft Azure
- Windows Server 2022
- 3 Azure Virtual Machines
- Azure Virtual Network (VNet)
- Azure Network Security Groups (NSGs)
- Active Directory Domain Services (AD DS)
- DNS
- Remote Desktop Protocol (RDP)
- PowerShell
- Windows Server Manager

### Domain

`lab.local`

### Server Roles

| Server | Role |
|---|---|
| VM1 | Domain Controller / DNS Server |
| VM2 | Domain-Joined Server |
| VM3 | Domain-Joined Server |

---

# Lab Architecture

All three virtual machines were deployed inside the same Azure Virtual Network.

VM1 was configured as the Domain Controller and DNS server.

VM2 and VM3 were configured to use VM1's private IP address as their DNS server before being joined to the `lab.local` domain.

```text
Microsoft Azure
      |
      |
Azure Virtual Network
      |
      |---------------------------
      |            |             |
     VM1          VM2           VM3
Domain Controller Server       Server
AD DS + DNS       |             |
      |            |             |
      |------------|-------------|
              lab.local
