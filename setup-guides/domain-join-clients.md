# Domain Join – Client Machines

## Purpose
This document describes the process used to join Windows client machines to the Active Directory domain. Domain-joined clients authenticate against the Domain Controller and represent end-user workstations in the enterprise lab environment.

Sensitive credentials and system-specific values are intentionally excluded.

---

## Client System Overview
- Operating System: Windows 11
- Role: Domain-joined workstation
- Authentication Source: Active Directory
- Domain: `corp.local`

These machines simulate employee workstations within the organization.

---

## Prerequisites
Before joining a client machine to the domain, the following prerequisites were verified:

- Client connected to the internal lab network
- Domain Controller reachable on the network
- DNS configured to point to the Domain Controller
- Client system time synchronized with the Domain Controller
- Local administrative access available on the client

---

## DNS Configuration
DNS configuration is critical for successful domain joins.

### Validation Steps
- Client DNS settings configured to use the Domain Controller
- Domain name resolution verified
- Domain Controller hostname successfully resolved

Improper DNS configuration is the most common cause of domain join failures.

---

## Domain Join Process

### System Configuration
The client machine was configured to join the domain through Windows system settings. During this process:
- The domain name was specified
- Domain credentials were used to authorize the join
- The system was restarted to apply changes

---

## Post-Join Verification

### Authentication Testing
After reboot, domain authentication was validated by:
- Logging in with a domain user account
- Confirming domain name appears on the login screen
- Verifying successful login without errors

### System Validation
Additional checks performed:
- Client appears in Active Directory Users and Computers
- Client assigned to appropriate container
- Network connectivity remains intact

---

## User Experience
Once joined:
- Users authenticate using domain credentials
- Centralized identity management is enforced
- Workstations behave as managed domain assets

Login window for user Stacy Watson:
<img width="1025" height="772" alt="domain-login" src="https://github.com/user-attachments/assets/a92749f5-850e-4153-b82c-6303615bd560" />

> Note: The standard domain user account (Stacy Watson) does not have sufficient privileges to access certain system and security settings. A Help Desk account was used to validate domain membership through system settings. This behavior is expected and demonstrates role-based access control and least-privilege enforcement.
<img width="1025" height="767" alt="domain-membership-helpdesk" src="https://github.com/user-attachments/assets/23c06bc6-ef68-487c-a07b-9717f7092193" />


---

## Security Considerations
- Domain credentials are required for authentication
- DNS misconfiguration can expose authentication failures
- Domain membership enables centralized policy enforcement
- Local administrator access is limited post-join

---

## Common Issues Encountered
- DNS pointing to an external resolver
- Time synchronization issues
- Incorrect domain name entry
- Network connectivity problems

Resolution of these issues is documented in the troubleshooting section.

---

## Limitations
- Clients are joined to a single domain
- No Group Policy restrictions applied yet
- No endpoint monitoring configured

---

## Future Enhancements
- Apply Group Policy Objects (GPOs)
- Implement login auditing
- Add endpoint security monitoring
- Test role-based access restrictions
