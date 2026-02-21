---
tags:
  - Documentation
---
## PPDIOO Lifecycle Model

**PPDIOO** is a life-cycle model. It is a continuous process of improvement developed by CISCO.

It is used to create a plan of tasks, milestones and responsibilities. If the project is repeatable, the plan is also reusable.

**PPDIOO** is an acronym for Prepare, Plan, Design, Implement, Operate, Optimise.

- **Prepare** - Determine The organization's goals and create a high-level design.
- **Plan** - Identify network/infrastructure requirements and perform gap analysis.
- **Design** - Create a detailed technical design.
- **Implement** - Configure and implement the network/infrastructure.
- **Operate** - Perform day-to-day management.
- **Optimise** - Proactive management and design improvements.

#### Advantages

- **Lower TCO** - Planning eliminates guesswork. This allows you to use the right equipment for the job. This avoids the biggest (overkill) or cheapest (under-specified) equipment. This minimizes redesigns, upgrades and waste
- **Availability and performance** - High availability in infrastructure prevents costly downtime
- **Business Agility** - Understanding where the business wants to go can help future-proof the infrastructure. This avoids the need for a complete redesign in the near future.

![[Pasted image 20260211143403.png]]

### Prepare

_The preparation phase is about identifying organizational requirements and goals_

The preparation phase gathers the organizational requirements. Then use these requirements as the basis for a high-level design. Next, create a business case to justify the project.

#### Step 1 - Business Requirements

Collect the business requirements. This includes immediate requirements, as well as the long-term vision and technology strategy.

It is important to understand business goals and strategy. This means having discussions with management about their plans for the business. For example, they may have a five-year plan to release a web-based application to the public. The business will need a data center to host the application.

To understand immediate requirements, talk to the users. Try to understand what works for them and what doesn't. An example might be WiFi coverage. Users may be able to tell you where they find black spots or areas with poor performance. Talking to users helps to remove any assumptions you may have.

#### Step 2 - High Level Design

Use the requirements and goals to develop a high-level architecture. This is a conceptual model of how the solution would work. There does not need to be much detail, if any.

This architecture may not include the entire end-game. Think about the five-year plan to release a web application. The high level design may be a data center with internet links, routers and switches, and some servers. The design should be scalable, and put the network in a good position to start app development. Over time, the data center can scale out with more servers, bigger links, and so on.

#### Step 3 - Financial Business Case

The financial business case document lists out the **requirements for the network**. It addresses how to solve challenges, and **estimates a budget** to complete the project. It is **important** to justify the project, by explaining **how it will help the business**. Include an outline of what would happen if the business were to do nothing, and the impact on the business.

It's also good to include a few options. You may include the premium option to cover every need, and a cheap option to cover the basics. There could also be a 'middle-ground' option, which is likely to be the most popular. For each option, include risks and cost.

As the designer, this removes some risk and responsibility from you. It's up to management and the finance team to approve or deny the project. You have outlined the project, and the risks involved. It's up to management to decide what risk to accept.

### Plan

_The plan phase identifies technical requirements and required resources_

During the planning phase, audit the current network, and compare to the high level design. This is the gap analysis. After completing this, create a project plan.

#### Step 1 - Assess the Current System

Audit the current network. Documentation should be helpful, but doesn't always exist. Even when there is documentation, it may not be up to date.

Collect information such as the hardware and the software in the network. This includes version details and licenses. Document link sizes (WAN and internet), service providers, and costs. Measure the performance of the current network. Performance measurement may include discussions with users, around their perceptions and 'pain-points'.

The information collected here provides a baseline. Use this later to compare how successful the project has been. The baseline is also used later to develop a test plan.

#### Step 2 - Create a Gap Analysis

A gap analysis measures the difference between the current and planned network. It is a map of 'where we are' and 'where we want to be'. Compare this against best-practices for best results.

The gap analysis determines the detail around what needs to change in the network.

#### Step 3 - Create a Project Plan

The gap analysis finds the difference in the current state and the required state. Break this information into tasks, and add them into a project plan.

The project plan should include:

- **Tasks** - A list of what needs to be done
- **Milestones** - The tasks grouped into project phases
- **Responsibilities** - A list of who performs each task
- **Financial Resources** - The cost of each phase of the project. Financial teams like to spread the cost across a project when possible

### Design

_The design phase creates a detailed network design_

Take the business goals, along with the technical requirements. Use this information to create a detailed design.

The detailed design needs to support:

- Availability
- Reliability
- Security
- Scalability
- Performance

This phase yields the detailed design document, and a bill of materials (BOM). The project plan is now updated with more detail.

The design, plan and BOM now needs approval by technical, management, and finance teams.

### Implement

_The Implementation phase moves the design into production_

Use the detailed design to create an implementation plan. This is where the network moves into production.

#### Step 1 - Create an Implementation Plan

Use the project plan and the detailed design to create an implementation plan. This includes change management, maintenance windows, and notification of works to users.

Each step needs to include:

- Task description
- Detailed implementation guidelines
- Estimated time to implement
- Rollback steps
- Reference to design and other documents

#### Step 2 - Verify in the Lab

If possible, start with a lab. This helps to find unexpected errors and resolve them before affecting users.

#### Step 3 - Implement a Pilot

Break a larger project into smaller deployments. For example, the project may be to upgrade firewalls at several branch sites.

When this is the case, start with a pilot deployment. In the example above, this means upgrading the firewall at one branch first. Then test if this is successful.

This will test if there are any issues in a real world environment. If there are serious issues, they will affect a group of users, rather than all users.

This is done by many.

#### Step 4 - Full Deployment

After the lab and pilot irons out the bugs, move to the full scale deployment. on completion, compare it to the baseline created earlier. This will determine if the project has been successful. This also makes sure the project hasn't had a negative effect on the network.

### Optimise

_In the Optimise phase, the design is proactively improved_

The optimise phase is all about proactive management. This means identifying problems before they arise. This is another occasion when the performance baseline is useful.

This may identify needed network improvements. As an example, management may decide they want to install IP telephony.

This is where the lifecycle begins again. Identifying the need here leads back to the Prepare phase to start a new project.

## PBM Lifecycle Model

Cisco's second lifecycle model is PBM. This was created as a simplified way to engage customers in their projects. The PPDIOO phases are still relevant, but they map to three simple phases.

This is easier for customer engagement. Different teams, companies, or consultants, can handle different sections of the project. For example:

1. Consultant-A is designs the solution. This is the **Plan** section
2. Internal IT is implements the solution. This is the **Bulid** section
3. A managed services team operates the solution. This is the **Manage** section

### Plan

The **plan** section includes:

- Strategy and Analysis
- Assessment of the current network
- Design of the revised network

### Build

The **build** section includes:

- Deployment of the new network
- Migration to the new network
- Validation of the new network

### Manage

The **manage** section includes:

- Product Support
- Solution Support
- Optimization
- Operations Management

### Mapping PPE to PPDIOO

As shown below, Each section still maps to PPDIOO. The teams in each PPE phase can refer to their relevant PPDIOO tasks.

![[Pasted image 20260211143342.png]]

## Products

All phases of the PPDIOO model have specific end products. Depending on the project, you will work out the appropriate end products. Be sure to review these with your subject teachers as well.

| **Phase designation**                                                                 | **Organization layer**                                                                                                                                                                      | **Applications layer**                                                                                  | **Tech-low**                                                                   | **Phase (final) product**                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| **Prepare -** Establish the (business) goals, and create a "High Level" design.       | - Userstories<br>- Business-requirements<br>- Moscow-prioritized                                                                                                                            | - Requirements (functional & technical)<br>- Services model explaining how all userstories are covered. | - System-requirements<br>- Conceptual network design                           | **Functional design**                                                                               |
| **Plan -** Identify network and application requirements, and perform a gap analysis. | - Gap analysis<br>- Risk analysis (including information security)                                                                                                                          | - Feasibility Analysis<br>- Deployment strategy                                                         | - Resources Analysis<br>- Feasibility Analysis<br>- Security risk analysis     | **Plan of Action**                                                                                  |
| **Design -** Create a detailed technical design.                                      | - Underpinning non-functional requirements (availability, reliability, security, scalability, performance)<br>- Setting up management processes (according to ITIL, SRE, devops or similar) | - Product architecture<br>- Data storage<br>- Proof of Concept(s)                                       | - Network Design<br>- Network/system architecture<br>- Proof of Concept(s)     | **Technical design**                                                                                |
| **Implement -** set up and roll out.                                                  | - Implementation plan (instead of 'over the wall')<br>- GAP check<br>- Service-level agreement (sla, slo, sli).<br>- Critical performance indicators (KPIs).                                | - GIT with commits<br>- Test report<br>- Deployment                                                     | - OTAP setup<br>- Integration Test                                             | **Implementation Plan**  <br>**Application(s)**  <br>**Network**  <br>**Test reports (acceptance)** |
| **Operate -** performs day-to-day management.                                         | - Management processes                                                                                                                                                                      | - Bug tracking (GIT issue management).<br>- Transfer documentation to management                        | - Monitoring on KPIs<br>- Monitoring at tresholds<br>- Escalation of incidents | **Reports on incident, problem, and change management**                                             |
| **Optimise -** proactive management and improvements.                                 | - Collect new features                                                                                                                                                                      | - Rolling out patches<br>- Improvement Proposal                                                         | - Rolling out patches<br>- Proactively replacing hardware                      | **Patches**  <br>**Reports**  <br>**New features list**                                             |
