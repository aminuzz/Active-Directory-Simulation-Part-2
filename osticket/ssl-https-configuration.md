# SSL / HTTPS Configuration for osTicket

## Purpose
This document describes how HTTPS was enabled for the osTicket help desk application using a locally generated SSL certificate. The configuration is intended for an internal lab environment to simulate secure web access within an enterprise network.

Sensitive configuration values, file paths, and access URLs are intentionally omitted.

---

## Why HTTPS Was Implemented
Even in internal environments, encrypting web traffic is a best practice. Enabling HTTPS for osTicket provides:

- Encrypted communication between clients and the help desk server
- Protection of authentication data in transit
- Experience configuring SSL on a Linux web server
- Familiarity with browser trust warnings and certificate validation

---

## SSL Certificate Type
A **self-signed SSL certificate** was generated for this lab.

### Rationale
- No external Certificate Authority (CA) required
- Suitable for internal testing and development
- Allows full HTTPS functionality without public trust

Because the certificate is self-signed, browsers display a security warning. This behavior is expected and documented.

---

## Web Server Configuration
osTicket is hosted using the Apache web server on Ubuntu.

### Configuration Overview
- Apache HTTPS support enabled
- SSL module activated
- Virtual host configured for HTTPS
- osTicket site bound to the SSL virtual host
- HTTP traffic allowed for initial access and testing

---

## Validation & Testing
The following checks were performed to validate the HTTPS configuration:

- osTicket loads successfully over HTTPS
- Apache service starts without SSL-related errors
- Browser displays certificate trust warning (expected)
- Admin and user portals remain accessible
- No mixed-content errors observed

---

## Browser Trust Warning
When accessing the site, the browser displays a “Not Secure” or certificate warning.

### Explanation
- The certificate is not signed by a trusted public CA
- The certificate is used only within the internal lab
- No sensitive production data is exposed

This behavior is acceptable and expected in a lab environment.

<img width="1912" height="991" alt="osticket-https-certificate-warning" src="https://github.com/user-attachments/assets/82f21b6e-2777-4836-b2d1-73a7757305d2" />
 
---

## Security Considerations
- SSL encrypts traffic despite the certificate not being publicly trusted
- No external access to the help desk system
- Certificate files are stored securely on the server
- HTTPS configuration reduces risk of credential interception

---

## Limitations
- Certificate is not trusted by default
- No automatic certificate renewal
- No public DNS validation
- Not suitable for production environments

---

## Future Improvements
- Replace self-signed certificate with internal CA
- Use Let’s Encrypt for trusted certificates in production
- Enforce HTTP to HTTPS redirection
- Harden SSL/TLS configuration
