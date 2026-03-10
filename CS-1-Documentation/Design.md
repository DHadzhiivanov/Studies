
**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# Table of Contents

- [[#1. Introduction|1. Introduction]]
- [[#2. Design Goals|2. Design Goals]]
- [[#3. High-Level Network Architecture|3. High-Level Network Architecture]]
    - [[#3.1 Access Layer|3.1 Access Layer]]
    - [[#3.2 Edge Layer (Firewall / Routing)|3.2 Edge Layer (Firewall / Routing)]]
- [[#4. VLAN and IP Design|4. VLAN and IP Design]]
- [[#5. Core Infrastructure Services|5. Core Infrastructure Services]]
    - [[#5.1 Active Directory Domain Controller|5.1 Active Directory Domain Controller]]
    - [[#5.2 File Server|5.2 File Server]]
    - [[#5.3 Public Web Server|5.3 Public Web Server]]
- [[#6. Routing Design|6. Routing Design]]
- [[#7. Security Design|7. Security Design]]
    - [[#7.1 VLAN Segmentation|7.1 VLAN Segmentation]]
    - [[#7.2 DMZ Architecture|7.2 DMZ Architecture]]
    - [[#7.3 Firewall Rules|7.3 Firewall Rules]]
- [[#8. Switch Port Allocation|8. Switch Port Allocation]]
- [[#9. Firewall Policy Table|9. Firewall Policy Table]]
- [[#10. Network Diagram|10. Network Diagram]]
- [[#11. Conclusion|11. Conclusion]]

---

# 1. Introduction

This document describes the technical design of the IT infrastructure for _The Knowledge Hub_ library. The goal of the design is to create a secure, scalable, and manageable network environment that supports both staff operations and public access services.

The infrastructure focuses on network segmentation, centralized identity management, and controlled access to internal and public services. The design also introduces a demilitarized zone to safely host public-facing services without exposing internal resources.

---

# 2. Design Goals

The main design objectives for the infrastructure are:

• Provide logical separation between staff systems, servers, public computers, and public services

• Centralize user management through Active Directory
• Ensure secure communication between network segments
• Protect internal systems using firewall-based traffic filtering
• Provide reliable shared storage for staff
• Allow controlled internet access for public computers
• Maintain a simple and maintainable infrastructure design

---

# 3. High-Level Network Architecture

The infrastructure uses a **segmented network architecture** with a central firewall handling routing and security policies.

The main components of the network include:

• pfSense firewall/router
• Managed Layer 2 switch
• Virtualized servers providing infrastructure services
• Segmented networks for staff, servers, public users, and DMZ services

---

## 3.1 Access Layer

The access layer consists of a managed switch that connects all end devices and servers.

Since the switch operates on Layer 2, it is responsible for:

• Providing access ports for workstations and servers  
• Assigning devices to the correct VLAN  
• Forwarding VLAN traffic to the firewall using a trunk link

Ports on the switch are assigned to VLANs based on the type of device connected.

---

## 3.2 Core Layer (Firewall / Routing)

The pfSense firewall acts as the core device and central routing component.

Its responsibilities include:

• Inter-VLAN routing  
• Firewall traffic filtering  
• Controlling access between internal networks  
• Protecting the infrastructure from external threats  
• Isolating the DMZ from internal networks

All VLAN gateways are situated on pfSense.

---

# 4. VLAN and IP Design

The network is segmented into multiple VLANs to separate different types of systems and users.

| VLAN    | Purpose            | Network         | Gateway      |
| ------- | ------------------ | --------------- | ------------ |
| VLAN 10 | Staff Workstations | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 | Internal Servers   | 192.168.20.0/24 | 192.168.20.1 |
| VLAN 30 | Public Computers   | 192.168.30.0/24 | 192.168.30.1 |
| VLAN 40 | DMZ                | 192.168.40.0/24 | 192.168.40.1 |

Each VLAN is assigned a dedicated subnet to improve security.

---

# 5. Core Infrastructure Services

The infrastructure provides several centralized services hosted on virtual machines.

---

## 5.1 Active Directory Domain Controller

The Domain Controller provides centralized identity and authentication services.

**Server Details**

|Server|IP Address|VLAN|
|---|---|---|
|DC1|192.168.20.10|VLAN 20|

Functions include:

• User authentication  
• Group policy management  
• Centralized user administration

---

## 5.2 File Server

The file server provides shared storage for library staff.

**Server Details**

|Server|IP Address|VLAN|
|---|---|---|
|File Server|192.168.20.20|VLAN 20|

Functions include:

• Shared file storage  
• Role-based access control  
• Support for collaboration between staff members

---

## 5.3 Public Web Server

A web server is hosted in the DMZ to provide public services while maintaining separation from the internal network.

**Server Details**

| Server     | IP Address    | VLAN    |
| ---------- | ------------- | ------- |
| Web Server | 192.168.40.40 | VLAN 40 |

Hosting public services in the DMZ ensures that internal systems remain protected even if the public service is compromised.

---

# 6. Routing Design

Routing between network segments is performed by the pfSense firewall.

Each VLAN interface on pfSense acts as the default gateway for its respective subnet.

• VLAN 10 - 192.168.10.1
• VLAN 20 - 192.168.20.1
• VLAN 30 - 192.168.30.1
• VLAN 40 - 192.168.40.1

This approach allows the firewall to inspect and control all inter-network traffic.

---

# 7. Security Design

Security is implemented through multiple layers including network segmentation and firewall rules.

---

## 7.1 VLAN Segmentation

Network segmentation reduces the risk of unauthorized access between systems.

• Public computers cannot directly access internal servers
• Staff systems can access shared resources
• Public services are isolated in the DMZ

---

## 7.2 DMZ Architecture

The DMZ provides a dedicated network for public-facing services.

This ensures that:

• External users can access the web server
• Internal networks remain protected
• Firewall rules control traffic between the DMZ and internal networks

---

## 7.3 Firewall Rules

Firewall rules enforce security policies between networks.

Example policies include:

|Source|Destination|Action|
|---|---|---|
|Staff VLAN|Server VLAN|Allow|
|Public VLAN|Server VLAN|Deny|
|Public VLAN|Internet|Allow|
|Internet|DMZ Web Server|Allow (HTTP/HTTPS)|
|DMZ|Internal Networks|Deny|

---

# 8. Switch Port Allocation

The managed switch connects all infrastructure components and assigns devices to their respective VLANs. Port assignments are intentionally simplified in the simulation environment to reduce unnecessary complexity while still demonstrating the correct network design.

| Port   | Device                  | VLAN       | Purpose                                 |
| ------ | ----------------------- | ---------- | --------------------------------------- |
| Port 0 | Management VM           | Management | Switch management interface             |
| Port 1 | pfSense Firewall        | Trunk      | Carries VLAN 10, 20, 30, and 40 traffic |
| Port 2 | File Server             | VLAN 20    | Staff file storage                      |
| Port 3 | Domain Controller (DC1) | VLAN 20    | Active Directory services               |
| Port 4 | Web Server              | VLAN 40    | Public web service in DMZ               |
| Port 5 | Staff PC 1              | VLAN 10    | Staff workstation                       |
| Port 6 | Staff PC 2              | VLAN 10    | Staff workstation                       |
| Port 7 | Public PC 1             | VLAN 30    | Public library computer                 |
| Port 8 | Public PC 2             | VLAN 30    | Public library computer                 |
| Port 9 | pfSense Management VM   | VLAN 20    | Allows access to pfSense web interface  |

Although the real environment would contain more devices, the simulation environment uses fewer systems while maintaining the same network logic and security architecture.

---

# 9. Firewall Policy Table

The firewall is responsible for controlling communication between network segments. All traffic between VLANs is routed through the pfSense firewall where rules are applied to enforce security policies.

| Source Network                | Destination Network            | Service      | Action | Purpose                                          |
| ----------------------------- | ------------------------------ | ------------ | ------ | ------------------------------------------------ |
| Staff VLAN (192.168.10.0/24)  | Server VLAN (192.168.20.0/24)  | Any          | Allow  | Staff access to internal services                |
| Staff VLAN                    | WAN                            | Any          | Allow  | Normal internet access                           |
| Public VLAN (192.168.30.0/24) | WAN                            | Any          | Allow  | Public internet access                           |
| Public VLAN                   | Server VLAN                    | Any          | Deny   | Prevent public access to internal systems        |
| Public VLAN                   | Staff VLAN                     | Any          | Deny   | Prevent access to staff systems                  |
| WAN                           | DMZ Web Server (192.168.40.99) | HTTP / HTTPS | Allow  | Public website access                            |
| WAN                           | LAN                            | Any          | Deny   | Protect internal systems                         |
| DMZ                           | LAN                            | Any          | Deny   | Prevent compromised DMZ hosts from accessing LAN |

This firewall policy ensures that internal services remain protected while still allowing necessary communication between systems and external users.

---

# 10. Network Diagram

The network diagram illustrates the relationship between the router, switch, servers, and network segments.


![](Network%20Diagram.svg)

---

# 11. Conclusion

The proposed design provides a structured and secure infrastructure for _The Knowledge Hub_. Network segmentation, centralized services, and firewall-based routing ensure that staff systems, public computers, and public services remain isolated while still allowing communication where necessary.