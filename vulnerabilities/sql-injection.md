# SQL Injection (SQLi)

## Description
SQL Injection is a web application vulnerability that allows an attacker to manipulate backend database queries by injecting malicious SQL code into input fields. This occurs when user input is not properly validated or sanitized.

## Objective
The objective of this test was to check whether the application is vulnerable to SQL Injection by manipulating input fields and observing database behavior.

## Testing Approach
The SQL Injection vulnerability was tested on the DVWA SQL Injection module by entering crafted inputs into the user input field.

## Payload Used
1' OR '1'='1

## Steps to Reproduce
1. Navigate to DVWA → SQL Injection module  
2. Enter the payload in the input field  
3. Submit the request  
4. Observe the response returned by the application  
5. The application returns multiple user records, indicating successful injection  

## Proof of Concept
Screenshot showing successful SQL Injection and extracted data from the database.

## Impact
- Unauthorized access to sensitive database information  
- Authentication bypass  
- Exposure of user credentials  
- Potential full database compromise  

## Tools Used
- Burp Suite (for intercepting and modifying requests)  
- Web Browser  

## Remediation
- Use parameterized queries (prepared statements)  
- Implement proper input validation and sanitization  
- Avoid dynamic SQL queries  
- Apply least privilege principle to database users
