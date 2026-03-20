# Reading Guide

---

## Learning Outcome 1: Basic Interoperability

> *After conducting research, you are able to design and implement a sustainable infrastructure based on the specified requirements of a small SME, taking into account the different types of data, connections, protocols, communication, and applications.*

This learning outcome is about building infrastructure that actually works end to end. For me that means going through the full process: understanding the requirements, designing a solution that fits them, and then actually implementing and verifying it. It is not enough to just set up a server or configure a switch in isolation. Everything has to connect and serve the right purpose.

For CS1 I designed and implemented a segmented network for the Knowledge Hub library including VLAN separation, inter-VLAN routing through pfSense, a Windows Server Domain Controller with Active Directory, DNS, OUs and users, a file server with SMB shares, and two domain-joined workstations with GPO-based standardization.

### Case Study 1

Current level: Beginning

I would place myself at Beginning because the implemented components are solid but a significant part of the design is still pending, specifically the web server, external DNS, monitoring server, and NAT configuration. The network, DC, file server, and workstations are all working and validated with evidence. I used research to back my decisions, particularly for the network topology and AD configuration.

The evidence for this LO is spread across several documents. @Design covers the full architecture and shows how I translated requirements into a technical plan. @Implementation documents what was actually built and the reasoning behind decisions. @Validation provides the test results and screenshots proving it works. @Research Doc entries 1, 5, and 6 show the research that informed the topology, AD DS setup, and file server configuration. @Requirements Analysis connects each technical component back to an organizational requirement. @Show & Grow Technical shows I presented this work to an audience.

#### Next Steps

Complete the web server, external DNS, monitoring server, and NAT configuration. These are the missing components that will fully round out the LO1 evidence. Add validation entries for each once they are implemented.

#### Reflection

The biggest challenge was the DC breaking multiple times. Each time it happened I had to diagnose what went wrong and figure out how to recover or rebuild. That was frustrating but it taught me more about how AD actually works than following a guide would have. I also learned that small configuration details like pointing DNS to the DC before joining the domain matter a lot and the only way to understand why is to see what breaks when you get it wrong.

### Evidence Overview

- @Design: Full network and infrastructure design. Section 5 covers the VLAN and IP plan, sections 8 and 10 cover security and firewall design, section 11 covers the AD structure and AGDLP group model, section 12 covers the file server share structure.
- @Requirements Analysis: Maps each functional requirement to a technical IT solution. REQ-S2P1-01, 02, 03, and 06 are directly relevant to LO1.
- @Implementation: Documents the actual configuration of each component. Sections 2 through 5 cover the network, DC, file server, and workstations.
- @Validation: Test results for all implemented components. Sections 3 through 6 provide pass/fail results and screenshots.
- @Research Doc: Entry 1 covers topology design, entry 5 covers AD DS installation, entry 6 covers file server and NTFS permissions.
- @Show & Grow Technical: Presentation demonstrating the network diagram, VLAN configuration, DHCP, and DC setup.

---

## Learning Outcome 2: Basic Securing

> *After conducting research, you are able to design and implement modern and traditional basic security measures across all infrastructure domains based on the specified requirements of a small SME.*

Security for me means making sure access is controlled, traffic is filtered, and systems are isolated from each other where they need to be. It is not just about a firewall. It runs through the whole infrastructure from the network layer down to individual folder permissions.

For CS1 I implemented VLAN segmentation to separate staff, servers, public computers, and the DMZ. Firewall rules on pfSense enforce which traffic can flow between segments. The file server uses NTFS permissions tied to AD security groups following the AGDLP model. GPO disables registry editing for staff users and excludes admin accounts from the policy.

### Case Study 1

Current level: Beginning

The security design covers multiple layers and the implemented parts are working and validated. VLAN segmentation, firewall rules, NTFS permissions, and GPO security settings are all evidenced. The gap is that the DMZ and web server are not yet implemented which means the public-facing security layer is still missing. NAT is also outstanding.

@Design sections 8 and 10 show the security design including VLAN segmentation, DMZ architecture, and the full firewall policy table. @Implementation sections 2.4, 3.4, 4.4, and 5.2 through 5.4 cover firewall rules, AGDLP groups, NTFS permissions, and GPO security settings. @Validation sections 5.2, 5.4, and 6.3 provide evidence that these security measures work correctly. @Research Doc entry 4 covers the AGDLP research. @Requirements Analysis REQ-S2P1-02, 04, and 05 are the relevant requirements.

#### Next Steps

Implement the web server in the DMZ and configure NAT on pfSense. Also complete OS-level firewall hardening on all VMs as required by Task 9.

#### Reflection

Designing the permission model was the most interesting part of this LO. Before this project I knew permissions existed but I did not understand the reasoning behind using groups instead of assigning permissions directly to users. Researching AGDLP and then actually implementing it made the logic click. The practical test of logging in as different users and seeing the correct access behavior was a good confirmation that the design was right.

### Evidence Overview

- @Design: Sections 8 and 10 cover VLAN segmentation, DMZ architecture, and the firewall policy table.
- @Implementation: Section 2.4 covers firewall rules. Section 3.4 covers AGDLP security groups. Section 4.4 covers NTFS permissions. Sections 5.2 to 5.4 cover GPO security settings.
- @Validation: Sections 5.2, 5.4, and 6.3 provide test results for RegEdit restriction, admin exclusion, and firewall rules.
- @Research Doc: Entry 4 covers the AGDLP model and the reasoning behind group nesting.
- @Requirements Analysis: REQ-S2P1-02, 04, and 05 are the security-related requirements.

---

## Learning Outcome 3: Basic Automation

> *After conducting research, you are able to automate the deployment of an infrastructure, application, and business process by programming scripts, based on the specified requirements of a small SME.*

Automation means reducing manual work through scripting. In the context of this project that means writing Python scripts that collect system metrics, store them persistently, and provide a CLI interface to retrieve and analyze the data.

For CS1 this is the area where I have the least progress. The Python scripting tasks have not been started yet. The plan is to build a monitoring script in three stages matching Tasks 5, 10, and 11.

### Case Study 1

Current level: Orienting

No implementation has been done for this LO yet. I have a clear plan for what needs to be built but no evidence to show at this point.

#### Next Steps

Start with Task 5 — write a basic Python script that takes hostname, IP, and metric inputs and displays them formatted. Then build on that for Task 10 by adding psutil measurements, disk storage with timestamps, and CLI modes. Then upgrade to SQLite storage for Task 11. Set up a GitLab repository for version control.

#### Reflection

Not started yet so there is nothing meaningful to reflect on. This section will be updated once the scripting tasks are completed.

### Evidence Overview

No evidence yet. To be added after completing Tasks 5, 10, and 11.

---

## Learning Outcome 4: Manage and Control Basics

> *After conducting research, you are able to design an infrastructure based on the specified requirements of a small SME that considers certain management aspects and processes and complies with local laws and regulations.*

This LO is about thinking beyond the technical build and considering how the infrastructure is managed, what processes exist around it, and how decisions are justified in an organizational context. It covers planning, risk management, stakeholder communication, and process design.

For CS1 I completed a full project analysis, stakeholder analysis, and requirements analysis. I also presented the project context in the professional Show and Grow session. The ITIL process design covering incident and change management is still pending.

### Case Study 1

Current level: Beginning

The analysis and planning documents are complete and well-structured. They show I can identify stakeholders, analyze risks, prioritize requirements, and frame infrastructure decisions in an organizational context. The missing piece is the ITIL process design which is a direct requirement for this LO.

@Stakeholder Analysis covers stakeholder identification, power-interest matrix, communication plan, and risk assessment per group. @Project Analysis includes the health check, MoSCoW prioritization, risk analysis, and value scorecard. @Requirements Analysis maps organizational requirements to technical solutions including management and monitoring requirements REQ-S2P1-07, 08, and 09. @Show & Grow Professional demonstrates professional communication of the project context and design rationale.

#### Next Steps

Complete the ITIL process design covering incident management flow and change management flow. Link both back to the stakeholder analysis as required by Task 12.

#### Reflection

The stakeholder analysis was useful for making me think about who the infrastructure actually serves and why. It changed how I framed some design decisions. For example the public VLAN isolation is not just a technical choice — it directly addresses the visitor stakeholder group's privacy and security concerns. Making those connections explicitly in the documentation made the reasoning behind technical decisions clearer.

### Evidence Overview

- @Stakeholder Analysis: Full stakeholder identification, power-interest matrix, communication plan, and risk assessment.
- @Requirements Analysis: REQ-S2P1-07, 08, and 09 cover monitoring, automation, and management process requirements.
- @Project Analysis: Health check, MoSCoW prioritization, risk analysis, cost considerations, and value scorecard.
- @Show & Grow Professional: Presentation covering the what, why, and how of the project from a professional perspective.

---

## Learning Outcome 5: Professional Standard

> *You apply professional practice, both individually and in teams, in the areas of project organisation, communication with stakeholders, exploratory research, and reporting.*

Being professional means organizing yourself, doing proper research before making decisions, communicating clearly, and documenting in a way that someone else can follow and verify. It runs through everything in the project, not just the final deliverables.

For CS1 I followed a structured phased workflow, maintained a research log throughout the project, kept consistent documentation across all documents, tracked all tasks in a planning document, and presented progress in two Show and Grow sessions.

### Case Study 1

Current level: Beginning

The documentation quality and research approach are the strongest parts of this LO. Every major technical decision has a corresponding research entry and the documents follow a consistent professional structure. The areas that still need work are completing the remaining documents and filling in the reflection sections at the end of the project.

@Research Doc shows structured use of research throughout the project with six entries covering all major technical decisions. @Project Planning defines the phased workflow and task management approach. @Task Planning shows continuous task tracking throughout the project. @Requirements Analysis and @Stakeholder Analysis demonstrate structured professional analysis. @Show & Grow Professional and @Show & Grow Technical show professional communication of project progress. @Workshop GEN AI and @Workshop DOT Framework show participation in professional development workshops.

#### Next Steps

Complete all pending documentation sections. Finalize the reflection sections in the learning goals. Ensure all evidence has proper descriptions in the portfolio.

#### Reflection

Keeping a research log during the project was more useful than I expected. It forced me to articulate why I was making certain choices instead of just doing things. It also made the documentation process easier because the reasoning was already written down when I needed it. The Show and Grow sessions were a good reminder that communicating technical work to others requires a different way of thinking than just building it.

### Evidence Overview

- @Research Doc: Six research entries documenting the sources and reasoning behind all major technical decisions.
- @Project Planning: Phased workflow from requirement analysis to finalization with defined activities and outputs per phase.
- @Workshop GEN AI: Workshop participation showing professional development and reflection on AI tools in an IT context.
- @Workshop DOT Framework: Workshop participation showing structured research methodology.
- @Task Planning: Continuous self-managed task tracking showing organized professional workflow.
- @Requirements Analysis: Structured professional analysis connecting organizational needs to technical solutions.
- @Project Analysis: Professional project analysis using standard methods including MoSCoW and risk assessment.
- @Stakeholder Analysis: Structured stakeholder identification, power matrix, communication plan and risk assessment.
- @Show & Grow Professional: Professional presentation of project context and design decisions.
- @Show & Grow Technical: Technical presentation of implementation progress.

---

## Learning Outcome 6: Personal Leadership

> *You take the initiative in asking for, and reflecting on, feedback. You identify your own core values as the basis for your study career and professional development.*

Personal leadership means owning your own learning. Not waiting for someone to tell you what to do when things break or when you do not understand something. It also means being honest about where you are and where you need to go.

For CS1 I set concrete learning goals at the start of the semester, ran into serious problems during implementation, researched solutions independently, adapted my approach multiple times, and documented the process honestly.

### Case Study 1

Current level: Beginning

I showed initiative when things broke. The DC failing multiple times could have been a stopping point but instead I researched recovery options, tried alternatives like Samba, and eventually rebuilt and moved forward. Research entries 2 and 3 specifically document this process. The honest gap is that the reflection sections in the learning goals document are not yet written and the full picture of personal development will only be visible once those are completed.

@Semester Learning Goals shows five concrete goals set at the start of the semester with measurable success criteria. @Research Doc entries 2 and 3 specifically show personal initiative — I identified problems, researched alternatives, tried them, and adapted based on what worked. @Project Planning shows structured self-organization throughout the project. @Workshop DOT Framework and @Task Planning show continued professional engagement and self-management.

#### Next Steps

Fill in the reflection sections in the Semester Learning Goals document at the end of the semester. Seek teacher feedback on the current portfolio and use it to improve.

#### Reflection

The moments where things went wrong were the most valuable learning experiences of CS1. The DC breaking taught me more about AD than a smooth implementation would have. Researching pfSense alternatives and Samba taught me about the broader landscape of tools even though I did not end up using them. The willingness to try things and accept that they might not work is something I want to carry forward into future case studies.

### Evidence Overview

- @Semester Learning Goals: Five personal learning goals with target outcomes, concrete actions, success criteria, and reflection sections for end of semester.
- @Research Doc: Entries 2 and 3 specifically document personal initiative, problem solving under pressure, and adapting approach based on research outcomes.
- @Project Planning: Shows self-organized structured approach to project management throughout CS1.
- @Workshop DOT Framework: Participation showing structured approach to research methodology as part of personal professional development.
- @Task Planning: Continuous self-managed task tracking showing personal accountability throughout the project.