
**Name:** David Hadzhiivanov
**Student Number:** 570330

---

# Core Tasks

- [x] Stakeholder & Requirement Analysis ⏫ ✅ 2026-03-20
- [x] Network Foundation ⏫ ✅ 2026-03-20
	- [x] Topology ✅ 2026-03-20
	- [x] VM Roles ✅ 2026-03-20
	- [x] IP Plan ✅ 2026-03-20
	- [x] Connectivity ✅ 2026-03-20
- [x] Central Directory & Internal Network Services ⏫ ✅ 2026-03-20
	- [x] Windows Server VM ✅ 2026-03-20
		- [x] AD DS ✅ 2026-03-20
		- [x] DNS ✅ 2026-03-20
		- [x] OU Structure ✅ 2026-03-20
- [ ] File Server & Monitoring Server ⏫
	- [x] Create file server ✅ 2026-03-20
		- [x] Install and Join to AD ✅ 2026-03-20
	- [ ] Install Linux Monitoring Server
		- [ ] Necessary software
		- [ ] Join to AD
- [ ] Python Environment Setup & Initial Scripting 🔼 
	- [ ] Repository
	- [ ] On all server VMs install Python and Git if necessary
	- [ ] Write a script
		- [ ] Allows the user to enter information about the system that should be monitored
		- [ ] Allows the user to specify a list of system metrics
		- [ ] Display all of the information the user entered in a well-formatted way
		- [ ] Follow PEP8 coding style
- [x] Workstations and Standardization 🔼 ✅ 2026-03-20
	- [x] 2 Win10 VMs ✅ 2026-03-20
		- [x] Auto assignment of drive mappings to fileserver shares ✅ 2026-03-20
		- [x] Disable RegEdit ✅ 2026-03-20
		- [x] Auto force updates ✅ 2026-03-20
		- [x] Exclude Admin Accounts ✅ 2026-03-20
- [ ] Web Server Installation & Configuration ⏫ 
	- [ ] Install Linux VM
		- [ ] Install Apache or Nginx
		- [ ] Host a static page
		- [ ] Self signed certificate
		- [ ] Test access
- [ ] External DNS Server Installation & Configuration ⏫ 
	- [ ] Install Linux Server
		- [ ] Install BIND for DNS
			- [ ] Configure to host a public zone such as knowledgehub.nl
		- [ ] Create an A-record in this public zone (e.g. "library") pointing to the _public_ IP address (from step 2) assigned for external webserver access.
		- [ ] Test name resolution of "library.knowledgehub.nl" from a VM in the simulated internet network, using this DNS server for the query.
- [ ] External Web Server Exposure & Basic Security ⏫ 
	- [ ] NAT
	- [ ] Security hardening on all VMs
- [ ] Continued Scripting 🔼 
	- [ ] Adapt previous code
		- [ ] allows the user to perform measurements of metrics that it recognizes
		- [ ] performs the measurements (by using things like the 'psutil' Python module, or tools offered to you by the operating system)
		- [ ] writes them to permanent storage (disk) including the current date and time and the name of the metric
	- [ ] a different "mode" of execution, that allows the user to retrieve the stored measurements over a certain time-period:
		- [ ] reads them from permanent storage (disk), and filters based on (for example) a given start- and end-time
		- [ ] displays them on screen in a well-formatted fashion
		- [ ] optionally, allows things like calculating an average, or a total, etc. for the displayed statistics
	- [ ] commandline application, that takes it's "instructions" from the commandline or from a configuration file (so NO interactivity, never pauses execution until it's done).
	- [ ] in normal operation doesn't overwrite data already present on permanent storage (disk), only adds to it. Unless you implement a seperate option for the application which the user can use to specify that it SHOULD start with a clean slate.
- [ ] Python Monitoring Scripting 🔼 
	- [ ] all of the data that is recorded by the application, must be stored in a (local) database. SQLite3 is a good fit for this.
	- [ ] Document the script, how it collects data, its output/log format, and how to run it.
- [ ] ITIL Process Design 🔼 
	- [ ] Design a basic Incident Management flow
		- [ ] Define how an "ALERT" from your monitoring script (e.g., low disk space) should be handled.
		- [ ] Outline the key steps (Log, Categorize/Prioritize, Assign, Resolve, Close) and create a simple Incident Ticket template with essential fields.
	- [ ] Design a basic Change Management flow
		- [ ] Using the fileserver implementation (Task 6) as an example, define how a request for a new share should be managed. Outline the steps (Request, Assess, Approve, Implement, Review) and create a simple Change Request form.
	- [ ] Explain how these designed processes directly support the IT needs and address the concerns identified in your Stakeholder Analysis (Task 1).
- [ ] Final Documentation & Reflection ⏫ 
	- [ ] [[#Documentation]]
---

# Documentation

- [x] Analyze Stakeholders ⏫ ✅ 2026-03-07
	- [x] Classify ✅ 2026-03-05
	- [x] Define Interests and Expectations ✅ 2026-03-05
	- [x] Define Roles ✅ 2026-03-05
		- [x] Define Problems ✅ 2026-03-05
		- [x] Define Desires ✅ 2026-03-05
		- [x] Address Requirements ✅ 2026-03-05
		- [x] Define Solutions ✅ 2026-03-05
	- [x] Advanced Analysis ✅ 2026-03-07
		- [x] Power Matrix ✅ 2026-03-07
			- [x] Interpretation ✅ 2026-03-07
	- [x] Communication Plan ✅ 2026-03-07
		- [x] Plan ✅ 2026-03-07
			- [x] Approach ✅ 2026-03-07
	- [x] Risk Analysis ✅ 2026-03-10
		- [x] Risk Assessment ✅ 2026-03-10
			- [x] Evaluation ✅ 2026-03-10

---

- [x] Analyze Requirements ⏫ ✅ 2026-03-07
	- [x] Connect to Learning Outcomes ✅ 2026-03-05

---

- [x] Project Analysis ⏫ ✅ 2026-03-11
	- [x] Health Check ✅ 2026-03-04
		- [x] Issues ✅ 2026-03-04
	- [x] Capability Analysis ✅ 2026-03-04
	- [x] Assess Benefits ✅ 2026-03-04
	- [x] Consider Costs ✅ 2026-03-04
	- [x] Risk Analysis ✅ 2026-03-05
	- [x] MoSCoW ✅ 2026-03-05
	- [x] Value Scorecard ✅ 2026-03-07

---

- [x] Design ⏫ ✅ 2026-03-10
	- [x] Goal? ✅ 2026-03-09
	- [x] Define Architecture ✅ 2026-03-09
	- [x] VLAN & IP Design ✅ 2026-03-09
	- [x] Core Services ✅ 2026-03-09
	- [x] Routing Design ✅ 2026-03-09
	- [x] Security Design ✅ 2026-03-09
		- [x] Segmentation ✅ 2026-03-09
		- [x] Firewall ✅ 2026-03-09
	- [x] Port Allocation ✅ 2026-03-10
	- [x] Firewall Policy Table ✅ 2026-03-10
	- [x] Network Diagram ⏫ ✅ 2026-03-10
	- [x] DC Design ⏫ ✅ 2026-03-20
		- [x] Structure ✅ 2026-03-20
		- [x] Groups ✅ 2026-03-20
	- [x] File Server Design ⏫ ✅ 2026-03-20
		- [x] Structure ✅ 2026-03-20
		- [x] Permissions ✅ 2026-03-20
	- [ ] Web Server Design ⏫ 

---

- [x] Semester Learning Goals ⏫ ✅ 2026-03-07

---

- [x] Research Document 🔼 ✅ 2026-03-11
	- [x] Define Main Project Question ✅ 2026-03-11
		- [x] Sub-Questions ✅ 2026-03-11

---

- [ ] Implementation ⏫

---

- [ ] Validation ⏫ 

---

- [ ] Reflection ⏫ 

---

# Implementation

- [x] Set Topology ⏫ ✅ 2026-03-11
	- [x] Study Topology Practices ✅ 2026-03-11
- [x] Set Up DC1 ⏫ ✅ 2026-03-20
	- [x] Create OUs ✅ 2026-03-20
		- [x] Define User Groups ✅ 2026-03-20
			- [x] Define Users ✅ 2026-03-20
- [x] Set Up File Server ⏫ ✅ 2026-03-20
	- [x] Create Shares ✅ 2026-03-20
		- [x] Role-based access permissions ✅ 2026-03-20
- [ ] Set Up Web Server ⏫ 
	- [ ] Install dependencies
	- [ ] HTTPS
		- [ ] Self-signed cert
- [x] Set Up Web Config 🔼 ✅ 2026-03-20
	- [x] Router ✅ 2026-03-20
	- [x] Switch ✅ 2026-03-20
- [x] Set Up VLANs ⏫ ✅ 2026-03-20
	- [x] Staff ✅ 2026-03-20
		- [x] DHCP ✅ 2026-03-20
	- [x] Servers ✅ 2026-03-20
	- [x] Public PCs ✅ 2026-03-20
		- [x] DHCP ✅ 2026-03-20
	- [x] DMZ ✅ 2026-03-20
- [ ] Roter config ⏫
	- [x] Firewall ✅ 2026-03-20
		- [x] Rules between VLANs ✅ 2026-03-20
	- [ ] NAT
- [ ] Automation 🔼 
	- [ ] Monitoring tool
