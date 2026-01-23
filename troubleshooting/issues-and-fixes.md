# Troubleshooting – Issues and Resolutions

## Purpose
This document captures common issues encountered during the setup of the Active Directory and osTicket lab environment, along with their root causes and resolutions. Documenting these issues demonstrates real-world problem-solving, troubleshooting methodology, and operational awareness.

Sensitive information, credentials, and system-specific secrets are intentionally excluded.

---

## Issue: Client Unable to Join Domain

### Symptoms
- Domain join fails during setup
- Error indicating the domain cannot be contacted
- Client unable to locate Domain Controller

### Root Cause
- Client DNS configured to use an external resolver instead of the Domain Controller

### Resolution
- Updated client DNS settings to point directly to the Domain Controller
- Verified name resolution for the domain

### Lesson Learned
Active Directory is tightly coupled with DNS. Incorrect DNS configuration is the most common cause of domain join failures.

---

## Issue: osTicket Website Not Loading After Installation

### Symptoms
- Web page fails to load
- Blank page or server error displayed

### Root Cause
- Apache service not properly configured or required PHP extensions missing

### Resolution
- Verified Apache service status
- Installed missing PHP dependencies
- Restarted web services

### Lesson Learned
Web applications depend heavily on correct service configuration and runtime dependencies.

---

## Issue: HTTPS Enabled but Browser Shows “Not Secure”

### Symptoms
- osTicket loads over HTTPS
- Browser displays certificate trust warning

### Root Cause
- SSL certificate is self-signed and not issued by a trusted Certificate Authority

### Resolution
- Verified SSL configuration was functioning correctly
- Confirmed encryption was active
- Documented expected browser behavior

### Lesson Learned
Certificate trust and encryption are separate concerns. Self-signed certificates still encrypt traffic but are not trusted by default.

---

## Issue: osTicket Admin Portal Inaccessible

### Symptoms
- User portal accessible
- Admin control panel unavailable

### Root Cause
- Incorrect access path or permissions
- Confusion between user and admin interfaces

### Resolution
- Verified correct admin access method
- Confirmed administrative account permissions

### Lesson Learned
Many enterprise applications separate user and administrative interfaces, which can lead to confusion during initial setup.

---

## Issue: osTicket Email Address Rejected During Configuration

### Symptoms
- Email address flagged as invalid
- Configuration could not be saved

### Root Cause
- Email format did not meet application validation requirements

### Resolution
- Adjusted email format to meet osTicket validation rules
- Used internal domain-based email structure

### Lesson Learned
Even in lab environments, applications enforce strict input validation.

---

## Issue: Tickets Not Routed to Expected Department

### Symptoms
- Tickets appear in incorrect department
- Agents unable to view submitted tickets

### Root Cause
- Department assignment misconfigured
- Default routing rules not aligned with expectations

### Resolution
- Reviewed department configuration
- Updated ticket routing logic
- Verified agent department assignments

### Lesson Learned
Proper ticket routing depends on consistent department and role configuration.

---

## Issue: Permissions Prevent osTicket Installer from Completing

### Symptoms
- Installer fails to proceed
- File or directory permission errors displayed

### Root Cause
- Incorrect file ownership or permissions on osTicket directories

### Resolution
- Adjusted file permissions to allow installer access
- Hardened permissions post-installation

### Lesson Learned
Linux file permissions must balance security and functionality during application installation.

---

## General Troubleshooting Approach
The following methodology was applied consistently throughout the project:

1. Identify symptoms clearly
2. Isolate the affected component
3. Validate configuration against expected behavior
4. Apply minimal corrective changes
5. Re-test and document results

---

## Future Improvements
- Create automated validation checks
- Implement centralized logging for faster diagnosis
- Add monitoring alerts for critical services
- Expand troubleshooting documentation as the environment grows
