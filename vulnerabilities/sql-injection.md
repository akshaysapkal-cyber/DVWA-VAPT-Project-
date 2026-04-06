# SQL Injection (SQLi)
### Low Level Testing

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
![SQLi](https://github.com/akshaysapkal-cyber/DVWA-VAPT-Project-/blob/main/screenshots/SQLi.png?raw=true)

## Impact
- Unauthorized access to sensitive database information  
- Authentication bypass  
- Exposure of user credentials  
- Potential full database compromise  

## Tools Used
- Web Browser  

## Remediation
- Use parameterized queries (prepared statements)  
- Implement proper input validation and sanitization  
- Avoid dynamic SQL queries  
- Apply least privilege principle to database users

# Medium Level Testing (Using Burp Suite)

## Description
At medium security level, input validation and filtering mechanisms are implemented to prevent basic SQL Injection attacks. Standard payloads containing special characters are restricted, making direct injection through the browser ineffective.

## Testing Approach
Since manual SQL injection was restricted, Burp Suite was used to intercept and modify the HTTP request, bypassing client-side restrictions, This allowed direct manipulation of parameters and bypassed client-side input filtering.

## Payload Used
1+OR+1%3D1

(Decoded: `1 OR 1=1`, where `+` represents space and `%3D` represents `=`)

## Steps to Reproduce
1. Set DVWA Security Level to Medium  
2. Open DVWA → SQL Injection module  
3. Configure browser to use Burp Suite proxy (127.0.0.1:8080)  
4. Enable Intercept in Burp Suite  
5. Enter a normal value (e.g., 1) and submit the request  
6. Capture the request in Burp Suite  
7. Modify the parameter:
   - Change `id=1` to `id=1+OR+1%3D1`  
8. Forward the request  
9. Observe the response showing multiple records  

## Proof of Concept
Screenshot showing successful SQL Injection after modifying request in Burp Suite.

![Burp Suite](https://github.com/akshaysapkal-cyber/DVWA-VAPT-Project-/blob/main/screenshots/Burp%20Suite.png?raw=true)
![Burp Result](https://github.com/akshaysapkal-cyber/DVWA-VAPT-Project-/blob/main/screenshots/Burp%20Result.png?raw=true)

## Observation
- Manual SQL Injection payloads were restricted due to input filtering  
- Burp Suite allowed interception and modification of requests  
- URL-encoded payload successfully bypassed filtering  
- The application remained vulnerable despite security controls  

## Tools Used
- Burp Suite (for intercepting and modifying HTTP requests)  
- Web Browser  

## Key Learning
Client-side input validation can be bypassed by intercepting and modifying requests. Security mechanisms relying only on input filtering are not sufficient to prevent SQL Injection.

## Remediation
- Use parameterized queries (prepared statements) to prevent SQL Injection  
- Implement strict server-side input validation instead of relying on client-side filtering  
- Apply least privilege to database access  
