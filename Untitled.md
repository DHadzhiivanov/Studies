**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# 1. Introduction

This document records the validation and testing results for the IT infrastructure implemented for The Knowledge Hub library. Each section covers a specific component, describing what was tested, the expected outcome, the actual result, and evidence in the form of screenshots or recordings.

This document is a work in progress and will be expanded as additional components are implemented and tested.

---

# 2. Validation Status Overview

| Component | Task | Status |
| --------- | ---- | ------ |
| Domain Controller | Task 3 | Pass |
| File Server | Task 4 | Pass |
| Workstations & GPO | Task 6 | Pass |
| Network Foundation | Task 2 | Pass |
| Linux Monitoring Server | Task 4 | Pending |
| Web Server | Task 7 | Pending |
| External DNS Server | Task 8 | Pending |
| NAT & Security Hardening | Task 9 | Pending |
| Python Monitoring Script | Tasks 5, 10, 11 | Pending |

---

# 3. Domain Controller

## 3.1 Test Details

| Field      | Value                      |
| ---------- | -------------------------- |
| Hostname   | DC1                        |
| IP Address | 192.168.20.10              |
| VLAN       | VLAN 20 - Internal Servers |
| OS         | Windows Server 2022        |
| Domain     | knowledgeHub.local         |

## 3.2 OU Structure

**Test:** Verify that the OU structure reflects the organizational design.

**Expected:** OUs exist for Groups, Servers, and Users with IT, Management and Staff sub-OUs under Users.

**Result:** Pass

![[Pasted image 20260320215149.png]]

## 3.3 User Accounts

**Test:** Verify that all user accounts exist in the correct OUs.

**Expected:** All users created and placed in the correct department OU.

**Result:** Pass

| User | OU | Result |
| ---- | -- | ------ |
| K. Noorlander | IT | Pass |
| M. van Dijk | IT | Pass |
| T. Willems | IT | Pass |
| Y. Peters | IT | Pass |
| L. Jansen | Management | Pass |
| F. Bakker | Staff | Pass |
| S. Koenraadt | Staff | Pass |
| A. Vermeulen | Staff | Pass |
| P. Hendriks | Staff | Pass |
| I. Blom | Staff | Pass |

![[Pasted image 20260320215209.png]] ![[Pasted image 20260320215225.png]] ![[Pasted image 20260320215240.png]] 

## 3.4 Security Groups

**Test:** Verify that all security groups exist with correct scope and nesting follows the AGDLP model.

**Expected:** Global groups contain user accounts. Domain Local groups contain Global groups. Domain Local groups will be assigned permissions on the file server.

**Result:** Pass

| Group | Scope | Members |
| ----- | ----- | ------- |
| GG_IT | Global | K. Noorlander, M. van Dijk, T. Willems, Y. Peters |
| GG_Management | Global | L. Jansen |
| GG_Staff | Global | F. Bakker, S. Koenraadt, A. Vermeulen, P. Hendriks, I. Blom |
| DL_Staff_RW | Domain Local | GG_IT, GG_Management, GG_Staff |
| DL_Management_RW | Domain Local | GG_Management |
| DL_IT_RW | Domain Local | GG_IT |

![[Pasted image 20260320215315.png]]

---

# 4. File Server

## 4.1 Test Details

| Field      | Value                      |
| ---------- | -------------------------- |
| Hostname   | FILESERVER                 |
| IP Address | 192.168.20.20              |
| VLAN       | VLAN 20 - Internal Servers |
| OS         | Windows Server 2022        |
| Domain     | knowledgeHub.local         |

## 4.2 Domain Join

**Test:** Verify FILESERVER appears as a computer object in Active Directory.

**Expected:** FILESERVER visible in the Servers OU under KNOWLEDGEHUB.

**Result:** Pass

![[Pasted image 20260320215405.png]]

## 4.3 Share Configuration

**Test:** Verify that all shares exist with correct NTFS permissions assigned to the appropriate Domain Local groups.

**Expected:** Three shares exist - Staff, Management, IT - each accessible only by the correct groups.

**Result:** Pass

| Share | Path | Permission Group | Access Level |
| ----- | ---- | ---------------- | ------------ |
| Staff | C:\Shares\Staff | DL_Staff_RW | Modify |
| Management | C:\Shares\Management | DL_Management_RW | Modify |
| IT | C:\Shares\IT | DL_IT_RW | Full Control |

![[Pasted image 20260320215655.png]] ![[Pasted image 20260320215826.png]]

## 4.4 Access Testing

**Test:** Verify that users can access shares they are permitted to and are denied access to shares they are not.

**Expected:** Each user can only access shares relevant to their role. Unauthorized access attempts result in Access Denied.

**Result:** Pass

Access was validated through a recorded demonstration from the perspective of L. Jansen. The recording shows successful read/write access to the Staff and Management shares, and an Access Denied result when attempting to open the IT share.

[Click here for demo](https://youtu.be/AB708ZesDn8)

---

# 5. Workstations and Group Policy

## 5.1 Test Details

| Field | Value |
| ----- | ----- |
| Staff-PC1 | Windows 10, VLAN 10, domain joined |
| Staff-PC2 | Windows 10, VLAN 10, domain joined |
| GPO Name | KH-Workstation-Policy |
| Linked To | OU=Users, OU=KNOWLEDGEHUB |
| Applies To | GG_Staff, GG_Management |

## 5.2 RegEdit Disabled

**Test:** Attempt to open Registry Editor as a standard domain user.

**Expected:** Access is denied with a message stating registry editing has been disabled by the administrator.

**Result:** Pass

![[Pasted image 20260320193826.png]]

## 5.3 Automatic Updates

**Test:** Verify that the automatic updates policy is applied and configured to auto download and schedule installation.

**Expected:** GPO setting Configure Automatic Updates is enabled and set to option 4.

**Result:** Pass

![[Pasted image 20260320194120.png]]

## 5.4 Admin Account Exclusion

**Test:** Verify that the GPO does not apply to domain administrator accounts.

**Expected:** Security Filtering on the GPO only includes GG_Staff and GG_Management. Authenticated Users has Read permission but not Apply Group Policy.

**Result:** Pass

![[Pasted image 20260320194814.png]]

## 5.5 Drive Mappings

**Test:** Verify that each user automatically receives the correct drive letters at login based on their group membership.

**Expected:** Users only see drives relevant to their department. Drives are mapped automatically on login without manual configuration.

**Result:** Pass

| User | S: Staff | M: Management | I: IT |
| ---- | -------- | ------------- | ----- |
| P. Hendriks (GG_Staff) | Visible | Not visible | Not visible |
| L. Jansen (GG_Management) | Visible | Visible | Not visible |
| K. Noorlander (GG_IT) | Visible | Not visible | Visible |

![[Pasted image 20260320203841.png]]
*Drive map targeting configuration - only selected security groups see each drive.*

![[Pasted image 20260320204319.png]]
*P. Hendriks - Staff drive visible only.*

![[Pasted image 20260320205135.png]]
*L. Jansen - Staff and Management drives visible.*

---

# 6. Network Foundation

## 6.1 VLAN Configuration

**Test:** Verify that all VLANs are configured on the switch and pfSense with correct subnets and gateways.

**Expected:** Four VLANs active - Staff (10), Servers (20), Public (30), DMZ (40).

**Result:** Pass

| VLAN | Purpose | Network | Gateway |
| ---- | ------- | ------- | ------- |
| VLAN 10 | Staff Workstations | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 | Internal Servers | 192.168.20.0/24 | 192.168.20.1 |
| VLAN 30 | Public Computers | 192.168.30.0/24 | 192.168.30.1 |
| VLAN 40 | DMZ | 192.168.40.0/24 | 192.168.40.1 |

![[network-vlans.png]]

## 6.2 DHCP

**Test:** Verify that VLAN 10 and VLAN 30 clients receive IP addresses automatically from pfSense with the correct DNS server.

**Expected:** Clients receive an IP in the correct range with DNS pointing to 192.168.20.10.

**Result:** Pass

![[network-dhcp.png]]

## 6.3 Firewall Rules

**Test:** Verify that firewall rules are configured between VLANs according to the security design.

**Expected:** Staff can reach servers, public cannot reach servers or staff, DMZ is isolated from LAN.

**Result:** Pass

![[network-firewall-rules.png]]

---

# 7. Pending Validation

The following sections are placeholders for components not yet implemented. Each will be completed and filled in as implementation progresses.

---

## 7.1 Linux Monitoring Server

**Test:** Ubuntu VM joins knowledgeHub.local using realmd. An AD user authenticates successfully on the Linux machine.

**Expected:** Domain join succeeds, AD user login works.

**Result:** Pending

---

## 7.2 Web Server

**Test:** Access the web server from a client VM via HTTPS using the internal IP address.

**Expected:** Static HTML page loads, browser accepts self-signed certificate.

**Result:** Pending

---

## 7.3 External DNS Server

**Test:** Resolve library.knowledgehub.nl from a VM in the simulated internet network.

**Expected:** DNS query returns the correct public IP address of the web server.

**Result:** Pending

---

## 7.4 NAT and Security Hardening

**Test:** Access the web server from the internet-side VM using library.knowledgehub.nl over HTTPS.

**Expected:** Request is NAT'd through pfSense to the web server. Internal systems remain unreachable from the internet.

**Result:** Pending

---

## 7.5 Python Monitoring Script

**Test:** Run the monitoring script, collect metrics, store to SQLite database, retrieve by time range via CLI.

**Expected:** Script collects CPU, memory and disk metrics, stores with timestamps, retrieves and displays correctly.

**Result:** Pending