# Sample Tickets and Help Desk Workflows

## Purpose
This document demonstrates common help desk ticket types and workflows handled within the osTicket system. The examples reflect realistic enterprise support scenarios across multiple departments and illustrate ticket routing, agent actions, and resolution practices.

Sensitive information such as credentials, system secrets, and access URLs is intentionally excluded.

---

## Ticket Lifecycle Overview
The following ticket lifecycle was used consistently across all examples:

1. New (Ticket Submitted)
2. Open (Assigned to Department / Agent)
3. In Progress (Troubleshooting or Action Taken)
4. Resolved
5. Closed

This workflow mirrors standard IT service management (ITSM) practices.

---

## Ticket 1: Password Reset / Account Lockout (IT)

### Issue Summary
A user is unable to log into their workstation due to a suspected password issue or account lockout.

### Department
- Human Resources (HR)

### Actions Taken
- Verified user account status
- Confirmed authentication issue
- Performed account recovery actions
- Notified user of resolution

### Resolution
User access restored and ticket closed after successful login confirmation.

### Validation Screenshots
- Ticket details view
  <img width="1028" height="767" alt="ticket-01-password-reset-details" src="https://github.com/user-attachments/assets/d4702e8b-ae27-4999-ac37-f0fe450bccb9" />

  
- Ticket resolution process
  <img width="1226" height="918" alt="ticket-01-PoC-part1" src="https://github.com/user-attachments/assets/5429247c-f519-4132-9f06-2c1f72e697b2" />
  <img width="1027" height="768" alt="image" src="https://github.com/user-attachments/assets/670ee4d2-d7e9-4de4-9dda-a05ba696ce35" />
  <img width="1028" height="770" alt="image" src="https://github.com/user-attachments/assets/4b04bb71-de95-4b56-a2f5-4f5babc5af1a" />

- Ticket closed status
  
 <img width="1229" height="920" alt="ticket-01-password-reset-resolution" src="https://github.com/user-attachments/assets/74780a7b-3cd3-4c27-ba48-fff4dd04ea68" />


---

## Ticket 2: New Hire Onboarding Request (HR)

### Issue Summary
Human Resources submits a request to provision access for a new employee.

### Department
- Human Resources (HR)

### Actions Taken
- Ticket routed to HR department
- Request reviewed for completeness
- IT notified for account and access provisioning
- Status updated for tracking

### Resolution
Onboarding request processed and marked as completed.

### Validation Screenshots
- HR department ticket view  
  `screenshots/tickets/ticket-02-onboarding-details.png`
- Ticket assignment and completion  
  `screenshots/tickets/ticket-02-onboarding-resolution.png`

---

## Ticket 3: Network Share / Printer Access Issue (IT)

### Issue Summary
A user reports inability to access a shared network resource or printer.

### Department
- Information Technology (IT)

### Actions Taken
- Verified user access permissions
- Confirmed resource availability
- Guided user through reconnecting resource
- Documented troubleshooting steps

### Resolution
Access restored and ticket closed.

### Validation Screenshots
- IT ticket troubleshooting view  
  `screenshots/tickets/ticket-03-network-access-details.png`
- Final resolution status  
  `screenshots/tickets/ticket-03-network-access-resolution.png`
