
**Name:** David Hadzhiivanov  
**Student Number:** 570330

---

# Table of Contents

- [[#1. Introduction|1. Introduction]]
    - [[#2. Context|2. Context]]
    - [[#3. Research Questions|3. Research Questions]]
    - [[#3.1 Main Research Question|3.1 Main Research Question]]
        - [[#3.1.1 Sub-Questions|3.1.1 Sub-Questions]]
    - [[#4. Plan to Answer the Research Questions|4. Plan to Answer the Research Questions]]
    - [[#5. Research Pattern & Strategy|5. Research Pattern & Strategy]]
- [[#6. Research Topics|6. Research Topics]]
    - [[#6.1 Research Entry 1|6.1 Research Entry 1]]
        - [[#6.1.1 Topic|6.1.1 Topic]]
        - [[#6.1.2 Reason for Research|6.1.2 Reason for Research]]
        - [[#6.1.3 Research Sources|6.1.3 Research Sources]]
        - [[#6.1.4 Key Findings|6.1.4 Key Findings]]
        - [[#6.1.5 Application to the Project|6.1.5 Application to the Project]]
    - [[#6.2 Research Entry 2|6.2 Research Entry 2]]
        - [[#6.2.1 Topic|6.2.1 Topic]]
        - [[#6.2.2 Reason for Research|6.2.2 Reason for Research]]
        - [[#6.2.3 Research Sources|6.2.3 Research Sources]]
        - [[#6.2.4 Key Findings|6.2.4 Key Findings]]
        - [[#6.2.5 Application to the Project|6.2.5 Application to the Project]]
    - [[#6.3 Research Entry 3|6.3 Research Entry 3]]
        - [[#6.3.1 Topic|6.3.1 Topic]]
        - [[#6.3.2 Reason for Research|6.3.2 Reason for Research]]
        - [[#6.3.3 Research Sources|6.3.3 Research Sources]]
        - [[#6.3.4 Key Findings|6.3.4 Key Findings]]
        - [[#6.3.5 Application to the Project|6.3.5 Application to the Project]]
    - [[#6.4 Research Entry 4|6.4 Research Entry 4]]
        - [[#6.4.1 Topic|6.4.1 Topic]]
        - [[#6.4.2 Reason for Research|6.4.2 Reason for Research]]
        - [[#6.4.3 Research Sources|6.4.3 Research Sources]]
        - [[#6.4.4 Key Findings|6.4.4 Key Findings]]
        - [[#6.4.5 Application to the Project|6.4.5 Application to the Project]]
- [[#7. Conclusion|7. Conclusion]]

---

# 1. Introduction

This document records the research conducted during the development of the IT infrastructure for *The Knowledge Hub*. The purpose of this research log is to document the topics that required further investigation, the resources used to understand them, and how the research influenced the technical decisions made during the project.

---

## 2. Context

Libraries typically provide public access computers while also maintaining internal administrative systems. Because these systems serve different types of users, the network must separate traffic to prevent security risks.

Public computers should not have access to internal services such as file servers or domain controllers. At the same time, staff members must be able to access internal resources and the internet without restrictions.

To address these requirements, the network must implement proper segmentation, routing, and firewall controls.

---

## 3. Research Questions

## 3.1 Main Research Question

How can a segmented and secure network be designed for a small library environment using VLANs, firewall rules, and centralized services?

### 3.1.1 Sub-Questions

1. How can VLANs be used to separate staff, servers, and public computers?
2. How should inter-VLAN routing be implemented in the network?
3. How can firewall policies protect internal systems from public users?
4. How should servers be placed within the network to maintain security and accessibility?
5. What is an efficient design for the library's needs?

---

## 4. Plan to Answer the Research Questions

To answer the research questions, multiple networking concepts will be researched and analyzed. These concepts will then be applied to the network design.

The research focuses on:

- VLAN segmentation
- Firewall-based network security
- Network routing strategies
- Server placement and DMZ architecture
- Topology layout

After researching these topics, the results will be applied to the design of the network architecture used in the project.

---

## 5. Research Pattern & Strategy

The research follows a **problem-solution approach**.

First, the network requirements and potential security risks are identified. After that, networking concepts and best practices are studied to determine how these issues can be addressed.

Information is gathered from networking documentation, course materials, and technical resources related to network architecture and security.

The research focuses on identifying practical solutions that can be implemented in the simulation environment.

---

# 6. Research Topics

## 6.1 Research Entry 1

### 6.1.1 Topic

Network topology design.

### 6.1.2 Reason for Research

I needed to design a segmented network topology for the *KnowledgeHub Library*.

### 6.1.3 Research Sources

| Type    | Source                                                                                                                    | Description                                                                |
| ------- | ------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Website | [Hierarhical Internetworking Model](https://en.wikipedia.org/wiki/Hierarchical_internetworking_model)                     | Used to understand the 3 layer topology model                              |
| Website | [Collapsed Core and 3 Layer Architectures](https://study-ccna.com/collapsed-core-and-three-tier-architectures/)           | Used to compare and understand both the 3 layer topology model and 2 layer |
| Website | [Design Fundamentals](https://www.cisco.com/c/en/us/td/docs/solutions/CVD/Campus/cisco-campus-lan-wlan-design-guide.html) | Used to understand the design fundamentals and planning for scalability    |
| Website | [Router on a Stick](https://en.wikipedia.org/wiki/Router_on_a_stick)                                                      | Used to understand the logic behind having a router on a stick             |
| AI      | [ChatGPT](https://chatgpt.com)                                                                                            | Used to confirm my choice and do in depth explanations                     |

### 6.1.4 Key Findings

Summary of the most important information discovered during the research.

-  Following a 2 layer design, despite the issues of less resiliency and low redundancy, still retains the ability to upscale the network in the future.
-  A 2 layer design is much cheaper than a 3 layer design and easier to maintain which is more fitting for the scale of the project
-  A router on a stick provides no advantage over having a layer 3 switch do the inter VLAN routing and it may even create a bottleneck. A router is best used for firewall enforcement for external traffic but a router on a stick will teach me tagging, setting up trunk ports, and the routing part.

### 6.1.5 Application to the Project

Explanation of  how the research influenced my implementation.

- Used VLAN segmentation to separate staff, server, public, and DMZ networks
- Implemented pfSense firewall rules between network zones and set up trunking.
- Decided to use router on a stick and do routing via the firewall due to the scale of the project and necessity requirements.

---

## 6.2 Research Entry 2

### 6.2.1 Topic

pfSense replacement

### 6.2.2 Reason for Research

PfSense doesn't allow for configuration through the CLI, so im looking for a free alternative with similar capabilities and fully configurable through the CLI.

The reason i don't want to use pfsense through the web interface as it is supposed to, is because it is extremely slow and hindering my productivity.

### 6.2.3 Research Sources

| Type          | Source                                                                              | Description                                                |
| ------------- | ----------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Documentation | [VyOS Documentation](https://docs.vyos.io/en/latest/)                               | Read the documentation to see whether it will fit my needs |
| Website       | [Top 7 Software](https://cloudswit.ch/blogs/7-best-open-source-router-os-software/) | Comparison between the available router software           |


### 6.2.4 Key Findings

-  I compared the top software that were recommended
-  Decided to try VyOS and OPNsense

### 6.2.5 Application to the Project

VyOS is a very extensive machine capable of configuration entirely through the CLI. The problem with it is that the documentation is a bit vague for my liking and it requires expertise to use which i don't have yet.

When it comes to OPNSense, i tried installing it in my environment but it just corrupted my volume on educloud leading to more problems so i decided to ditch it and just continue using pfSense as intended by the case study.

---

## 6.3 Research Entry 3

### 6.3.1 Topic

File server and AD DC implementation

### 6.3.2 Reason for Research

The windows virtual machine on GNS3 is broken and gets corrupted all the time whenever i implement some changes resetting my progress to 0 every time, so i need another way to implement the file server and domain controller so that i don't need a windows server VM as i intended to have in the first place.

### 6.3.3 Research Sources

| Type          | Source                                                                                                               | Description                                                         |
| ------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| Documentation | [Samba By Ubuntu](https://ubuntu.com/server/docs/how-to/samba/provision-samba-ad-controller/)                        | Guide on provisioning a Samba AD DC                                 |
| Documentation | [Samba Official Wiki](https://wiki.samba.org/index.php/Setting_up_Samba_as_an_Active_Directory_Domain_Controller)    | Further documentation about Samba                                   |
| Tutorial      | [Didi - The SysAdmin](https://didi-thesysadmin.com/2025/11/23/build-samba-active-directory-domain-controller-linux/) | Guide to Samba on Linux                                             |
| AI            | [Claude](https://claude.ai)                                                                                          | Used to confirm the choice i will make along with additional advice |

### 6.3.4 Key Findings

-  Samba is used by default on windows server for AD DC and file sharing
-  Samba can be used on an Ubuntu VM

### 6.3.5 Application to the Project

Since Samba can be used on an Ubuntu machine, it is good to try and complete my project tasks this way. 

The good thing about this discovery is that scripting will become much easier since setting up Samba requires the use of the Linux CLI meaning that i dont need a desktop environment to use it. It is going to be a bit harder to get the gist of it when it comes to configuration but by following the guides made [here](https://didi-thesysadmin.com/2025/11/23/build-samba-active-directory-domain-controller-linux/) it will be pretty straight forward.

---
## 6.4 Research Entry 4

### 6.4.1 Topic

Active Directory group nesting and permission management.

### 6.4.2 Reason for Research

I needed to design a structured and maintainable permission model for the file server at The Knowledge Hub, using Active Directory security groups to control access to shared folders based on staff roles.

### 6.4.3 Research Sources

| Type    | Source                                                                                   | Description                                                                                     |
| ------- | ---------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Website | [Artiste1](https://artiste1.com/admin/active-directory/agdlp-model)                      | Understanding and Implementing the AGDLP Model in Active Directory                              |
| Website | [Wikipedia](https://en.wikipedia.org/wiki/AGDLP)                                         | Useful wiki but a bit short                                                                     |
| Website | [ManageEngine](https://www.manageengine.com/products/ad-manager/blog/what-is-agdlp.html) | Advantages and disadvantages of using it along with best practices                              |
| AI      | [Claude](https://claude.ai)                                                              | Used to explain the reasoning behind group nesting and how it applies to the file server design |

### 6.4.4 Key Findings

- AGDLP stands for Accounts; Global groups; Domain Local groups; Permissions. It is a Microsoft-recommended pattern for organizing AD permissions in a scalable and maintainable way.
- Assigning permissions directly to user accounts creates management overhead - every staff change requires manual updates to folder permissions on the server itself.
- Group nesting solves this by separating identity management from permission management. I manage who belongs to a group in one place; the permissions on the resource never need to change.
- For a small organization like the Knowledge Hub, a simplified version of AGDLP is sufficient - Global security groups are assigned permissions directly, without Domain Local groups as an intermediate layer. This keeps the structure simple while retaining the core benefit of role-based access.

### 6.4.5 Application to the Project

- Created `IT_Admins`, `Management_Group`, and `Operations_Group` as Global security groups reflecting the three staff roles in the organization.
- Created `FileServer_Read` and `FileServer_Modify` as permission-specific groups, containing the role groups rather than individual users.
- This means staff changes only require updating one group membership - the file server permissions remain untouched regardless of who joins or leaves.

This simplifies giving permissions and taking them away later on.

---

# 7. Conclusion

The research documented in this file supports the technical decisions made during the case study. By recording the topics investigated, the sources used, and the conclusions drawn, the project demonstrates a structured approach to learning and problem solving.

This document will continue to be updated as new technologies and implementation challenges arise during the development of the infrastructure.