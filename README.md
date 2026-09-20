<p align="center">
  <img src="project-banner.png" alt="OWASP Juice Shop Web Application and API Security Assessment">
</p>

<h1 align="center">OWASP Juice Shop – Web Application & API Security Assessment</h1>

<p align="center">
  <strong>Burp Suite</strong> •
  <strong>Nmap</strong> •
  <strong>Podman</strong> •
  <strong>OWASP API Security</strong>
</p>

---

## Executive Summary

This project demonstrates a structured Web Application and API Security Assessment of OWASP Juice Shop within an authorized local laboratory environment.

The assessment followed a practical security testing workflow covering reconnaissance, service and endpoint enumeration, vulnerability identification, manual validation, evidence collection, CVSS-based risk assessment, and remediation planning.

The assessment focused on authentication, authorization, API security, injection vulnerabilities, security misconfigurations, and information exposure.

---

## Project Overview

**OWASP Juice Shop** is an intentionally vulnerable web application used for security education and practical application-security testing.

This project was conducted to develop hands-on experience in identifying, validating, documenting, and assessing common web application and API security weaknesses.

The assessment involved analyzing HTTP requests and responses, identifying application and API endpoints, testing authorization controls, validating security findings, collecting reproducible evidence, and preparing remediation recommendations.

---

## Objectives

* Perform target reconnaissance and service discovery
* Analyze HTTP communication using Burp Suite
* Enumerate web application and API endpoints
* Assess authentication mechanisms
* Test object-level authorization
* Test function-level authorization
* Assess injection-related risks
* Identify security misconfigurations
* Validate security findings using reproducible evidence
* Perform risk assessment and CVSS-based severity classification
* Provide appropriate remediation recommendations

---

## Assessment Methodology

The assessment followed a structured security testing workflow:

**Reconnaissance**
↓
**Service & Endpoint Enumeration**
↓
**Application/API Analysis**
↓
**Vulnerability Identification**
↓
**Manual Validation**
↓
**Evidence Collection**
↓
**CVSS Risk Assessment**
↓
**Remediation Recommendations**

---

## Vulnerability Areas

The assessment investigated the following security areas:

* BOLA / IDOR
* Broken Authentication
* Broken Function-Level Authorization (BFLA)
* Injection
* Security Misconfiguration
* Excessive Data Exposure

---

## Tools & Technologies

| Tool / Technology                | Purpose                                                 |
| -------------------------------- | ------------------------------------------------------- |
| **OWASP Juice Shop**             | Intentionally vulnerable web application and API target |
| **Podman**                       | Container deployment and laboratory environment         |
| **Burp Suite Community Edition** | Web application security testing                        |
| **Burp Proxy**                   | HTTP traffic interception                               |
| **Burp HTTP History**            | Request and response analysis                           |
| **Burp Target / Site Map**       | Application and API enumeration                         |
| **Burp Repeater**                | Manual request modification and validation              |
| **Nmap**                         | Port and service discovery                              |
| **Web Browser**                  | Application interaction and testing                     |

---

## Key Findings

The assessment identified and risk-assessed five security findings across authentication, authorization, API security, input validation, and security configuration.

| ID      | Finding                                    | Security Area        | Severity | CVSS v3.1 | Priority       |
| ------- | ------------------------------------------ | -------------------- | -------- | --------: | -------------- |
| WEB-001 | BOLA / IDOR                                | API Authorization    | High     |       7.1 | P1 – Immediate |
| WEB-002 | Broken Authentication                      | Authentication       | High     |       7.5 | P1 – Immediate |
| WEB-003 | Broken Function-Level Authorization (BFLA) | Authorization        | High     |       7.6 | P1 – Immediate |
| WEB-004 | Injection                                  | Input Validation     | Critical |       9.8 | P1 – Immediate |
| WEB-005 | Security Misconfiguration                  | Application Security | Low      |       3.7 | P3 – Planned   |

### Assessment Highlights

* **BOLA / IDOR:** Testing demonstrated access to a different user's object by modifying the object identifier while maintaining the authenticated session context.
* **Broken Authentication:** Authentication and unauthorized-access behavior were tested using valid, invalid, and unauthenticated requests.
* **BFLA:** A standard-user session was demonstrated to successfully invoke a function intended to be restricted to an administrative role.
* **Injection:** Controlled injection testing was performed against application input parameters, including an SQL injection test case.
* **Security Misconfiguration:** HTTP security headers and detailed application error responses were reviewed for configuration weaknesses and information disclosure.

Detailed technical evidence, testing procedures, CVSS calculations, and remediation recommendations are documented in the assessment report.

---

## Selected Assessment Evidence

The following evidence provides direct visual support for the security findings documented in this assessment. Each finding includes links to the relevant screenshots and the complete evidence directory.

---

### 1. BOLA / IDOR — Object-Level Authorization

**Finding:** A low-privileged authenticated user was able to access another user's basket by modifying the object identifier in the API request.

**Evidence:**

* [Baseline Request](./Evidence/BOLA-IDOR/01-bola-baseline-request.png)
* [Modified Request](./Evidence/BOLA-IDOR/02-bola-modified-request.png)
* [Response Comparison](./Evidence/BOLA-IDOR/03-bola-response-comparison.png)
* [Response Comparison – Additional Evidence](./Evidence/BOLA-IDOR/03-bola-response-comparison-2.png)

📁 [View all BOLA / IDOR evidence](./Evidence/BOLA-IDOR/)

---

### 2. Broken Authentication

**Finding:** Authentication controls were assessed using valid, invalid, and unauthenticated requests, including verification of protected-resource access.

**Evidence:**

* [Authentication Request](./Evidence/Authentication/01-authentication-request.png)
* [Authentication Response / Session](./Evidence/Authentication/02-authentication-response-session.png)
* [Invalid Authentication](./Evidence/Authentication/03-invalid-authentication.png)
* [Authenticated Baseline](./Evidence/Authentication/04-authenticated-baseline.png)
* [Unauthenticated Test](./Evidence/Authentication/05-unauthenticated-test.png)

📁 [View all Authentication evidence](./Evidence/Authentication/)

---

### 3. Broken Function-Level Authorization (BFLA)

**Finding:** A standard-user session successfully invoked a function intended to be restricted to an administrative role, demonstrating insufficient server-side function-level authorization.

**Evidence:**

* [Admin Privileged Function](./Evidence/BFLA/01-admin-privileged-function.png)
* [Privileged API Request](./Evidence/BFLA/02-privileged-api-request.png)
* [Admin API Response](./Evidence/BFLA/03-admin-api-response.png)
* [Standard User Replay](./Evidence/BFLA/04-standard-user-replay.png)
* [BFLA Authorization Bypass](./Evidence/BFLA/05-bfla-authorization-bypass.png)

📁 [View all BFLA evidence](./Evidence/BFLA/)

---

### 4. Injection

**Finding:** Controlled injection testing was performed against application input parameters, including an SQL injection test case.

**Evidence:**

* [Normal Search Request / Response](./Evidence/Injection/01-normal-search-request-response.png)
* [Injection Test Payload](./Evidence/Injection/02-injection-test-payload.png)
* [Injection Response](./Evidence/Injection/03-injection-response.png)

📁 [View all Injection evidence](./Evidence/Injection/)

---

### 5. Security Misconfiguration

**Finding:** HTTP security headers and application error responses were reviewed to identify configuration weaknesses and unnecessary information disclosure.

**Evidence:**

* [HTTP Security Headers](./Evidence/Security-Misconfiguration/01-http-security-headers.png)
* [Detailed Server Error](./Evidence/Security-Misconfiguration/02-detailed-server-error.png)
* [Security Header Configuration](./Evidence/Security-Misconfiguration/03-security-header-configuration.png)

📁 [View all Security Misconfiguration evidence](./Evidence/Security-Misconfiguration/)

---

### Evidence Summary

| Finding                       | Severity | CVSS v3.1 | Evidence                                               |
| ----------------------------- | -------: | --------: | ------------------------------------------------------ |
| **BOLA / IDOR**               |     High |       7.1 | [View Evidence](./Evidence/BOLA-IDOR/)                 |
| **Broken Authentication**     |     High |       7.5 | [View Evidence](./Evidence/Authentication/)            |
| **BFLA**                      |     High |       7.6 | [View Evidence](./Evidence/BFLA/)                      |
| **Injection**                 | Critical |       9.8 | [View Evidence](./Evidence/Injection/)                 |
| **Security Misconfiguration** |      Low |       3.7 | [View Evidence](./Evidence/Security-Misconfiguration/) |

For the complete testing methodology, technical analysis, CVSS assessment, and remediation recommendations, see the [full assessment report](./Report/).

---

## Environment

The assessment was conducted in an isolated and authorized local laboratory environment.

| Configuration           | Details                              |
| ----------------------- | ------------------------------------ |
| **Target Application**  | OWASP Juice Shop                     |
| **Target URL**          | `http://localhost:3000`              |
| **Protocol**            | HTTP                                 |
| **Port**                | 3000                                 |
| **Deployment Platform** | Podman                               |
| **Testing Proxy**       | Burp Suite                           |
| **Reconnaissance Tool** | Nmap                                 |
| **Client**              | Web Browser                          |
| **Environment Type**    | Authorized Local Security Laboratory |

### Assessment Architecture

```text
┌──────────────────────┐
│     Web Browser      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│     Burp Suite       │
│ Proxy / Repeater     │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│    localhost:3000    │
│    OWASP Juice Shop  │
│      Podman          │
└──────────────────────┘

        ┌─────────────┐
        │    Nmap     │
        │ Recon /     │
        │ Enumeration │
        └─────────────┘
```

The laboratory setup allowed HTTP traffic to be intercepted, application and API endpoints to be enumerated, requests to be modified and replayed, and security findings to be validated without targeting unauthorized external systems.

---

## Project Structure

```text
owasp-juice-shop-security-assessment/
│
├── Evidence/
│   ├── Reconnaissance/
│   ├── BOLA-IDOR/
│   ├── Authentication/
│   ├── BFLA/
│   ├── Injection/
│   └── Security-Misconfiguration/
│
├── Report/
│   └── Web_Application_API_Security_Assessment.pdf
│
├── project-banner.png
└── README.md
```

---

## Assessment Report

The complete assessment report documents the security testing methodology, reconnaissance results, vulnerability validation, evidence, risk assessment, CVSS scoring, and remediation recommendations.

### 📄 Full Technical Report

**[View Web Application & API Security Assessment Report](./Report/Web_Application_API_Security_Assessment.pdf)**

### 🔎 Supporting Evidence

**[View All Assessment Evidence](./Evidence/)**

The evidence directory contains screenshots organized by security finding:

* **[BOLA / IDOR](./Evidence/BOLA-IDOR/)** — Object-level authorization testing
* **[Broken Authentication](./Evidence/Authentication/)** — Authentication and unauthorized-access testing
* **[BFLA](./Evidence/BFLA/)** — Function-level authorization testing
* **[Injection](./Evidence/Injection/)** — Injection testing and validation
* **[Security Misconfiguration](./Evidence/Security-Misconfiguration/)** — Security-header and error-disclosure analysis

### Assessment Coverage

| Assessment Component                 | Included |
| ------------------------------------ | :------: |
| Reconnaissance                       |     ✅    |
| Service Discovery                    |     ✅    |
| Web Application Enumeration          |     ✅    |
| API Enumeration                      |     ✅    |
| Authentication Testing               |     ✅    |
| Object-Level Authorization Testing   |     ✅    |
| Function-Level Authorization Testing |     ✅    |
| Injection Testing                    |     ✅    |
| Security Configuration Review        |     ✅    |
| Evidence Collection                  |     ✅    |
| CVSS Risk Assessment                 |     ✅    |
| Remediation Recommendations          |     ✅    |

---

## Skills Demonstrated

This project provided hands-on experience in the following areas:

### Web & API Security

* Web Application Security Testing
* API Security Assessment
* OWASP-based Vulnerability Assessment
* HTTP Request/Response Analysis
* API Endpoint Enumeration

### Authentication & Authorization

* Authentication Testing
* Object-Level Authorization Testing
* BOLA / IDOR Validation
* Function-Level Authorization Testing
* Privilege Boundary Testing

### Security Testing Tools

* Burp Suite
* Burp Proxy
* Burp Repeater
* Burp HTTP History
* Burp Target / Site Map
* Nmap
* Podman

### Vulnerability Assessment

* Injection Testing
* Security Misconfiguration Analysis
* Vulnerability Validation
* Evidence Collection
* CVSS v3.1 Risk Assessment
* Remediation Planning

### Security Documentation

* Security Finding Documentation
* Technical Evidence Analysis
* Risk Classification
* Vulnerability Reporting
* Security Recommendations

---

## Disclaimer

This project was conducted strictly within an authorized local laboratory environment using the intentionally vulnerable OWASP Juice Shop application.

The assessment was performed for educational, academic, and cybersecurity skill-development purposes.

No unauthorized systems, networks, applications, or third-party services were targeted.

The techniques and tools demonstrated in this repository should only be used against systems for which appropriate authorization has been obtained.

---

## Repository

This repository contains the assessment methodology, technical evidence, security findings, assessment report, and supporting documentation.

**GitHub Repository:**
https://github.com/SethuBandara/owasp-juice-shop-security-assessment
