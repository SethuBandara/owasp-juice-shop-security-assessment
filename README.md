# OWASP Juice Shop — Web Application & API Security Assessment

## Overview

This project documents a practical Web Application and API Security Assessment conducted against **OWASP Juice Shop** within an authorized local laboratory environment.

The assessment focuses on identifying, validating, and documenting common web application and API security weaknesses using a structured penetration-testing methodology.

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

## Methodology

The assessment followed these major phases:

1. Reconnaissance
2. HTTP Traffic Interception
3. API Enumeration
4. Endpoint Classification
5. Vulnerability Assessment
6. Manual Validation
7. Risk Assessment
8. Remediation Planning

## Vulnerability Areas

The assessment covers:

* BOLA / IDOR
* Broken Authentication
* Broken Function-Level Authorization (BFLA)
* Injection
* Security Misconfiguration
* Excessive Data Exposure

## Tools

| Tool                         | Purpose                                    |
| ---------------------------- | ------------------------------------------ |
| Podman                       | Container deployment and management        |
| OWASP Juice Shop             | Intentionally vulnerable target            |
| Burp Suite Community Edition | Web application security testing           |
| Burp Proxy                   | HTTP traffic interception                  |
| Burp HTTP History            | Request and response analysis              |
| Burp Target / Site Map       | Application and API enumeration            |
| Burp Repeater                | Manual request modification and validation |
| Nmap                         | Port and service discovery                 |
| Web Browser                  | Application interaction                    |

## Environment

**Target:** OWASP Juice Shop
**Target URL:** `http://localhost:3000`
**Protocol:** HTTP
**Port:** 3000
**Deployment:** Podman
**Environment:** Local authorized laboratory environment

## Report

The complete assessment report is available in the [`Report`](./Report/) directory.

## Disclaimer

This project was conducted strictly within an authorized local laboratory environment for educational and security-testing purposes.

No unauthorized systems or third-party applications were targeted.
