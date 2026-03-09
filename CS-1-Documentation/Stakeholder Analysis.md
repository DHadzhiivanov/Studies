
**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# Table of Contents

- [[#1. Introduction|1. Introduction]]
- [[#2. Main Problem|2. Main Problem]]
- [[#3. Stakeholder Analysis|3. Stakeholder Analysis]]
    - [[#3.1 Stakeholder Classification|3.1 Stakeholder Classification]]
    - [[#3.2 Stakeholder Interests and Expectations|3.2 Stakeholder Interests and Expectations]]
    - [[#3.3 Library Staff|3.3 Library Staff]]
        - [[#3.3.1 Role and Perspective|3.3.1 Role and Perspective]]
        - [[#3.3.2 Current Problems|3.3.2 Current Problems]]
        - [[#3.3.3 Desired Situation|3.3.3 Desired Situation]]
        - [[#3.3.4 Addressed Requirements|3.3.4 Addressed Requirements]]
        - [[#3.3.5 IT Solutions|3.3.5 IT Solutions]]
    - [[#3.4 Library Management|3.4 Library Management]]
        - [[#3.4.1 Role and Perspective|3.4.1 Role and Perspective]]
        - [[#3.4.2 Current Problems|3.4.2 Current Problems]]
        - [[#3.4.3 Desired Situation|3.4.3 Desired Situation]]
        - [[#3.4.4 Addressed Requirements|3.4.4 Addressed Requirements]]
        - [[#3.4.5 IT Solutions|3.4.5 IT Solutions]]
    - [[#3.5 Visitors (Public Users)|3.5 Visitors (Public Users)]]
        - [[#3.5.1 Role and Perspective|3.5.1 Role and Perspective]]
        - [[#3.5.2 Current Problems|3.5.2 Current Problems]]
        - [[#3.5.3 Desired Situation|3.5.3 Desired Situation]]
        - [[#3.5.4 Addressed Requirements|3.5.4 Addressed Requirements]]
        - [[#3.5.5 IT Solutions|3.5.5 IT Solutions]]
    - [[#3.6 IT Support Personnel|3.6 IT Support Personnel]]
        - [[#3.6.1 Role and Perspective|3.6.1 Role and Perspective]]
        - [[#3.6.2 Current Problems|3.6.2 Current Problems]]
        - [[#3.6.3 Desired Situation|3.6.3 Desired Situation]]
        - [[#3.6.4 Addressed Requirements|3.6.4 Addressed Requirements]]
        - [[#3.6.5 IT Solutions|3.6.5 IT Solutions]]
    - [[#3.7 Teachers and Assessors|3.7 Teachers and Assessors]]
        - [[#3.7.1 Role and Perspective|3.7.1 Role and Perspective]]
        - [[#3.7.2 Current Problems|3.7.2 Current Problems]]
        - [[#3.7.3 Desired Situation|3.7.3 Desired Situation]]
        - [[#3.7.4 Addressed Requirements|3.7.4 Addressed Requirements]]
        - [[#3.7.5 IT Solutions|3.7.5 IT Solutions]]
- [[#4. Advanced Stakeholder Analysis|4. Advanced Stakeholder Analysis]]
    - [[#4.1 Stakeholder Power-Interest Matrix|4.1 Stakeholder Power-Interest Matrix]]
        - [[#4.1.1Interpretation|4.1.1Interpretation]]
- [[#5. Communication Plan|5. Communication Plan]]
    - [[#5.1 Stakeholder Communication Plan|5.1 Stakeholder Communication Plan]]
        - [[#5.1.1 Communication Approach|5.1.1 Communication Approach]]
- [[#6. Stakeholder Risk Analysis|6. Stakeholder Risk Analysis]]
    - [[#6.1 Stakeholder Risk Assessment|6.1 Stakeholder Risk Assessment]]
        - [[#6.1.1 Risk Evaluation|6.1.1 Risk Evaluation]]
- [[#7. Conclusion|7. Conclusion]]

---

# 1. Introduction

This document presents a stakeholder and requirements analysis for the IT infrastructure modernization project at *The Knowledge Hub* library. The objective of this analysis is to identify key stakeholder groups, understand their needs and concerns, and determine how the defined functional requirements address these needs through appropriate ICT solutions.

---

# 2. Main Problem

The current IT environment is **fragmented**, **outdated**, and **difficult to manage**, resulting in **reduced staff productivity**, **limited digital services** for visitors, and **maintenance challenges** for IT personnel. The proposed infrastructure aims to provide a secure, scalable, and manageable foundation that supports future digital services while addressing current operational limitations.

---

# 3. Stakeholder Analysis

The successful implementation of the new IT infrastructure depends on understanding the expectations and requirements of all relevant stakeholders.

---

## 3.1 Stakeholder Classification

| Stakeholder            | Type     | Description                                             |
| ---------------------- | -------- | ------------------------------------------------------- |
| Library Staff          | Internal | Employees using IT systems daily                        |
| Library Management     | Internal | Decision makers responsible for operations and strategy |
| IT Support Personnel   | Internal | Maintain and manage infrastructure                      |
| Visitors               | External | Public users of library digital services                |
| Teachers and Assessors | External | Evaluate project implementation and learning outcomes   |

## 3.2 Stakeholder Interests and Expectations

| Stakeholder            | Main Interests                                    | Concerns                                     | Expected Benefits                         |
| ---------------------- | ------------------------------------------------- | -------------------------------------------- | ----------------------------------------- |
| Library Staff          | Fast systems, file sharing, reliable workstations | Slow systems, data loss, inconsistent setups | Improved productivity and collaboration   |
| Library Management     | Control, scalability, security                    | System failures, lack of visibility          | Reliable and future-proof infrastructure  |
| Visitors               | Secure access, privacy, stable services           | Data privacy risks, unreliable systems       | Better digital experience                 |
| IT Support             | Manageable infrastructure, automation, monitoring | Complex maintenance, lack of tools           | Easier administration and troubleshooting |
| Teachers and Assessors | Clear documentation, correct implementation       | Missing requirements, poor structure         | Demonstration of competencies             |

## 3.3 Library Staff

### 3.3.1 Role and Perspective

Library staff are the primary users of the internal IT systems and depend on reliable access to digital resources to perform their daily tasks efficiently.

### 3.3.2 Current Problems

- Slow and unreliable systems
- Lack of centralized file storage and collaboration tools
- Inconsistent workstation configurations
- Limited access control mechanisms
- Inefficient manual processes

### 3.3.3 Desired Situation

Staff require reliable systems, fast access to shared resources, secure document handling, and standardized work environments that support efficient collaboration.

### 3.3.4 Addressed Requirements

- **REQ-S2P1-01** Centralized User and Resource Management
- **REQ-S2P1-03** Secure Collaborative Storage
- **REQ-S2P1-10** Standardized Workstation Management
- **REQ-S2P1-02** Structured and Segmented Network

### 3.3.5 IT Solutions

- Centralized directory services for authentication and authorization
- File server with role-based access control
- Centralized workstation configuration policies
- Automated network configuration for user devices

---

## 3.4 Library Management

### 3.4.1 Role and Perspective

Library management is responsible for strategic decision-making, operational efficiency, and future development of digital services.

### 3.4.2 Current Problems

- Limited visibility and control over IT systems
- Lack of system monitoring and performance reporting
- Infrastructure not prepared for future expansion
- Security and operational risks

### 3.4.3 Desired Situation

Management requires a scalable and secure infrastructure with centralized control, monitoring capabilities, and structured management processes.

### 3.4.4 Addressed Requirements

- **REQ-S2P1-07** Proactive System and Service Monitoring
- **REQ-S2P1-08** Automated Task Execution
- **REQ-S2P1-09** Defined Management Processes
- **REQ-S2P1-06** Virtual Infrastructure Deployment

### 3.4.5 IT Solutions

- Monitoring and logging mechanisms
- Automated administrative processes
- Virtualized infrastructure for efficiency
- Defined incident and change management procsses

---

## 3.5 Visitors (Public Users)

### 3.5.1 Role and Perspective

Visitors use public computers and network services provided by the library and require secure and reliable access to digital resources.

### 3.5.2 Current Problems

- Unreliable public systems
- Limited digital services
- Potential security risks
- Insufficient separation between public and internal resources

### 3.5.3 Desired Situation

Visitors expect secure access to public services, stable systems, and protection of personal data and privacy.

### 3.5.4 Addressed Requirements

- **REQ-S2P1-02** Structured and Segmented Network
- **REQ-S2P1-04** Protected Public Online Presence
- **REQ-S2P1-05** Controlled Network Access at Boundaries

### 3.5.5 IT Solutions

- Segregated public network environment
- Restricted public workstations
- Dedicated network zone for public services (DMZ)
- Firewall-based traffic control

---

## 3.6 IT Support Personnel

### 3.6.1 Role and Perspective

IT support personnel are responsible for maintaining, monitoring, and troubleshooting the infrastructure. As support is provided part-time, manageability and documentation are critical.

### 3.6.2 Current Problems

- Fragmented infrastructure
- Difficult maintenance and troubleshooting
- Lack of monitoring and automation tools
- Limited documentation

### 3.6.3 Desired Situation

IT support requires centralized management tools, automation capabilities, monitoring systems, and clear documentation to maintain the infrastructure efficiently.

### 3.6.4 Addressed Requirements

- **REQ-S2P1-07** Proactive System and Service Monitoring
- **REQ-S2P1-08** Automated Task Execution
- **REQ-S2P1-09** Defined Management Processes
- **REQ-S2P1-06** Virtual Infrastructure Deployment

### 3.6.5 IT Solutions

- Monitoring and alerting mechanisms
- Automated administrative scripts
- Standardized configurations
- Comprehensive documentation practices

---

## 3.7 Teachers and Assessors

### 3.7.1 Role and Perspective

Teachers and assessors evaluate the project implementation and learning outcomes. They are stakeholders because they define project expectations, assess compliance with requirements, and evaluate the quality of technical and documentation deliverables.

### 3.7.2 Current Problems

- Need for clear demonstration of competencies
- Requirement for structured documentation and justification of decisions
- Need for reproducible and verifiable implementation    

### 3.7.3 Desired Situation

Teachers and assessors expect a structured, well-documented implementation that demonstrates analysis, design, realization, and management competencies.

### 3.7.4 Addressed Requirements

- **REQ-S2P1-07** Proactive Monitoring
- **REQ-S2P1-08** Automated Task Execution
- **REQ-S2P1-09** Defined Management Processes
- **REQ-S2P1-06** Virtual Infrastructure Deployment

### 3.7.5 IT Solutions

- Proper documentation of infrastructure design
- Implementation of monitoring and automation tools
- Structured system architecture and management processes
- Clear justification of technical decisions

---

# 4. Advanced Stakeholder Analysis

To better understand the influence of each stakeholder on the project, stakeholders are analyzed based on their **level of power and level of interest** in the project. This helps determine how actively they should be managed and involved in communication.

## 4.1 Stakeholder Power-Interest Matrix

| Stakeholder            | Power  | Interest | Management Strategy                                  |
| ---------------------- | ------ | -------- | ---------------------------------------------------- |
| Library Management     | High   | High     | Manage closely and involve in major decisions        |
| IT Support Personnel   | High   | High     | Manage closely and involve in technical decisions    |
| Library Staff          | Medium | High     | Keep informed and collect feedback                   |
| Teachers and Assessors | Medium | High     | Provide regular updates and documentation            |
| Visitors               | Low    | Medium   | Monitor satisfaction and ensure service availability |

### 4.1.1Interpretation

Stakeholders with **high power and high interest** must be closely managed because their decisions and feedback directly influence the project's success. Stakeholders with **high interest but lower power** should be kept informed and involved where appropriate.

This analysis helps prioritize communication and ensures that important stakeholders remain engaged throughout the project.

---

# 5. Communication Plan

A structured communication plan ensures that stakeholders remain informed about the progress of the project and can provide feedback when necessary.

## 5.1 Stakeholder Communication Plan

| Stakeholder            | Information Needs                        | Communication Method                | Frequency                | Responsible   |
| ---------------------- | ---------------------------------------- | ----------------------------------- | ------------------------ | ------------- |
| Library Management     | Project progress, risks, major decisions | Progress reports, meetings          | Weekly / milestone based | Project team  |
| Library Staff          | Changes to systems, new tools, training  | Demonstrations, documentation       | During implementation    | IT support    |
| IT Support Personnel   | Technical configuration, system updates  | Technical documentation, meetings   | Continuous               | Project team  |
| Teachers and Assessors | Project progress, deliverables           | Presentations, documentation review | Weekly checkpoints       | Student       |
| Visitors               | Availability of public services          | Informational signage or website    | When services change     | Library staff |

### 5.1.1 Communication Approach

The communication approach focuses on **clear documentation, regular updates, and feedback collection**. Different stakeholders require different levels of information depending on their role and influence within the project.

---

# 6. Stakeholder Risk Analysis

Stakeholders can also introduce risks to the project if their expectations, influence, or cooperation are not properly managed.

## 6.1 Stakeholder Risk Assessment

| Stakeholder            | Potential Risk                           | Impact | Mitigation Strategy                                       |
| ---------------------- | ---------------------------------------- | ------ | --------------------------------------------------------- |
| Library Management     | Changing priorities or requirements      | Medium | Maintain regular communication and progress updates       |
| Library Staff          | Resistance to new systems                | Medium | Provide training and clear documentation                  |
| IT Support Personnel   | Limited availability (part-time support) | High   | Ensure documentation and automation tools are implemented |
| Visitors               | Misuse of public systems                 | Low    | Implement network segmentation and access restrictions    |
| Teachers and Assessors | Requirements not fully addressed         | High   | Maintain structured documentation and request feedback    |

### 6.1.1 Risk Evaluation

Managing stakeholder-related risks requires **clear communication, proper documentation, and stakeholder involvement throughout the project lifecycle**. Addressing these risks early helps ensure smoother implementation and better adoption of the new infrastructure.

---

# 7. Conclusion

This stakeholder analysis identified the key groups involved in or affected by the IT infrastructure project at *The Knowledge Hub*. By analyzing their needs, interests, and influence, it becomes clearer how the proposed infrastructure supports both operational and organizational goals.  
  
The communication plan and stakeholder risk analysis help ensure that stakeholders remain informed and that potential conflicts or risks can be addressed early. Together, these elements provide a structured foundation for the design and implementation of the new IT environment.