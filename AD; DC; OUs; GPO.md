# What is Active Directory?

Directory service developed by microsoft that helps manage users, computers and other resources on the network. Think of it as a secure, centralized, phonebook for the company's IT environment.

It stores information about:
- Users
- Computers and servers
- Printers
- Shared folders
- Security groups

And it controls:
- Who can log in
- What they can access
- What they are allowed to do

## Core components

### Domain

**Example:**
company.local
school.edu
etc.

All users inside the domain authenticate through AD.

### Domain Controller (DC)

Its the server that runs AD services.

### Organizational Units (OUs)

They help structure objects logically.

**Example:**
Company
	|- HR
	|- IT
	|_ Sales

Different rules can be applied to each department.

### Group Policy (GP)

Allows administrators to enforce settings across users or computers.

**Example:**
Force password complexity
Disable USB drives
Automatically install software
etc.

# Domain Controller

Is a server computer that responds to security authentication request within a computer domain.

Risks:
- A single point of failure
- Once hacked we're fucked

# AD vs DC

- AD is what is called a **directory** service, it **stores objects** 