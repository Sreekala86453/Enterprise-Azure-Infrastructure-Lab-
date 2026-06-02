# Architecture Overview

## Objective

This project simulates a multi-tier enterprise infrastructure environment deployed in Microsoft Azure. The lab was designed to demonstrate hands-on experience with identity management, networking, patch management, file services, web hosting, database administration, Linux integration, and backup operations.

---

## Architecture Diagram

![Architecture Diagram](azure_enterprise_architecture_diagram.png)

---

## Environment Information

| Component | Value |
|------------|---------|
| Platform | Microsoft Azure |
| Domain | Enterprise.local |
| Virtual Network | 192.168.10.0/24 |

---

## Infrastructure Components

| Server | VM Name | IP Address | Function |
|----------|-------------|--------------|------------|
| DC01 | VM-DC01 | 192.168.10.10 | Active Directory, DNS, Group Policy |
| SQL01 | VM-DBServer01 | 192.168.10.20 | SQL Server Express |
| FS01 | VM-FS01 | 192.168.10.30 | SMB File Services |
| MGMT01 | VM-MGMT01 | 192.168.10.40 | DHCP, WSUS |
| WEB01 | VM-WebS01 | 192.168.10.50 | IIS Web Server |
| BACKUP01 | VM-BackupServer | 192.168.10.60 | Windows Server Backup |
| LINUX01 | VM-LinuxServer | 192.168.10.70 | Ubuntu Server (Apache, MySQL, Samba, SSH) |
| ClientVM01 | Windows 11 Client | DHCP | End User Workstation |

---

## Network Design

All virtual machines are connected to the same Azure virtual network:

```text
192.168.10.0/24
```

The environment uses:

- Active Directory integrated DNS
- Centralized authentication
- Role-based access control
- Internal server-to-server communication
- Client access to shared resources and web services

---

## Service Relationships

### Identity Services
- DC01 provides Active Directory authentication
- DNS name resolution is managed through DC01

### Management Services
- MGMT01 provides DHCP and WSUS functionality
- Group Policy distributes WSUS configuration to clients

### Storage Services
- FS01 hosts departmental file shares
- Access controlled using Active Directory security groups and NTFS permissions

### Application Services
- WEB01 hosts an internal IIS website
- SQL01 provides database services

### Linux Services
- LINUX01 provides Apache, MySQL, Samba, and SSH services

### Backup Services
- BACKUP01 provides backup and recovery capabilities for Windows servers

---

## Skills Demonstrated

- Azure Infrastructure Deployment
- Active Directory Administration
- DNS & DHCP Configuration
- Group Policy Management
- WSUS Patch Management
- File Server Administration
- NTFS Permission Management
- IIS Web Hosting
- SQL Server Administration
- Linux System Administration
- Backup & Recovery Operations
