
**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# Table of Contents

- [[#1. Introduction|1. Introduction]]
- [[#2. Network Infrastructure|2. Network Infrastructure]]
    - [[#2.1 Topology|2.1 Topology]]
    - [[#2.2 VLAN Configuration|2.2 VLAN Configuration]]
    - [[#2.3 DHCP|2.3 DHCP]]
    - [[#2.4 Firewall Rules|2.4 Firewall Rules]]
- [[#3. Domain Controller|3. Domain Controller]]
    - [[#3.1 Installation|3.1 Installation]]
    - [[#3.2 OU Structure|3.2 OU Structure]]
    - [[#3.3 User Accounts|3.3 User Accounts]]
    - [[#3.4 Security Groups|3.4 Security Groups]]
- [[#4. File Server|4. File Server]]
    - [[#4.1 Installation|4.1 Installation]]
    - [[#4.2 Domain Join|4.2 Domain Join]]
    - [[#4.3 File Server Role|4.3 File Server Role]]
    - [[#4.4 Share Configuration|4.4 Share Configuration]]
- [[#5. Workstations and Group Policy|5. Workstations and Group Policy]]
    - [[#5.1 Workstation Setup|5.1 Workstation Setup]]
    - [[#5.2 Group Policy|5.2 Group Policy]]
    - [[#5.3 RegEdit Disabled|5.3 RegEdit Disabled]]
    - [[#5.4 Automatic Updates|5.4 Automatic Updates]]
    - [[#5.5 Drive Mappings|5.5 Drive Mappings]]
- [[#6. Pending Implementation|6. Pending Implementation]]

---

# 1. Introduction

This document describes the technical implementation of the IT infrastructure for The Knowledge Hub library. It covers what was installed, how it was configured, and the reasoning behind the choices made during implementation.

This is a work in progress. Sections will be added as each component is implemented.

---

# 2. Network Infrastructure

The network was the first thing set up since everything else depends on it. Without working VLANs and routing, nothing can communicate and there is no point setting up servers.

## 2.1 Topology

The network follows a two-layer design with a pfSense firewall handling all routing and a managed switch handling VLAN separation at the access layer. All inter-VLAN traffic goes through pfSense which means firewall rules can be applied to everything.

A router-on-a-stick approach was used, meaning pfSense handles routing for all VLANs through a single trunk link from the switch. This is not the most performant setup but it is appropriate for the scale of this project and it keeps things simple to manage.

![[gns3TopologyLatest 1.png]]

## 2.2 VLAN Configuration

Four VLANs were created to separate different types of systems and users from each other.

| VLAN | Purpose | Network | Gateway |
| ---- | ------- | ------- | ------- |
| VLAN 10 | Staff Workstations | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 | Internal Servers | 192.168.20.0/24 | 192.168.20.1 |
| VLAN 30 | Public Computers | 192.168.30.0/24 | 192.168.30.1 |
| VLAN 40 | DMZ | 192.168.40.0/24 | 192.168.40.1 |

The server VLAN (20) is kept separate from the staff VLAN (10) so that workstations cannot directly reach servers without going through the firewall first. Public computers (30) are completely isolated from both. The DMZ (40) is for the web server which needs to be reachable from the internet without exposing anything internal.

![[Pasted image 20260320222546.png]]
*VLANS on Switch*
## 2.3 DHCP

DHCP was configured on pfSense for VLAN 10 and VLAN 30. Staff workstations and public computers get their IP configuration automatically. The DNS server option was set to 192.168.20.10 so clients use the internal DC for name resolution.

VLAN 20 and VLAN 40 use static IPs only since servers should never change address.

![[Pasted image 20260320222822.png]]
*DHCP on VLAN 10*

DHCP also auto-assigns the default gateways.

## 2.4 Firewall Rules

Firewall rules were set up on pfSense to enforce the security design. The main idea is that traffic is denied by default and only explicitly allowed where needed.

| Source | Destination | Action | Reason |
| ------ | ----------- | ------ | ------ |
| Staff VLAN (10) | Server VLAN (20) | Allow | Staff need access to DC and file server |
| Staff VLAN (10) | WAN | Allow | Normal internet access |
| Public VLAN (30) | WAN | Allow | Public internet access |
| Public VLAN (30) | Server VLAN (20) | Deny | Public should not reach internal servers |
| Public VLAN (30) | Staff VLAN (10) | Deny | Public should not reach staff systems |
| WAN | DMZ Web Server | Allow HTTP/HTTPS | Public website needs to be reachable |
| WAN | LAN | Deny | Protect everything internal |
| DMZ | LAN | Deny | If the web server gets compromised it cannot reach internal systems |

![[Pasted image 20260320221057.png]]
![[Pasted image 20260320221119.png]]
![[Pasted image 20260320221141.png]]
![[Pasted image 20260320221201.png]]
![[Pasted image 20260320221213.png]]


---

# 3. Domain Controller

## 3.1 Installation

A Windows Server 2016 VM was set up with a static IP of 192.168.20.10 in VLAN 20. The Active Directory Domain Services role was installed through Server Manager and the server was promoted to Domain Controller for the domain knowledgehub.local.

DNS was installed automatically alongside AD DS. The DC serves as the internal DNS server for the domain. All clients on the network use 192.168.20.10 as their DNS server.

| Field      | Value              |
| ---------- | ------------------ |
| Hostname   | DC1                |
| IP Address | 192.168.20.10      |
| VLAN       | VLAN 20            |
| Domain     | knowledgehub.local |
| Roles      | AD DS, DNS         |

## 3.2 OU Structure

The OU structure was designed to reflect how the organization is actually structured. The idea is that different departments can have different policies applied to them and users are easy to find and manage.

```
knowledgehub.local
- KNOWLEDGEHUB
	- Groups
	- Servers
	- Users
		- IT
		- Management
		- Staff
```

The Groups OU holds all security groups. The Servers OU is where server computer objects live. Users are split by department under the Users OU.

![[Pasted image 20260320215149.png]]

## 3.3 User Accounts

User accounts were created in their respective department OUs. All accounts were set to require a password change on first login.

| User | OU | Role |
| ---- | -- | ---- |
| K. Noorlander | IT | IT Administrator |
| M. van Dijk | IT | IT Administrator |
| T. Willems | IT | IT Administrator |
| Y. Peters | IT | IT Administrator |
| L. Jansen | Management | Library Manager |
| F. Bakker | Staff | Operations Staff |
| S. Koenraadt | Staff | Operations Staff |
| A. Vermeulen | Staff | Operations Staff |
| P. Hendriks | Staff | Operations Staff |
| I. Blom | Staff | Operations Staff |

![[Pasted image 20260320215209.png]]![[Pasted image 20260320215225.png]]![[Pasted image 20260320215240.png]] 
## 3.4 Security Groups

Security groups were designed following the AGDLP model. The idea behind this is to keep permission management centralized. Instead of assigning permissions directly to users on every resource, you assign them to groups once and just manage who is in which group.

Global groups represent roles in the organization. Domain Local groups represent access to specific resources. Global groups are nested into Domain Local groups.

**Global groups:**

| Group | Members |
| ----- | ------- |
| GG_IT | K. Noorlander, M. van Dijk, T. Willems, Y. Peters |
| GG_Management | L. Jansen |
| GG_Staff | F. Bakker, S. Koenraadt, A. Vermeulen, P. Hendriks, I. Blom |

**Domain Local groups:**

| Group | Contains | Purpose |
| ----- | -------- | ------- |
| DL_Staff_RW | GG_IT, GG_Management, GG_Staff | Read/Write on Staff share |
| DL_Management_RW | GG_Management | Read/Write on Management share |
| DL_IT_RW | GG_IT | Full Control on IT share |

This means that if a new IT employee joins, you add them to GG_IT and they automatically get access to everything GG_IT has access to. Nothing on the file server needs to be touched.

![[Pasted image 20260320223643.png]]

---

# 4. File Server

## 4.1 Installation

A second Windows Server 2022 VM was set up as the dedicated file server. Before joining the domain, the static IP and DNS were configured first. The DNS server was pointed at the DC (192.168.20.10) because the domain join requires the machine to resolve knowledgeHub.local.

| Field | Value |
| ----- | ----- |
| Hostname | FILESERVER |
| IP Address | 192.168.20.20 |
| VLAN | VLAN 20 |
| Domain | knowledgeHub.local |
| Role | File Server, File Server Resource Manager |

## 4.2 Domain Join

The file server was joined to knowledgeHub.local through System Properties. After rebooting, the computer object appeared in Active Directory under the Computers container and was then moved to the Servers OU under KNOWLEDGEHUB.

The domain join was verified by logging in with a domain administrator account after the reboot.

![[fileserver-aduc.png]]

## 4.3 File Server Role

The File Server and File Server Resource Manager roles were installed through Server Manager. No reboot was required after installation.

## 4.4 Share Configuration

Three shared folders were created, one for each department. The folders were created under C:\Shares\ and shared using the New Share Wizard in Server Manager.

The permission model uses two layers:

- Share permissions are set to allow the relevant Domain Local group Full Control. This is intentional because share permissions are a blunt tool and the real access control happens at the NTFS level.
- NTFS permissions define the actual access level per group. Inheritance was disabled on each folder and permissions were assigned explicitly.

| Share | Path | NTFS Group | NTFS Permission |
| ----- | ---- | ---------- | --------------- |
| Staff | C:\Shares\Staff | DL_Staff_RW | Modify |
| Management | C:\Shares\Management | DL_Management_RW | Modify |
| IT | C:\Shares\IT | DL_IT_RW | Full Control |

IT gets Full Control on their share because they are administrators and may need to manage files and permissions within it. Staff and Management get Modify which means they can read, write, edit and delete files but cannot change permissions or take ownership.

![[Pasted image 20260320223705.png]]

Access-based enumeration was enabled on all shares so users only see shares they actually have access to. This avoids confusion and keeps the environment clean.

---

# 5. Workstations and Group Policy

## 5.1 Workstation Setup

Two Windows 10 VMs were set up in VLAN 10 as staff workstations. Both received their IP configuration automatically from DHCP with DNS pointing to the DC. Both were joined to knowledgeHub.local through System Properties.

| Machine | VLAN | Domain |
| ------- | ---- | ------ |
| Staff-PC1 | VLAN 10 | knowledgeHub.local |
| Staff-PC2 | VLAN 10 | knowledgeHub.local |

## 5.2 Group Policy

A single GPO called KH-Workstation-Policy was created and linked to the Users OU under KNOWLEDGEHUB. The naming follows a simple convention where KH identifies the organization, Workstation identifies what it targets, and Policy clarifies what it is.

The GPO was scoped to GG_Staff and GG_Management through Security Filtering. Authenticated Users was kept in the Delegation tab with Read permission only, without Apply Group Policy. This is required for the GPO to process correctly while still excluding admin accounts from the policy settings.

![[Pasted image 20260320223828.png]]

## 5.3 RegEdit Disabled

Registry editing was disabled for all users the GPO applies to. This prevents staff from making changes to the system registry which could cause instability or be used to bypass other security settings.

Setting: User Configuration, Policies, Administrative Templates, System, Prevent access to registry editing tools, Enabled.

![[Pasted image 20260320193826.png]]

## 5.4 Automatic Updates

Automatic updates were configured to download and install automatically without user intervention. This ensures workstations stay patched without relying on staff to manually update.

Setting: Computer Configuration, Policies, Administrative Templates, Windows Components, Windows Update, Configure Automatic Updates, Enabled, Option 4.

![[Pasted image 20260320194120.png]]

## 5.5 Drive Mappings

Drive mappings were configured through GPO Preferences so that users automatically get the correct network drives mapped at login. Item-level targeting was used on each drive map so that users only see drives relevant to their department.

| Drive | Share | Visible To |
| ----- | ----- | ---------- |
| S: | \\fileserver\Staff | GG_Staff, GG_Management, GG_IT |
| M: | \\fileserver\Management | GG_Management |
| I: | \\fileserver\IT | GG_IT |

Without item-level targeting every user would see all three drive letters but get Access Denied on the ones they cannot open. That is confusing and looks unprofessional. Targeting fixes this by hiding irrelevant drives entirely.

![[Pasted image 20260320203841.png]]
*Drive map targeting configuration for the Staff share.*

![[Pasted image 20260320204319.png]]
*P. Hendriks logged in, Staff drive visible only.*

![[Pasted image 20260320205135.png]]
*L. Jansen logged in, Staff and Management drives visible.*

---

# 6. Pending Implementation

The following components are yet to be implemented. This section will be expanded as each task is completed.

- Linux Monitoring Server (Task 4)
- Web Server in DMZ (Task 7)
- External DNS Server (Task 8)
- NAT configuration and security hardening (Task 9)
- Python monitoring scripts (Tasks 5, 10, 11)
- ITIL process design (Task 12)