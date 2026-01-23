# Ubuntu osTicket Installation Guide

## Purpose
This document outlines the process used to install and configure the osTicket help desk system on an Ubuntu Server. The setup is intended for an internal lab environment and demonstrates Linux system administration, web service configuration, and integration with an enterprise-style IT workflow.

Sensitive credentials, secrets, and access URLs are intentionally excluded.

---

## System Overview
- Operating System: Ubuntu Server
- Application: osTicket
- Web Server: Apache
- Database: MariaDB
- Language Runtime: PHP

The Ubuntu server hosts the help desk platform used by internal users and IT staff.

---

## Prerequisites
Before installing osTicket, the following prerequisites were met:

- Ubuntu Server installed and updated
- Network connectivity to the internal lab network
- Static IP address assigned
- Administrative (sudo) access available
- System hostname configured

---

## Web Stack Preparation

### Apache Web Server
Apache was installed and configured to serve web content for the help desk application. The service was verified to start successfully and listen on the appropriate ports.

### PHP Runtime
PHP and required extensions were installed to meet osTicket requirements. PHP configuration was validated to ensure compatibility with the application.

### Database Server
MariaDB was installed and secured. A dedicated database and database user were created for osTicket to enforce separation of application data.

---

## osTicket Installation

### Application Setup
The osTicket application files were deployed to the Apache web root. File ownership and permissions were configured to allow the web server to operate securely.

### Web-Based Installation
The osTicket web installer was used to:
- Define help desk settings
- Connect to the backend database
- Create the initial administrative account

Upon completion, the installer was removed to prevent reconfiguration.

---

## Post-Installation Configuration

### File Permissions
Permissions were adjusted to:
- Prevent unauthorized access
- Protect configuration files
- Ensure proper application operation

### Application Validation
The following checks were performed:
- osTicket loads successfully in the browser
- Admin dashboard accessible
- Ticket submission functional
- No PHP or Apache errors present

---

## Integration with Lab Environment
osTicket was configured to operate within the internal domain environment:
- Internal email identities used for departments
- HTTPS enabled using a self-signed certificate
- No external email services integrated

This ensures the help desk functions entirely within the lab network.

---

## Security Considerations
- Least-privilege permissions applied
- Database access restricted to osTicket user
- Installer files removed after setup
- HTTPS used to encrypt traffic
- No public exposure of the service

---

## Common Issues Encountered
- Permission errors preventing installer access
- Missing PHP extensions
- Database connection misconfiguration
- Apache service conflicts

Resolutions to these issues are documented in the troubleshooting section.

---

## Limitations
- No external email ticket intake
- No Active Directory authentication integration
- Self-signed SSL certificate
- Single-server deployment

---

## Future Enhancements
- Integrate osTicket with Active Directory
- Add centralized logging and monitoring
- Containerize the application
- Implement email-based ticket intake
