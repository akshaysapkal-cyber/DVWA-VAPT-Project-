# DVWA VAPT Project

This project demonstrates a hands-on approach to Vulnerability Assessment and Penetration Testing (VAPT) on DVWA (Damn Vulnerable Web Application), a purposely vulnerable platform used for security training. The goal of this project is to simulate real-world web application testing by identifying, exploiting, and analyzing common security vulnerabilities in a controlled lab environment.

## Objective
The primary objective of this project is to gain practical experience in web application security testing by:

- Identifying common web application vulnerabilities  
- Performing controlled exploitation of discovered vulnerabilities  
- Understanding how vulnerabilities behave under different security levels  
- Documenting findings with impact and remediation  

## Tools Used
- DVWA (Damn Vulnerable Web Application)  
- Web Browser  
- Burp Suite (used for request interception and modification during SQL Injection testing at medium level)  

## Target Environment
The testing was conducted in a controlled lab setup:

- Target Application: DVWA running on Metasploitable 2  
- Attacker Machine: Kali Linux  
- Security Levels Tested: Low and Medium  
- Environment: Local setup for safe and legal testing  

## Methodology
A structured VAPT methodology was followed:

1. Information Gathering  
2. Vulnerability Identification  
3. Exploitation  
4. Validation  
5. Documentation  

[View Detailed Methodology](./methodology/vapt-methodology.md)

## Vulnerability Assessment

### SQL Injection (Low & Medium)
SQL Injection vulnerability was identified in input fields, allowing manipulation of backend database queries.

- At Low level, basic payloads successfully bypassed authentication  
- At Medium level, input filtering restricted standard payloads, which were bypassed using URL-encoded payloads and Burp Suite  

[View SQL Injection Details](./vulnerabilities/sql-injection.md)

### Cross-Site Scripting (XSS - Low)
Reflected XSS vulnerability was identified by injecting scripts into input fields, resulting in execution of JavaScript in the browser.

[View XSS Details](./vulnerabilities/xss.md)

## Final Report
A structured VAPT report documenting vulnerabilities, impact, and remediation steps.

[View Full Report](./report/final-report.md)

## Proof of Work
Screenshots demonstrating successful exploitation are available in the project.

[View Screenshots](./screenshots/)

## Key Learnings
- Practical understanding of SQL Injection and Reflected XSS  
- Hands-on experience in manual web application testing  
- Understanding of input filtering and bypass techniques  
- Practical use of Burp Suite for request interception and modification  
- Importance of secure coding practices and input validation
 
## Disclaimer
This project was conducted in a controlled lab environment strictly for educational purposes. All testing was performed on intentionally vulnerable systems. Unauthorized testing on real-world systems is strictly prohibited.
