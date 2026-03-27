
**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# Table of Contents

---

# 1. Introduction

This document defines the functional requirements for Phase 2 of The Knowledge Hub IT infrastructure project. Phase 2 extends the on-premises foundation built in S2P1 into a hybrid cloud environment, with a focus on network optimization, advanced security, and traffic management. Requirements are mapped directly to technical implementations and key technologies.

---

# 2. Requirements Overview

| ID          | Title                                    | Keywords                         |
| ----------- | ---------------------------------------- | -------------------------------- |
| REQ-S2P2-01 | Cloud Foundation & Governance            | Cloud Infrastructure             |
| REQ-S2P2-02 | Hybrid Connectivity                      | Networking                       |
| REQ-S2P2-03 | Secure PaaS Networking                   | Networking / Security            |
| REQ-S2P2-04 | Centralized Monitoring Data Store        | Data / PaaS                      |
| REQ-S2P2-05 | Monitoring Data Access Interface         | Application / API                |
| REQ-S2P2-06 | Enhanced Monitoring Application          | Automation / Monitoring          |
| REQ-S2P2-07 | On-Premises Network Optimization         | Networking (Flavor A)            |
| REQ-S2P2-08 | Wireless Network Security                | Networking / Security (Flavor A) |
| REQ-S2P2-09 | Azure Firewall & Advanced Cloud Security | Cloud Security (Flavor A)        |
| REQ-S2P2-10 | Automation & Scripting                   | Automation                       |
| REQ-S2P2-11 | Project Management & Compliance          | Governance                       |

---

# 3. Detailed Requirements

## 3.1 REQ-S2P2-01 – Cloud Foundation & Governance

**Description:** A structured, secure, and well-governed cloud environment must be
established as the foundation for all Phase 2 services.

| Aspect | Requirement |
|--------|-------------|
| Organization | Logical resource grouping and hierarchy |
| Security | Centralized network security controls |
| Policy | Automated compliance and standards enforcement |
| Identification | Consistent resource tagging strategy |
| Cost | OPEX visibility and cost management |
| Access | Role-based access control, least privilege |

**Key Technologies:** Management Groups, Resource Groups, Azure Policy, Azure RBAC,
Cost Management, Network Security Groups

---

## 3.2 REQ-S2P2-02 – Hybrid Connectivity

**Description:** A secure, reliable connection between the existing on-premises network
(S2P1) and the cloud environment, with controlled traffic flow via defined routing rules.

| Aspect | Requirement |
|--------|-------------|
| Connectivity | Encrypted site-to-site tunnel |
| Routing | Defined rules for on-premises ↔ cloud traffic |
| Security | Controlled traffic flow, no open public exposure |

**Key Technologies:** VPN Gateway, Local Network Gateway, Route Tables

---

## 3.3 REQ-S2P2-03 – Secure PaaS Networking

**Description:** All PaaS components (databases, APIs) must be accessible only via
private network connections. Public internet access must be blocked. Internal DNS
resolution must function correctly.

| Aspect | Requirement |
|--------|-------------|
| Access | Private endpoints only (no public internet) |
| Origin | Traffic from on-premises or cloud private space |
| DNS | Internal name resolution for private endpoints |

**Key Technologies:** Private Endpoints, Private DNS Zones, Virtual Network Integration

---

## 3.4 REQ-S2P2-04 – Centralized Monitoring Data Store

**Description:** A managed, scalable database in the cloud to centrally store monitoring
data from both on-premises and cloud resources, with minimal administrative overhead.

| Aspect | Requirement |
|--------|-------------|
| Deployment | Managed PaaS database service |
| Scope | Data from on-premises and cloud resources |
| Operations | Minimal DBA overhead (managed service) |
| Access | Reachable only via private network (REQ-S2P2-03) |

**Key Technologies:** Azure Database for PostgreSQL Flexible Server (or equivalent
managed DB)

---

## 3.5 REQ-S2P2-05 – Monitoring Data Access Interface

**Description:** A secure, well-defined API hosted in the cloud as the single point of
interaction for submitting and retrieving monitoring data from the central database
(REQ-S2P2-04).

| Aspect | Requirement |
|--------|-------------|
| Interface | REST API with defined endpoints |
| Security | Authenticated access only |
| Network | Private access only (REQ-S2P2-03) |
| Consumers | Monitoring script (S2P1) and future applications |

**Key Technologies:** Azure Functions / App Service, API Management (optional)

---

## 3.6 REQ-S2P2-06 – Enhanced Monitoring Application

**Description:** The monitoring application from S2P1 must be upgraded to integrate
with cloud services and expand its monitoring scope.

| Enhancement | Requirement |
|-------------|-------------|
| Data submission | Send collected data to the API (REQ-S2P2-05) securely |
| Cloud monitoring | Monitor health and performance of PaaS components (DB, API) |
| Compatibility | Maintain existing on-premises monitoring capabilities |

**Key Technologies:** Python, REST API integration, Azure SDK / HTTP libraries

---

## 3.7 REQ-S2P2-07 – On-Premises Network Optimization

**Description:** The existing on-premises network must be analyzed and enhanced to
address traffic bottlenecks, improve routing efficiency, and prioritize critical
library traffic over general public internet usage.

| Aspect | Requirement |
|--------|-------------|
| Bottleneck analysis | Review S2P1 VLAN design; identify staff vs. public traffic conflicts |
| Routing | Research and implement a dynamic routing protocol (RIPv2 or OSPF); evaluate benefit over static routing |
| QoS | Prioritize traffic to/from the Azure API and DB over public Wi-Fi internet traffic |
| Media awareness | Account for speed limitations of different network media in QoS design |

**Key Technologies:** RIPv2 / OSPF, QoS policies (DSCP marking, traffic shaping),
managed switch/router configuration

---

## 3.8 REQ-S2P2-08 – Wireless Network Security

**Description:** The library's Wi-Fi networks must be analyzed and configured to apply
current security standards, with separate, appropriately secured profiles for staff
and public guests.

| Aspect | Requirement |
|--------|-------------|
| Standards | Evaluate and implement Wi-Fi 5 or Wi-Fi 6 where applicable |
| Staff Wi-Fi | Recommend secure settings; use WPA3 where feasible |
| Guest Wi-Fi | Isolate from staff network; apply appropriate restrictions |
| Protocols | Justify protocol choice (WPA2 vs. WPA3) per network segment |

**Key Technologies:** WPA2-Enterprise / WPA3, SSID segmentation, VLAN-to-SSID
mapping, wireless access point configuration

---

### 3.9 REQ-S2P2-09 – Azure Firewall & Advanced Cloud Security

**Description:** An Azure Firewall must be deployed in the Hub VNet to provide
granular traffic control beyond what NSGs offer, protecting current and future
Azure resources.

| Aspect | Requirement |
|--------|-------------|
| Placement | Deployed in the Azure Hub VNet |
| Inter-spoke control | Rules to control traffic between spoke VNets (future growth) |
| Outbound filtering | Filter and log outbound internet traffic from Azure resources |
| Hybrid inspection | Inspect and control traffic between Azure and on-premises |
| Rule design | Define specific, granular firewall rules with documented justification |

**Key Technologies:** Azure Firewall (Standard or Premium), Azure Firewall Policy,
UDR (User Defined Routes), Hub-Spoke VNet topology

---

### 3.10 REQ-S2P2-10 – Automation & Scripting

**Description:** Deployment and configuration tasks for cloud infrastructure must be
automated where feasible to ensure consistency and efficiency.

| Aspect | Requirement |
|--------|-------------|
| Infrastructure | Scripted/repeatable cloud resource deployment |
| Monitoring app | Treated as a key automation deliverable |
| Consistency | Reduce manual configuration errors through scripting |

**Key Technologies:** PowerShell, Azure CLI, Bicep / ARM Templates, Python

---

### 3.11 REQ-S2P2-11 – Project Management & Compliance

**Description:** The project must follow a defined methodology and demonstrate GDPR
compliance throughout design and implementation.

| Aspect | Requirement |
|--------|-------------|
| Methodology | Defined planning, tracking, and risk management process |
| Business alignment | IT decisions traceable to library needs (IT Business Analysis) |
| Compliance | GDPR requirements addressed in data handling and security design |
| Deliverables | Risk register, project plan, reflection report |

**Key Frameworks:** GDPR, ITIL-inspired processes, project management methodology
(e.g., Prince2 Agile / Scrum)

---

## 4. Conclusion

The requirements defined in this document extend The Knowledge Hub's IT infrastructure
into a hybrid cloud model with a focus on network performance, wireless security, and
advanced cloud traffic control. Each requirement is linked to concrete technologies and
implementation tasks. Together, they form the basis for a secure, optimized, and
compliant hybrid environment built on the S2P1 foundation — specifically aligned with
the Flavor A: Network Optimization & Advanced Security track.