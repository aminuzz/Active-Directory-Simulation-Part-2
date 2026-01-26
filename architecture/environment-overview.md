# Environment Architecture Overview

## Purpose
This document describes the overall architecture of the Active Directory and Help Desk simulation environment. It outlines the logical design, system roles, and how each component interacts within the lab. The goal of this architecture is to simulate a small enterprise IT environment with centralized identity management and a Linux-based help desk system.

---

## High-Level Architecture
The environment is built around a Windows Server acting as a Domain Controller and multiple domain-joined client machines. A separate Ubuntu Server hosts the osTicket help desk application, providing a realistic IT support workflow.

Key architectural goals:
- Centralized authentication using Active Directory
- Separation of Windows infrastructure and Linux services
- Internal-only network communication
- Secure web access to help desk services

---

## Core Components

### Domain Controller
- Windows Server 2022
- Hosts Active Directory Domain Services (AD DS)
- Provides DNS services for the domain
- Manages user accounts and authentication

### Client Machines
- Windows 11 workstations
- Joined to the Active Directory domain
- Authenticate using domain credentials
- Represent end-user systems in the environment

### Help Desk Server
- Ubuntu Server
- Hosts osTicket via Apache, MySQL, and PHP
- Uses HTTPS with a locally generated SSL certificate
- Handles internal help desk ticket submission and management

---

## Network Design
All systems reside on the same internal network to simulate a small enterprise environment. Name resolution is handled through Active Directory DNS, allowing domain-joined clients to locate the Domain Controller and other internal services.

The help desk system is accessed via an internal domain-based URL over HTTPS. Browser security warnings are expected due to the use of a self-signed certificate.

---

## Authentication & Access Flow
1. Users authenticate to Windows client machines using Active Directory credentials.
2. Domain authentication is handled by the Domain Controller.
3. Users access the osTicket web portal from domain-joined machines.
4. Help desk agents authenticate to the osTicket admin panel using locally defined agent accounts.
5. Administrative access is restricted to designated agent roles.

---

## Security Considerations
- Domain-based authentication reduces reliance on local user accounts
- Separation of roles between Windows infrastructure and Linux services
- HTTPS encryption protects help desk traffic within the internal network
- Self-signed certificate is acceptable for lab purposes but noted as a limitation

---

## Architecture Diagram
The following diagram provides a visual overview of the environment and system interactions.


<img width="4080" height="1474" alt="architecture-diagram" src="https://github.com/user-attachments/assets/8b81d3e7-837f-4e62-8679-66e8580868fc" />


---

## Limitations
- No external email integration
- Self-signed SSL certificate instead of a trusted CA
- osTicket agents not integrated with Active Directory authentication
- Logging and monitoring not yet centralized

---

## Future Enhancements
- Active Directory integration with osTicket authentication
- SIEM integration for centralized logging
- Multi-subnet or VLAN-based network segmentation
- Additional domain roles and group policies

