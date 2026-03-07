
**Name:** David Hadzhiivanov  
**Student Number:** 570330

---

# Introduction

This document records the research conducted during the development of the IT infrastructure for *The Knowledge Hub*. The purpose of this research log is to document the topics that required further investigation, the resources used to understand them, and how the research influenced the technical decisions made during the project.

---

# Reason for Research

During the implementation of the infrastructure, some technologies and design decisions require additional research. This research helps ensure that the chosen solutions follow best practices and that the implementation is technically correct.

The research process also supports learning objectives by documenting how new knowledge was acquired and applied during the project.

---

# Research Topics

---

## Research Entry 1

### Topic
Network topology design.

### Reason for Research
I needed to design a segmented network topology for the *KnowledgeHub Library*.

### Research Sources

| Type    | Source                                                                                                                    | Description                                                                |
| ------- | ------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Website | [Hierarhical Internetworking Model](https://en.wikipedia.org/wiki/Hierarchical_internetworking_model)                     | Used to understand the 3 layer topology model                              |
| Website | [Collapsed Core and 3 Layer Architectures](https://study-ccna.com/collapsed-core-and-three-tier-architectures/)           | Used to compare and understand both the 3 layer topology model and 2 layer |
| Website | [Design Fundamentals](https://www.cisco.com/c/en/us/td/docs/solutions/CVD/Campus/cisco-campus-lan-wlan-design-guide.html) | Used to understand the design fundamentals and planning for scalability    |
| Website | [Router on a Stick](https://en.wikipedia.org/wiki/Router_on_a_stick)                                                      | Used to understand the logic behind having a router on a stick             |
| AI      | [ChatGPT](https://chatgpt.com)                                                                                            | Used to confirm my choice and do in depth explanations                     |

### Key Findings

Summary of the most important information discovered during the research.

-  Following a 2 layer design, despite the issues of less resiliency and low redundancy, still retains the ability to upscale the network in the future.
-  A 2 layer design is much cheaper than a 3 layer design and easier to maintain which is more fitting for the scale of the project
-  A router on a stick provides no advantage over having a layer 3 switch do the inter VLAN routing and it may even create a bottleneck. A router is best used for firewall enforcement for external traffic but a router on a stick will teach me tagging, setting up trunk ports, and the routing part.

### Application to the Project

Explanation of  how the research influenced my implementation.

- Used VLAN segmentation to separate staff, server, public, and DMZ networks
- Implemented pfSense firewall rules between network zones and set up trunking.
- Decided to use router on a stick and do routing via the firewall due to the scale of the project and necessity requirements.

---

---

# Conclusion

The research documented in this file supports the technical decisions made during the case study. By recording the topics investigated, the sources used, and the conclusions drawn, the project demonstrates a structured approach to learning and problem solving.

This document will continue to be updated as new technologies and implementation challenges arise during the development of the infrastructure.