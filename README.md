# Active Directory & Help Desk Simulation Lab

## Overview
This project is a hands-on Active Directory and IT Help Desk simulation built to reflect a small enterprise environment. The lab combines Windows Server Active Directory with a Linux-based help desk ticketing system (osTicket) to demonstrate identity management, user administration, and real-world IT support workflows.

This environment was built from scratch to strengthen my understanding of Windows Server administration, Linux system configuration, and how help desk operations integrate with Active Directory in a corporate setting.

---

## Environment Overview
- One Windows Server Domain Controller
- Multiple domain-joined Windows client machines
- Ubuntu machine hosting osTicket
- Internal DNS and domain-based authentication
- HTTPS enabled using a local/self-signed certificate
- Department-based ticketing workflow (HR-focused)

---

## Technologies Used
- Windows Server 2022
- Active Directory Domain Services
- DNS
- Windows 11 Clients
- Ubuntu Server
- Apache Web Server
- MySQL
- PHP
- osTicket
- OpenSSL (local SSL certificate)
- VMware Workstation

---

## What Was Implemented

### Active Directory
- Created a new Active Directory domain
- Promoted Windows Server to Domain Controller
- Configured DNS automatically during AD DS installation
- Created organizational users for the environment
- Joined Windows client machines to the domain
- Verified domain authentication using AD credentials

---

### osTicket Help Desk
- Installed osTicket on Ubuntu Server using Apache, MySQL, and PHP
- Configured database and file permissions
- Completed web-based osTicket installation
- Enabled HTTPS using a locally generated SSL certificate
- Verified site loads securely (marked not secure due to local CA)

---

### Departments & Email Configuration
- Created an **HR department** in osTicket
- Configured department email addresses using the internal domain (`@corp.local`)
- Removed default IT department and email to keep the environment focused
- Configured auto-response email settings for ticket creation
- Verified internal email format works for osTicket validation

---

### Agents & Access
- Created an administrative agent with full access
- Verified admin agent permissions across departments
- Prepared environment for adding additional agents mapped to Active Directory users
- Confirmed separation between admin portal and client ticket portal

---

### HTTPS Configuration
- Generated a self-signed SSL certificate on Ubuntu
- Configured Apache virtual host to support HTTPS
- Verified HTTPS functionality for osTicket
- Confirmed browser warning is expected due to local certificate authority

---


### Directory Breakdown

| Directory | Purpose |
|--------|---------|
| `architecture/` | Network and Active Directory design |
| `setup-guides/` | Reproducible build documentation |
| `osticket/` | Help desk setup and workflows |
| `screenshots/` | Environment validation |
| `troubleshooting/` | Real-world issues and fixes |


---

## Troubleshooting Examples
Issues encountered and resolved during this build include:
- Invalid email formats rejected by osTicket
- HTTPS not loading due to Apache virtual host misconfiguration
- Browser security warnings caused by self-signed certificates
- Admin portal access issues vs client portal access

Each issue and resolution is documented in the `/troubleshooting` directory.

---

## What This Project Demonstrates
- Practical Active Directory administration
- Linux server configuration in an enterprise context
- Realistic help desk workflows using osTicket
- Understanding of HTTPS and certificate trust
- Troubleshooting skills across Windows and Linux systems
- Documentation of technical decisions and fixes

---

## Future Improvements
- Integrate Active Directory authentication with osTicket
- Add additional departments and role-based access
- Enable centralized logging
- Integrate Splunk for event monitoring
- Simulate common help desk incidents and security events

---

## License
This project is licensed under the MIT License.
