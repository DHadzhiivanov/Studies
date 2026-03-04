
**Name:** David Hadzhiivanov
**Student Number:**  570330

---

# Table of Contents

1. Introduction
2. Main Problem
3. Stakeholder Identification and Analysis
    1. Library Staff
        1. Role and Perspective
        2. Current Problems
        3. Desired Situation
        4. Addressed Requirements
        5. IT Solutions
    2. Library Management
        1. Role and Perspective
        2. Current Problems
        3. Desired Situation
        4. Addressed Requirements
        5. IT Solutions
    3. Visitors (Public Users)
        1. Role and Perspective
        2. Current Problems
        3. Desired Situation
        4. Addressed Requirements
        5. IT Solutions
    4. IT Support Personnel
        1. Role and Perspective
        2. Current Problems
        3. Desired Situation
        4. Addressed Requirements
        5. IT Solutions
    5. Teachers and Assessors
        1. Role and Perspective
        2. Current Problems
        3. Desired Situation
        4. Addressed Requirements
        5. IT Solutions
4. Functional Requirements and Corresponding IT Solutions
    1. REQ-S2P1-01 Centralized User and Resource Management
    2. REQ-S2P1-02 Structured and Segmented Network
    3. REQ-S2P1-03 Secure Collaborative Storage
    4. REQ-S2P1-04 Protected Public Online Presence
    5. REQ-S2P1-05 Controlled Network Access at Boundaries
    6. REQ-S2P1-06 Virtual Infrastructure Deployment
    7. REQ-S2P1-07 Proactive System and Service Monitoring
    8. REQ-S2P1-08 Automated Task Execution
    9. REQ-S2P1-09 Defined Management Processes
    10. REQ-S2P1-10 Standardized Workstation Management
5. Conclusion

---

# Introduction

This document presents a stakeholder and requirements analysis for the IT infrastructure modernization project at The Knowledge Hub library. The objective of this analysis is to identify key stakeholder groups, understand their needs and concerns, and determine how the defined functional requirements address these needs through appropriate ICT solutions.

---

# Main Problem

The current IT environment is fragmented, outdated, and difficult to manage, resulting in reduced staff productivity, limited digital services for visitors, and maintenance challenges for IT personnel. The proposed infrastructure aims to provide a secure, scalable, and manageable foundation that supports future digital services while addressing current operational limitations.

---

# Stakeholder Analysis

The successful implementation of the new IT infrastructure depends on understanding the expectations and requirements of all relevant stakeholders. The following stakeholder groups have been identified.

---

## Stakeholder Classification

| Stakeholder            | Type     | Description                                             |
| ---------------------- | -------- | ------------------------------------------------------- |
| Library Staff          | Internal | Employees using IT systems daily                        |
| Library Management     | Internal | Decision makers responsible for operations and strategy |
| IT Support Personnel   | Internal | Maintain and manage infrastructure                      |
| Visitors               | External | Public users of library digital services                |
| Teachers and Assessors | External | Evaluate project implementation and learning outcomes   |

## Stakeholder Interests and Expectations

| Stakeholder            | Main Interests                                    | Concerns                                     | Expected Benefits                         |
| ---------------------- | ------------------------------------------------- | -------------------------------------------- | ----------------------------------------- |
| Library Staff          | Fast systems, file sharing, reliable workstations | Slow systems, data loss, inconsistent setups | Improved productivity and collaboration   |
| Library Management     | Control, scalability, security                    | System failures, lack of visibility          | Reliable and future-proof infrastructure  |
| Visitors               | Secure access, privacy, stable services           | Data privacy risks, unreliable systems       | Better digital experience                 |
| IT Support             | Manageable infrastructure, automation, monitoring | Complex maintenance, lack of tools           | Easier administration and troubleshooting |
| Teachers and Assessors | Clear documentation, correct implementation       | Missing requirements, poor structure         | Demonstration of competencies             |

## Library Staff

### Role and Perspective

Library staff are the primary users of the internal IT systems and depend on reliable access to digital resources to perform their daily tasks efficiently.

### Current Problems

- Slow and unreliable systems
- Lack of centralized file storage and collaboration tools
- Inconsistent workstation configurations
- Limited access control mechanisms
- Inefficient manual processes

### Desired Situation

Staff require reliable systems, fast access to shared resources, secure document handling, and standardized work environments that support efficient collaboration.

### Addressed Requirements

- [[#REQ-S2P1-01 Centralized User and Resource Management|REQ-S2P1-01]] Centralized User and Resource Management
- [[#REQ-S2P1-03 Secure Collaborative Storage|REQ-S2P1-03]] Secure Collaborative Storage
- [[#REQ-S2P1-10 Standardized Workstation Management|REQ-S2P1-10]] Standardized Workstation Management
- [[#REQ-S2P1-02 Structured and Segmented Network|REQ-S2P1-02]] Structured and Segmented Network

### IT Solutions

- Centralized directory services for authentication and authorization
- File server with role-based access control
- Centralized workstation configuration policies
- Automated network configuration for user devices

---

## Library Management

### Role and Perspective

Library management is responsible for strategic decision-making, operational efficiency, and future development of digital services.

### Current Problems

- Limited visibility and control over IT systems
- Lack of system monitoring and performance reporting
- Infrastructure not prepared for future expansion
- Security and operational risks

### Desired Situation

Management requires a scalable and secure infrastructure with centralized control, monitoring capabilities, and structured management processes.

### Addressed Requirements

- [[#REQ-S2P1-07 Proactive System and Service Monitoring| REQ-S2P1-07]] Proactive System and Service Monitoring
- [[#REQ-S2P1-08 Automated Task Execution|REQ-S2P1-08]] Automated Task Execution
- [[#REQ-S2P1-09 Defined Management Processes|REQ-S2P1-09]] Defined Management Processes
- [[#REQ-S2P1-06 Virtual Infrastructure Deployment|REQ-S2P1-06]] Virtual Infrastructure Deployment

### IT Solutions

- Monitoring and logging mechanisms
- Automated administrative processes
- Virtualized infrastructure for efficiency
- Defined incident and change management procsses

---

## Visitors (Public Users)

### Role and Perspective

Visitors use public computers and network services provided by the library and require secure and reliable access to digital resources.

### Current Problems

- Unreliable public systems
- Limited digital services
- Potential security risks
- Insufficient separation between public and internal resources

### Desired Situation

Visitors expect secure access to public services, stable systems, and protection of personal data and privacy.

### Addressed Requirements

- [[#REQ-S2P1-02 Structured and Segmented Network|REQ-S2P1-02]] Structured and Segmented Network
- [[#REQ-S2P1-04 Protected Public Online Presence|REQ-S2P1-04]] Protected Public Online Presence
- [[#REQ-S2P1-05 Controlled Network Access at Boundaries|REQ-S2P1-05]] Controlled Network Access at Boundaries

### IT Solutions

- Segregated public network environment
- Restricted public workstations
- Dedicated network zone for public services (DMZ)
- Firewall-based traffic control

---

## IT Support Personnel

### Role and Perspective

IT support personnel are responsible for maintaining, monitoring, and troubleshooting the infrastructure. As support is provided part-time, manageability and documentation are critical.

### Current Problems

- Fragmented infrastructure
- Difficult maintenance and troubleshooting
- Lack of monitoring and automation tools
- Limited documentation

### Desired Situation

IT support requires centralized management tools, automation capabilities, monitoring systems, and clear documentation to maintain the infrastructure efficiently.

### Addressed Requirements

- [[#REQ-S2P1-07 Proactive System and Service Monitoring|REQ-S2P1-07]] Proactive System and Service Monitoring
- [[#REQ-S2P1-08 Automated Task Execution|REQ-S2P1-08]] Automated Task Execution
- [[#REQ-S2P1-09 Defined Management Processes|REQ-S2P1-09]] Defined Management Processes
- [[#REQ-S2P1-06 Virtual Infrastructure Deployment|REQ-S2P1-06]] Virtual Infrastructure Deployment

### IT Solutions

- Monitoring and alerting mechanisms
- Automated administrative scripts
- Standardized configurations
- Comprehensive documentation practices

---

## Teachers and Assessors

### Role and Perspective

Teachers and assessors evaluate the project implementation and learning outcomes. They are stakeholders because they define project expectations, assess compliance with requirements, and evaluate the quality of technical and documentation deliverables.

### Current Problems

- Need for clear demonstration of competencies
- Requirement for structured documentation and justification of decisions
- Need for reproducible and verifiable implementation    

### Desired Situation

Teachers and assessors expect a structured, well-documented implementation that demonstrates analysis, design, realization, and management competencies.

### Addressed Requirements

- [[#REQ-S2P1-07 Proactive System and Service Monitoring|REQ-S2P1-07]] Proactive Monitoring
- [[#REQ-S2P1-08 Automated Task Execution|REQ-S2P1-08]] Automated Task Execution
- [[#REQ-S2P1-09 Defined Management Processes|REQ-S2P1-09]] Defined Management Processes
- [[#REQ-S2P1-06 Virtual Infrastructure Deployment|REQ-S2P1-06]] Virtual Infrastructure Deployment

### IT Solutions

- Proper documentation of infrastructure design
- Implementation of monitoring and automation tools
- Structured system architecture and management processes
- Clear justification of technical decisions

---

# Functional Requirements and Corresponding IT Solutions

The following section explains how each functional requirement is implemented through technical solutions.

---

## REQ-S2P1-01 Centralized User and Resource Management

A central directory service provides authentication and authorization for users and systems. This enables controlled access to resources and centralized user administration.

**Implementation:** Domain-based identity management, centralized authentication, and role-based access control.

---

## REQ-S2P1-02 Structured and Segmented Network

The network is logically divided into separate zones to improve security and organization.

**Implementation:** Segmented network architecture with distinct zones for servers, staff workstations, public systems, and public services, including automated network configuration.

---

## REQ-S2P1-03 Secure Collaborative Storage

A centralized storage location enables secure document sharing and access control based on user roles.

**Implementation:** Central file server with permission management linked to the directory service.

---

## REQ-S2P1-04 Protected Public Online Presence

Public services are deployed in a dedicated network zone to minimize risks to internal resources.

**Implementation:** Deployment of public services in a demilitarized zone with controlled access.

---

## REQ-S2P1-05 Controlled Network Access at Boundaries

All traffic between network segments is filtered to enforce security policies.

**Implementation:** Firewall-based traffic inspection and filtering.

---

## REQ-S2P1-06 Virtual Infrastructure Deployment

Virtualization provides logical separation of services and efficient resource utilization.

**Implementation:** Virtual machines hosting core services and network components.

---

## REQ-S2P1-07 Proactive System and Service Monitoring

System performance and availability are continuously monitored.

**Implementation:** Monitoring tools and scripts collecting performance metrics and generating alerts.

---

## REQ-S2P1-08 Automated Task Execution

Administrative tasks are automated to improve efficiency.

**Implementation:** Scripting environment and automated procedures.

---

## REQ-S2P1-09 Defined Management Processes

Structured processes manage system changes and incident resolution.

**Implementation:** Defined incident and change management workflows.

---

## REQ-S2P1-10 Standardized Workstation Management

Centralized configuration ensures consistent workstation security and behavior.

**Implementation:** Centrally enforced configuration policies and system updates.

---

# Conclusion

The stakeholder and requirements analysis demonstrates that the proposed IT infrastructure addresses the needs of all relevant stakeholders by providing centralized management, secure resource access, network segmentation, monitoring capabilities, and standardized processes. The identified IT solutions form the foundation for a secure, scalable, and manageable infrastructure that supports operational efficiency and future digital services at The Knowledge Hub.