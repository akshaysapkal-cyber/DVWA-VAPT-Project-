# DVWA VAPT Project

This project demonstrates a hands-on approach to Vulnerability Assessment and Penetration Testing (VAPT) on DVWA (Damn Vulnerable Web Application), a purposely vulnerable platform used for security training. The goal of this project is to simulate real-world web application testing by identifying, exploiting, and documenting common security vulnerabilities in a controlled lab environment.

## Objective
The primary objective of this project is to gain practical experience in web application security testing by:

- Identifying vulnerabilities based on OWASP Top 10 standards  
- Performing basic exploitation of discovered vulnerabilities  
- Understanding how real-world attacks are executed  
- Documenting vulnerabilities with clear explanations and remediation steps  

## Tools Used
The following tools were used during the testing process:

- **Nmap** – for basic network scanning and target identification  
- **Burp Suite** – for intercepting and modifying HTTP requests  
- **Nikto** – for web server vulnerability scanning  
- **Browser Developer Tools** – for analyzing client-side behavior  

## Target Environment
The testing was conducted in a controlled lab setup:

- **Target Application**: DVWA running on Metasploitable 2  
- **Attacker Machine**: Kali Linux  
- This environment ensures safe and legal testing without affecting real systems  

## Methodology
A structured VAPT methodology was followed to simulate a real penetration testing process:

1. **Information Gathering** – Understanding the application structure, endpoints, and inputs  
2. **Vulnerability Identification** – Testing for common security issues  
3. **Exploitation** – Attempting to exploit identified vulnerabilities  
4. **Validation** – Confirming successful exploitation  
5. **Documentation** – Recording findings and remediation  

- Detailed methodology:  
[View Methodology](./methodology/vapt-methodology.md)

## Information Gathering
Initial reconnaissance was performed to understand the target application. This included identifying input fields, pages, and possible attack surfaces.

- View detailed steps and findings:  
[Information Gathering](./information-gathering/)

## Vulnerability Assessment

### SQL Injection
SQL Injection vulnerability was identified in user input fields, allowing manipulation of backend database queries. This was used to bypass authentication and retrieve unintended data.

[View Detailed SQL Injection Write-up](./vulnerabilities/sql-injection.md)

### Cross-Site Scripting (XSS)
Cross-Site Scripting vulnerabilities were tested by injecting malicious scripts into input fields, demonstrating how client-side code execution can occur in a victim’s browser.

[View Detailed XSS Write-up](./vulnerabilities/xss.md)

## Exploitation
Basic exploitation techniques were applied to demonstrate the real impact of identified vulnerabilities, such as authentication bypass and script execution.

- View detailed exploitation steps:  
[Exploitation Details](./exploitation/)

## Tools Usage
Tools were used to assist in testing, including request interception, scanning, and payload testing.

- View how tools were used:  
[Tools Usage](./tools-usage/)

## Final Report
A structured VAPT report was created documenting vulnerabilities, their impact, and recommended mitigation steps.

[View Full Report](./report/final-report.md)

## Proof of Work
Screenshots are included to provide evidence of successful vulnerability exploitation and testing process.

[View Screenshots](./screenshots/)

## Key Learnings
- Gained practical understanding of OWASP Top 10 vulnerabilities  
- Learned how to identify and exploit common web application flaws  
- Developed skills in using security testing tools  
- Understood the importance of structured vulnerability reporting  

## Disclaimer
This project was conducted in a controlled lab environment strictly for educational purposes. All testing was performed on intentionally vulnerable systems. Unauthorized testing on real-world systems is illegal.
