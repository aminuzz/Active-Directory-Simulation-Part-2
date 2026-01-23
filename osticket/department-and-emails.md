# osTicket Departments and Email Configuration

## Purpose
This document describes how departments and email identities are structured within the osTicket help desk system. The configuration is designed to simulate a small enterprise organization with department-based ticket routing and role separation.

Sensitive information such as passwords, mail server credentials, and access URLs is intentionally excluded.

---

## Department-Based Ticketing Model
osTicket is configured to route tickets based on organizational departments. Each department represents a functional area within the company and can be assigned specific agents, workflows, and automated responses.

This structure mirrors how enterprise IT teams triage and manage incoming requests.

---

## Configured Departments

### Human Resources (HR)
**Purpose:**
- Handle employee-related inquiries
- Manage internal requests such as onboarding and policy questions

**Characteristics:**
- Separate department to maintain privacy
- Limited agent access
- Distinct auto-response messaging

---

### Finance
**Purpose:**
- Handle finance-related support requests
- Manage issues related to payroll, reimbursements, and billing systems

**Characteristics:**
- Restricted visibility
- Assigned agents only
- Department-specific email identity

---

### Sales
**Purpose:**
- Handle sales-related internal support requests
- Support CRM access and sales tooling issues

**Characteristics:**
- Isolated from HR and Finance tickets
- Custom workflows for request prioritization

---

### Information Technology (IT)
**Purpose:**
- Primary technical support department
- Handle system access issues, device problems, and general IT requests

**Characteristics:**
- Tier 1 support agents assigned
- Receives default technical tickets
- Centralized troubleshooting workflows

---

## Department Email Identities
Each department is assigned a unique internal email identity to simulate enterprise ticket intake. These email addresses are used within osTicket for ticket creation, routing, and automated responses.

### Example Department Emails
- `hr@corp.local`
- `finance@corp.local`
- `sales@corp.local`
- `it@corp.local`

These email identities are configured for internal use only and are not connected to external mail servers.

---

## Auto-Response Configuration
Departments are configured with automatic responses to acknowledge ticket creation. Auto-responses provide confirmation to users while maintaining professional communication standards.

Auto-responses can be customized per department to reflect organizational tone and policies.

---

## Ticket Routing Logic
- Tickets are assigned to departments based on selected category or email identity
- Agents only see tickets assigned to their department
- Administrative users have visibility across all departments

This routing model enforces separation of duties and reduces unnecessary ticket exposure.

---

## Security & Privacy Considerations
- Department separation limits access to sensitive requests
- Internal email identities reduce external exposure
- No external email integration is enabled
- Role-based visibility enforces least privilege

---

## Limitations
- Email addresses are internal only
- No SMTP relay or external email forwarding
- Manual department selection required during ticket creation

---

## Future Enhancements
- Enable external email integration for ticket intake
- Implement department-specific SLA policies
- Automate ticket categorization
- Add escalation paths between departments
