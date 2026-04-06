# VAPT Report – DVWA

## Overview
This report presents the findings of Vulnerability Assessment and Penetration Testing (VAPT) performed on DVWA (Damn Vulnerable Web Application). The assessment was conducted in a controlled lab environment to identify and validate security vulnerabilities in the application.

## Objective
The objective of this assessment was to identify common web application vulnerabilities, exploit them in a controlled manner, and understand their potential impact.

## Scope
- Target: DVWA (running on Metasploitable 2)  
- Environment: Local Lab Setup  
- Testing Type: Web Application Security Testing
- Testing Level: Black-box (no prior knowledge of internal code)

## Tools Used
- Nmap  
- Burp Suite  
- Nikto  
- Web Browser  

## Methodology
A structured VAPT methodology was followed:
1. Information Gathering  
2. Vulnerability Identification  
3. Exploitation  
4. Validation  
5. Documentation  

## Findings Summary

- SQL Injection  
  Severity: High  
  Status: Confirmed
  Reason: Allows unauthorized database access and authentication bypass

- Cross-Site Scripting (XSS)  
  Severity: Medium  
  Status: Confirmed
  Reason: Enables execution of malicious scripts in user browser  

## SQL Injection

### Description
SQL Injection allows manipulation of database queries through user input, leading to unauthorized data access.

### Impact
- Authentication bypass  
- Unauthorized access to sensitive data  
- Potential database compromise  

### Recommendation
- Use parameterized queries  
- Validate user input  
- Avoid dynamic SQL queries  

## Cross-Site Scripting (XSS)

### Description
XSS allows execution of malicious scripts in the user’s browser due to improper input handling.

### Impact
- Session hijacking  
- User impersonation  
- Execution of malicious scripts in user browser  
- Possible phishing or redirection attacks  

### Recommendation
- Sanitize user input  
- Implement output encoding  
- Use Content Security Policy (CSP)  

## Conclusion
The assessment identified critical and medium-level vulnerabilities in the application. These vulnerabilities demonstrate how improper input validation can lead to serious security risks, Proper security measures and coding practices are recommended to mitigate these issues.

## Proof of Concept

Detailed evidence and screenshots are available in the respective vulnerability sections:

- SQL Injection → [View Details](../vulnerabilities/sql-injection.md)  
- Cross-Site Scripting (XSS) → [View Details](../vulnerabilities/xss.md)  

## Disclaimer
This testing was performed in a controlled lab environment for educational purposes only. No real systems were harmed during this process.
