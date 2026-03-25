
If youre not attending 3 times in a row - you pay lunch for everyone
If youre late past 9:30 without notice - 
Come on time regularly
Team members will conduct themselves in a professional manner, observing institutional policies given to them at student, faculty and staff orientation.

# Team Policies

### Fonteyn Holiday Parks - Infrastructure Modernisation Project

This document defines the professional standards and policies for our project team. All team members are expected to read, understand, and follow these policies throughout the project.

---

## 1. Communication & Meetings

### 1.1 Daily Standup

- The team holds a daily standup every working day, organised by the Scrum Master.
- Each team member answers three questions: what did I do yesterday, what will I do today, and are there any blockers.
- Standups are kept to a maximum of 15 minutes.
- Absence must be reported to the Scrum Master before the standup starts.

### 1.2 Team Communication

- The primary communication channel for the team is [Yet to be decided].
- All project-related communication happens in the designated team channel, not in private messages, unless the topic is personal.
- Messages must be responded to within one working day.
- Dutch or English may be used, but all official documents and deliverables are written in English.

### 1.3 Client Communication

- All communication with the client (Fonteyn Holiday Parks) goes through the Project Leader.
- No team member contacts the client directly without informing the Project Leader first.
- Emails to the client must be professional in tone and reviewed by at least one other team member before sending.
- Meeting notes are written up and shared with the client within 24 hours of every meeting.

### 1.4 Meetings

- Meetings are scheduled at least 24 hours in advance.
- Every meeting has a set agenda shared beforehand.
- One team member takes notes during each meeting and shares them in the team channel afterwards.
- Team members arrive on time. If running late, notify the team immediately.

### 1.5 Conflict Resolution

- Disagreements are discussed openly and respectfully within the team.
- If a conflict cannot be resolved internally, it is escalated to the proftaak tutor.
- Personal disputes do not belong in team channels.

---

## 2. Security & Access

### 2.1 Account & Credential Management

- Every team member uses a unique account for all project systems. Shared accounts are not permitted.
- Passwords must be at least 12 characters and include uppercase, lowercase, numbers, and a special character.
- Passwords are never shared via chat, email, or any other digital channel.
- A password manager is recommended for storing credentials.

### 2.2 Multi-Factor Authentication

- MFA is mandatory on all accounts that support it, including cloud platforms, version control, and remote access tools.
- MFA must be set up before a team member is granted access to any project system.

### 2.3 Access Control

- Access rights follow the principle of least privilege: each team member only has access to what they need for their role.
- The Security Officer is responsible for managing and reviewing access rights.
- When a team member's role changes, their access rights are updated within 24 hours.
- All access is revoked at the end of the project.

### 2.4 Device Security

- Project work is only carried out on personal or school-issued devices with up-to-date software and antivirus protection.
- Devices must be locked when left unattended, even briefly.
- Public Wi-Fi networks must not be used for project work without a VPN.

### 2.5 Incident Reporting

- Any suspected security incident, such as unauthorised access or a lost device, must be reported to the Security Officer immediately.
- The Security Officer logs all incidents and reports them to the Project Leader.
- Incidents that affect client data are also reported to the Privacy Officer.

---

## 3. Code & Documentation Standards

### 3.1 Version Control

- All code and configuration files are stored in the team's Git repository.
- No one commits directly to the main branch. All changes go through a feature branch and a pull request.
- Pull requests require at least one review and approval from another team member before merging.
- Commit messages are written in English and clearly describe what was changed and why.

### 3.2 Branching Convention

- Branch names follow this format: `role/short-description` (e.g. `devops/setup-cicd`, `network/vlan-config`).
- Feature branches are deleted after merging.
- The main branch always reflects the latest stable, working version of the project.

### 3.3 Code Quality

- Code is written clearly and includes comments where the logic is not self-explanatory.
- No hardcoded credentials, IP addresses, or sensitive values in code. Use environment variables or config files instead.
- Before submitting a pull request, the author tests their own changes.
- The Architect reviews changes that affect the overall infrastructure design.

### 3.4 Documentation

- All technical decisions are documented in the project wiki or in a decisions log (ADR format recommended).
- Network diagrams and system designs are kept up to date by the Architect after every significant change.
- Documentation is written in English, uses plain language, and is stored in the shared project folder.
- The README of the repository contains a clear overview of the project, setup instructions, and role assignments.

### 3.5 File & Folder Naming

- File names use lowercase letters and hyphens, no spaces (e.g. `network-diagram-v2.png`).
- Versioning is added to documents when multiple versions exist (e.g. `design-v1.md`, `design-v2.md`).
- Sensitive files such as keys and certificates are never committed to the repository.

---

## 4. Privacy & GDPR

### 4.1 Responsibilities

- The Privacy Officer is responsible for overseeing GDPR compliance throughout the project.
- All team members are responsible for handling personal data correctly within their own area of work.
- Any task involving personal data must be flagged to the Privacy Officer before starting.

### 4.2 Personal Data Handling

- Personal data is only collected if it is strictly necessary for the project.
- Data is stored in a secure, access-controlled environment. No personal data is stored on personal devices or in personal cloud storage.
- Personal data is never shared with third parties without documented justification and, where required, consent.
- Data is retained only as long as necessary and deleted securely when no longer needed.

### 4.3 Privacy by Design

- Privacy considerations are included from the start of every design or implementation task, not added as an afterthought.
- The Architect consults the Privacy Officer when making infrastructure design decisions that involve personal data flows.
- A Privacy Impact Assessment (PIA) is conducted and documented before the project goes into production.

### 4.4 Data Breach Protocol

- Any (suspected) data breach is reported to the Privacy Officer immediately.
- The Privacy Officer assesses the breach and, if necessary, reports it to the Project Leader and relevant authorities within 72 hours, in line with GDPR requirements.
- All breaches are logged, including those that turn out to be false alarms.

### 4.5 Team Awareness

- All team members complete a basic GDPR awareness check at the start of the project.
- Questions about privacy or data handling are always directed to the Privacy Officer.

---

## Policy Acceptance

All team members are expected to confirm they have read and understood this document at the start of the project. Policies are reviewed at the end of each sprint and updated if needed.

|Name|Role|Date|
|---|---|---|
||Architect||
||Project Leader||
||Scrum Master||
||Network Administrator||
||DevOps Engineer||
||Security Officer||
||Privacy Officer||

_Last updated: March 2026_