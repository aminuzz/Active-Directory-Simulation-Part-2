# Domain Controller Setup Guide

## Purpose
This document outlines the process used to configure a Windows Server as a Domain Controller in the Active Directory simulation lab. The goal of this setup is to establish centralized authentication, directory services, and DNS for a small enterprise environment.

Sensitive credentials and environment-specific secrets are intentionally excluded.

---

## System Overview
- Operating System: Windows Server 2022
- Role: Domain Controller
- Domain Type: New forest
- Forest Name: `corp.local`

The Domain Controller serves as the core identity and authentication service for all domain-joined systems.

---

## Prerequisites
Before promoting the server to a Domain Controller, the following prerequisites were met:

- Windows Server installed and fully updated
- Static IP address configured
- Hostname set appropriately
- Local administrator access confirmed
- Server connected to internal lab network

---

## Initial Server Configuration

### Hostname Configuration
The server hostname was configured prior to domain promotion to ensure consistency across directory services and DNS records.

### Network Configuration
A static IP address was assigned to the server to ensure:
- Reliable DNS resolution
- Consistent domain authentication
- Stability for domain-joined clients

---

## Active Directory Domain Services Installation

### Role Installation
The **Active Directory Domain Services (AD DS)** role was installed using Server Manager. Required dependencies, including DNS Server, were installed automatically.

### Domain Promotion
The server was promoted to a Domain Controller with the following characteristics:
- New forest created
- Domain name set to `corp.local`
- DNS installed during promotion
- Global Catalog enabled

A Directory Services Restore Mode (DSRM) password was configured during this process.

---

## Post-Promotion Configuration

### DNS Verification
After promotion, DNS functionality was verified to ensure:
- Forward lookup zones were created
- Domain records resolved correctly
- The server could resolve its own domain name

### Active Directory Verification
Active Directory was validated by:
- Accessing Active Directory Users and Computers
- Confirming default containers and objects
- Verifying domain and forest functionality levels

---

## Organizational Structure

### User Accounts
Domain user accounts were created to simulate employees and IT staff. These accounts are used for:
- Domain authentication
- Workstation logins
- Role-based access testing

### Administrative Accounts
Separate administrative accounts were used to:
- Manage Active Directory
- Perform domain-level configuration
- Reduce reliance on built-in administrator accounts

---

## Validation & Testing
The following checks were performed to confirm a successful setup:

- Domain Controller rebooted successfully
- Domain login screen displayed on server
- DNS resolution functioning correctly
- Active Directory management tools accessible
- Server operating without AD-related errors

---

## Security Considerations
- Static IP enforced for the Domain Controller
- Separation between user and administrative accounts
- DNS tightly coupled with Active Directory
- DSRM configured for recovery scenarios

---

## Limitations
- Single Domain Controller (no redundancy)
- No backup Domain Controller configured
- No Group Policy hardening applied yet
- No centralized logging configured

---

## Future Enhancements
- Add a secondary Domain Controller for redundancy
- Implement Group Policy baselines
- Integrate centralized logging
- Apply security hardening policies
