
**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# Table of Contents

- [[#1. Introduction|1. Introduction]]
- [[#2. Functional Requirements and Corresponding IT Solutions|2. Functional Requirements and Corresponding IT Solutions]]
    - [[#2.1 REQ-S2P1-01 – Centralized User and Resource Management|2.1 REQ-S2P1-01 – Centralized User and Resource Management]]
        - [[#2.1.1 Requirement Description|2.1.1 Requirement Description]]
        - [[#2.1.2 Implementation|2.1.2 Implementation]]
        - [[#2.1.3 Corresponding Tasks|2.1.3 Corresponding Tasks]]
    - [[#2.2 REQ-S2P1-02 – Structured and Segmented Network|2.2 REQ-S2P1-02 – Structured and Segmented Network]]
        - [[#2.2.1 Requirement Description|2.2.1 Requirement Description]]
        - [[#2.2.2 Implementation|2.2.2 Implementation]]
        - [[#2.2.3 Corresponding Tasks|2.2.3 Corresponding Tasks]]
    - [[#2.3 REQ-S2P1-03 – Secure Collaborative Storage|2.3 REQ-S2P1-03 – Secure Collaborative Storage]]
        - [[#2.3.1 Requirement Description|2.3.1 Requirement Description]]
        - [[#2.3.2 Implementation|2.3.2 Implementation]]
        - [[#2.3.3 Corresponding Tasks|2.3.3 Corresponding Tasks]]
    - [[#2.4 REQ-S2P1-04 – Protected Public Online Presence|2.4 REQ-S2P1-04 – Protected Public Online Presence]]
        - [[#2.4.1 Requirement Description|2.4.1 Requirement Description]]
        - [[#2.4.2 Implementation|2.4.2 Implementation]]
        - [[#2.4.3 Corresponding Tasks|2.4.3 Corresponding Tasks]]
    - [[#2.5 REQ-S2P1-05 – Controlled Network Access at Boundaries|2.5 REQ-S2P1-05 – Controlled Network Access at Boundaries]]
        - [[#2.5.1 Requirement Description|2.5.1 Requirement Description]]
        - [[#2.5.2 Implementation|2.5.2 Implementation]]
        - [[#2.5.3 Corresponding Tasks|2.5.3 Corresponding Tasks]]
    - [[#2.6 REQ-S2P1-06 – Virtual Infrastructure Deployment|2.6 REQ-S2P1-06 – Virtual Infrastructure Deployment]]
        - [[#2.6.1 Requirement Description|2.6.1 Requirement Description]]
        - [[#2.6.2 Implementation|2.6.2 Implementation]]
        - [[#2.6.3 Corresponding Tasks|2.6.3 Corresponding Tasks]]
    - [[#2.7 REQ-S2P1-07 – Proactive System and Service Monitoring|2.7 REQ-S2P1-07 – Proactive System and Service Monitoring]]
        - [[#2.7.1 Requirement Description|2.7.1 Requirement Description]]
        - [[#2.7.2 Implementation|2.7.2 Implementation]]
        - [[#2.7.3 Corresponding Tasks|2.7.3 Corresponding Tasks]]
    - [[#2.8 REQ-S2P1-08 – Automated Task Execution|2.8 REQ-S2P1-08 – Automated Task Execution]]
        - [[#2.8.1 Requirement Description|2.8.1 Requirement Description]]
        - [[#2.8.2 Implementation|2.8.2 Implementation]]
        - [[#2.8.3 Corresponding Tasks|2.8.3 Corresponding Tasks]]
    - [[#2.9 REQ-S2P1-09 – Defined Management Processes|2.9 REQ-S2P1-09 – Defined Management Processes]]
        - [[#2.9.1Requirement Description|2.9.1Requirement Description]]
        - [[#2.9.2 Implementation|2.9.2 Implementation]]
        - [[#2.9.3 Corresponding Tasks|2.9.3 Corresponding Tasks]]
    - [[#2.10 REQ-S2P1-10 – Standardized Workstation Management|2.10 REQ-S2P1-10 – Standardized Workstation Management]]
        - [[#2.10.1 Requirement Description|2.10.1 Requirement Description]]
        - [[#2.10.2 Implementation|2.10.2 Implementation]]
        - [[#2.10.3 Corresponding Tasks|2.10.3 Corresponding Tasks]]
- [[#3. Conclusion|3. Conclusion]]

---

# 1. Introduction

This document describes the functional requirements of the IT infrastructure for *The Knowledge Hub* library and outlines the technical solutions used to fulfill them. Each requirement is linked to the technical implementation tasks performed during the project.

---

# 2. Functional Requirements and Corresponding IT Solutions

## 2.1 REQ-S2P1-01 – Centralized User and Resource Management

### 2.1.1 Requirement Description

A central directory service must be implemented to manage user accounts, authentication, and access to internal systems and services.

### 2.1.2 Implementation

- Deployment of a **Windows Server Domain Controller**
- Installation and configuration of **Active Directory Domain Services (AD DS)**
- Centralized authentication and authorization for users and systems
- Role-based access control using **Organizational Units (OUs)** and **security groups**

### 2.1.3 Corresponding Tasks

- Install Windows Server
- Configure Active Directory Domain Services
- Create domain structure and Organizational Units
- Create and manage user accounts

---

## 2.2 REQ-S2P1-02 – Structured and Segmented Network

### 2.2.1 Requirement Description

The internal network must be logically segmented into separate zones to improve organization, security, and manageability. Devices in the user workstation network must receive automatic network configuration.

### 2.2.2 Implementation

- Network segmentation using **VLANs**
- Separate network zones for:
    - Staff workstations
    - Servers
    - Public access computers
    - Public-facing services (DMZ)
- Automatic network configuration using **DHCP**

### 2.2.3 Corresponding Tasks

- Design network topology
- Configure VLAN segmentation on switches
- Configure routing between networks
- Configure DHCP for client networks

---

## 2.3 REQ-S2P1-03 – Secure Collaborative Storage

### 2.3.1 Requirement Description

Staff members must have access to a centralized and secure location where documents can be stored and shared. Access permissions should be based on organizational roles.

### 2.3.2 Implementation

- Deployment of a **central file server**
- Creation of **network shares**
- Access control using **Active Directory groups and permissions**

### 2.3.3 Corresponding Tasks

- Install and configure file server
- Join file server to the domain
- Configure SMB file shares
- Apply role-based permissions to shared folders

---

## 2.4 REQ-S2P1-04 – Protected Public Online Presence

### 2.4.1 Requirement Description

Publicly accessible services must be deployed in a dedicated network segment to minimize security risks to internal infrastructure.

### 2.4.2 Implementation

- Deployment of a **web server in a DMZ network**
- Isolation of public services from internal systems
- Controlled access from the internet to the web service

### 2.4.3 Corresponding Tasks

- Install and configure Linux web server
- Deploy static website
- Configure HTTPS using certificates
- Place web server in DMZ network segment

---

## 2.5 REQ-S2P1-05 – Controlled Network Access at Boundaries

### 2.5.1 Requirement Description

All traffic between network segments must pass through a control point where security policies can be enforced.

### 2.5.2 Implementation

- Deployment of a **firewall and router**
- Traffic inspection and filtering between network zones
- Enforcement of security policies between internal, DMZ, and external networks

### 2.5.3 Corresponding Tasks

- Configure pfSense firewall
- Define firewall rules between VLANs
- Implement NAT for external access to public services

---

## 2.6 REQ-S2P1-06 – Virtual Infrastructure Deployment

### 2.6.1 Requirement Description

Core services and network components must be implemented using virtualization to improve resource efficiency and flexibility.

### 2.6.2 Implementation

- Deployment of **virtual machines for servers and infrastructure**
- Logical separation of services across multiple VMs

### 2.6.3 Corresponding Tasks

- Create virtual machines for infrastructure components
- Deploy Windows and Linux servers
- Configure virtual network interfaces

---

## 2.7 REQ-S2P1-07 – Proactive System and Service Monitoring

### 2.7.1 Requirement Description

Critical systems and services must be monitored to detect performance issues or failures.

### 2.7.2 Implementation

- Monitoring scripts developed in **Python**
- Collection of system metrics such as CPU usage, memory usage, and disk usage
- Storage of monitoring data for analysis

### 2.7.3 Corresponding Tasks

- Develop monitoring scripts
- Configure metric collection
- Store monitoring data for later analysis

---

## 2.8 REQ-S2P1-08 – Automated Task Execution

### 2.8.1 Requirement Description

Administrative tasks should be automated to improve efficiency and reduce manual work.

### 2.8.2 Implementation

- Use of **Python scripting environment**
- Automation of monitoring and administrative tasks

### 2.8.3 Corresponding Tasks

- Setup Python environment
- Develop automation scripts
- Store and manage scripts in a Git repository

---

## 2.9 REQ-S2P1-09 – Defined Management Processes

### 2.9.1Requirement Description

Structured processes must exist for managing system changes and responding to incidents.

### 2.9.2 Implementation

- Basic **ITIL-inspired management processes**
- Defined workflows for incident management and change requests

### 2.9.3 Corresponding Tasks

- Design incident management process
- Design change management process
- Create incident and change request templates

---

## 2.10 REQ-S2P1-10 – Standardized Workstation Management

### 2.10.1 Requirement Description

Workstations must be centrally managed to ensure consistent configuration, security, and user experience.

### 2.10.2 Implementation

- Centralized workstation management through **Active Directory policies**
- Automated configuration and update management

### 2.10.3 Corresponding Tasks

- Join workstations to the domain
- Configure Group Policy settings
- Standardize workstation configurations

---

# 3. Conclusion

The requirements described in this document form the basis for the design and implementation of the new IT infrastructure for _The Knowledge Hub_. By translating the needs of the organization into concrete technical solutions, it becomes easier to plan and build the system in a structured way.

Each requirement is connected to specific technologies and tasks that will be carried out during the project.