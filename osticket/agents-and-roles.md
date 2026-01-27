# osTicket Agents and Roles

## Purpose
This document describes how users, agents, and administrators are structured within the osTicket help desk system. It outlines role separation, account types, and access levels used to simulate a small enterprise IT support environment.

---

## User Types Overview
The help desk environment supports multiple user categories to reflect real-world IT operations:

- Active Directory users
- Help desk agents (Tier 1 support)
- Help desk administrators
- System-level service accounts

Each category is assigned a defined role with scoped access.

---


## Active Directory Users
Active Directory users represent corporate employees who authenticate to domain-joined systems and may interact with the help desk.

### Example Accounts
- Frank Khan (AD)
- Stacy Watson (AD)
- Bruce Wayne (AD)
- Lionel Messi (AD)

**Purpose:**
- Authenticate to Windows domain resources
- Submit help desk tickets
- No direct administrative access in osTicket

---

## Help Desk Agents (Tier 1 Support)
Help desk agents are responsible for handling incoming tickets and providing first-level support.

### Example Agent Role
**IT Help Desk**
- Assigned to the IT department
- Can view, respond to, and close tickets
- Cannot modify system-wide settings
- Limited to assigned departments

---

## Help Desk Administrators
Administrators manage the help desk platform and oversee agents, departments, and system configuration.

### Example Admin Role
**IT Admin**
- Full access to osTicket configuration
- Manages agents and roles
- Configures departments and workflows
- Oversees ticket routing and system behavior

---

## Departments
Departments are configured to simulate internal organizational structure and ticket routing.

### Configured Departments
- Human Resources
- Finance
- Sales
- Information Technology

Each department can have:
- Assigned agents
- Dedicated email addresses
- Custom workflows and auto-responses

---

## Role Separation & Access Control
Role-based access control (RBAC) is used to enforce least privilege:

- Users can submit and view their own tickets
- Agents can manage tickets within assigned departments
- Administrators can modify global settings
- System accounts are isolated from user access

This separation reduces risk and mirrors real enterprise help desk environments.

<img width="1225" height="835" alt="ostickets-agents" src="https://github.com/user-attachments/assets/ebdd0dfb-4818-4a94-8a21-861c1af173b1" />

---

## Security Considerations
- Credentials are not stored in documentation
- No external email services are integrated
- Authentication sources are separated by role
- Administrative access is restricted to designated users

---

## Future Enhancements
- Integrate osTicket agent authentication with Active Directory
- Implement auditing of agent actions
- Enforce stricter role-based permissions
- Centralize logging for help desk activity
