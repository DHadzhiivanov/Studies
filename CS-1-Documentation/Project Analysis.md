
**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# Table of Contents

- [[#1. Introduction|1. Introduction]]
- [[#2. Main Questions|2. Main Questions]]
    - [[#2.1 Sub Questions|2.1 Sub Questions]]
- [[#3. Health Check of Existing Infrastructure|3. Health Check of Existing Infrastructure]]
    - [[#3.1 Observed Issues|3.1 Observed Issues]]
    - [[#3.2 Type of Project|3.2 Type of Project]]
- [[#4. Stakeholder Identification|4. Stakeholder Identification]]
- [[#5. Project Capability Analysis|5. Project Capability Analysis]]
- [[#6. Benefit Assessment|6. Benefit Assessment]]
- [[#7. Cost Considerations|7. Cost Considerations]]
- [[#8. Risk Analysis|8. Risk Analysis]]
- [[#9. MoSCoW Prioritization|9. MoSCoW Prioritization]]
    - [[#9.1 Must Have|9.1 Must Have]]
    - [[#9.2 Should Have|9.2 Should Have]]
    - [[#9.3 Could Have|9.3 Could Have]]
    - [[#9.4 Won't Have|9.4 Won't Have]]
- [[#10. Value Scorecard|10. Value Scorecard]]
- [[#11. Conclusion|11. Conclusion]]

---

# 1. Introduction

This document outlines the project plan for the IT infrastructure modernization of *The Knowledge Hub*. The goal of this project is to replace the outdated and fragmented IT environment with a structured, secure, and manageable infrastructure.

The project focuses on building a stable foundation that supports staff productivity, provides reliable services for visitors, and allows future expansion of digital services. The infrastructure will include centralized user management, network segmentation, secure file storage, monitoring, and standardized workstation management.

This project plan describes the scope of the project, stakeholder involvement, prioritization of requirements, risk considerations, and the overall approach used to implement the infrastructure.

---

# 2. Main Questions

How can old systems be modernized to ensure efficiency in scalability, security and costs?

## 2.1 Sub Questions

1. What will the topology look like?
2. Which centralized services are needed?
3. How is security going to be enforced?
4. What could be considered cost-effective?

---

# 3. Health Check of Existing Infrastructure

The current IT environment of *The Knowledge Hub* is outdated and lacks central management. Systems are fragmented and not properly integrated, which causes inefficiencies and security risks.

## 3.1 Observed Issues

| Issue | Impact |
|------|------|
| No centralized user management | Difficult to manage access rights |
| Lack of network segmentation | Increased security risks |
| No centralized file storage | Poor collaboration between staff |
| Limited monitoring | Failures are detected too late |
| Inconsistent workstation configurations | Management overhead |

## 3.2 Type of Project

Based on the health check, this project can be classified as:

**Infrastructure modernization and foundational IT implementation**

The goal is not to upgrade individual systems but to design and deploy a **structured IT environment from the ground up**.

---

# 4. Stakeholder Identification

Stakeholders are individuals or groups that influence the project or are affected by its outcome.

| Stakeholder | Role | Interest in Project |
|-------------|------|---------------------|
| Library Management | Decision makers | Reliable infrastructure and future scalability |
| Library Staff | Daily users | Stable systems and fast access to resources |
| Visitors | Public users | Access to public computers and WiFi |
| IT Support Personnel | System administrators | Maintainable and well-documented environment |
| Teachers / Assessors | Project evaluators | Ensuring learning outcomes are achieved |

---

# 5. Project Capability Analysis

The project aims to provide the following capabilities.

| Capability | Description |
|-----------|-------------|
| Centralized identity management | Users managed through Active Directory |
| Network segmentation | VLAN-based separation of network zones |
| Secure file sharing | Central file server with role-based access |
| Public web presence | Web server hosted in DMZ |
| Infrastructure monitoring | Monitoring scripts collecting system metrics |
| Automation | Scripts to reduce manual administrative work |

---

# 6. Benefit Assessment

| Benefit | Description |
|--------|-------------|
| Improved security | Segmented networks and centralized access control |
| Increased productivity | Staff gain reliable access to shared resources |
| Better maintainability | Standardized environment for IT support |
| Future scalability | Infrastructure can support new services |

---

# 7. Cost Considerations

Since this is a small organization with limited budget, the infrastructure design prioritizes cost efficiency.

| Cost Factor        | Approach                                         |
| ------------------ | ------------------------------------------------ |
| Hardware resources | Use of virtualization                            |
| Licensing          | Combination of Windows and open-source solutions |
| Maintenance        | Automation and monitoring to reduce manual work  |
| Network design     | 2 Layer design                                   |

---

# 8. Risk Analysis

Potential risks must be identified early so mitigation strategies can be applied.

| Risk | Impact | Likelihood | Mitigation |
|-----|--------|-----------|------------|
| Misconfigured network segmentation | Security vulnerability | Medium | Careful VLAN and firewall configuration |
| Server failure | Service downtime | Low | Virtualization and monitoring |
| Incorrect access permissions | Data exposure | Medium | Role-based access control |
| Lack of documentation | Difficult maintenance | Medium | Maintain clear documentation |

---

# 9. MoSCoW Prioritization

MoSCoW helps determine which project components are most critical.

## 9.1 Must Have

- Active Directory Domain Controller
- Network segmentation
- File server with access control
- Firewall and secure network boundaries
- Virtualized infrastructure

## 9.2 Should Have

- Monitoring scripts
- Web server with HTTPS
- Automated administrative tasks

## 9.3 Could Have

- Advanced monitoring dashboards
- Extended automation features

## 9.4 Won't Have

- Cloud integration
- Large-scale high availability systems

---

# 10. Value Scorecard

The value scorecard evaluates the expected value of the infrastructure.

| Criteria | Score | Explanation |
|---------|------|-------------|
| Security Improvement | High | Segmented networks and centralized authentication |
| Operational Efficiency | High | Centralized management and automation |
| Scalability | Medium | Infrastructure prepared for future expansion |
| Cost Efficiency | Medium | Virtualization reduces hardware costs |

---

# 11. Conclusion

This project plan outlines the approach for implementing a modern IT infrastructure for *The Knowledge Hub*. By identifying stakeholders, assessing risks, and prioritizing requirements, the project provides a clear roadmap for building a secure and manageable environment.

The infrastructure will provide centralized management, improved security, and a scalable foundation that supports both current operational needs and future digital initiatives.