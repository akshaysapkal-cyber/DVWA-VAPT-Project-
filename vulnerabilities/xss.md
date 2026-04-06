# Cross-Site Scripting (XSS)

## Description
Cross-Site Scripting (XSS) is a web application vulnerability that allows an attacker to inject malicious scripts into web pages viewed by other users. This occurs when an application does not properly validate or sanitize user input before displaying it in the browser.

When executed, the injected script runs in the victim’s browser and can perform actions such as stealing session data, modifying page content, or redirecting users.

## Objective
The objective of this test was to determine whether the application is vulnerable to XSS by injecting client-side scripts into input fields and observing their execution in the browser.

## Testing Approach
The application was tested by entering JavaScript payloads into input fields and checking whether the input is reflected without proper sanitization. Successful execution of the script confirms the vulnerability.

## Payload Used
<script>alert('XSS')</script>

## Steps to Reproduce
1. Navigate to DVWA → XSS (Reflected or Stored) module  
2. Enter the payload in the input field  
3. Submit the request  
4. Observe the response in the browser  
5. A popup alert appears, confirming successful XSS execution  

## Proof of Concept
Screenshot showing a JavaScript alert popup executed in the browser.

![xss cmd](https://github.com/akshaysapkal-cyber/DVWA-VAPT-Project-/blob/main/screenshots/xss.png?raw=true)

![xss result](https://github.com/akshaysapkal-cyber/DVWA-VAPT-Project-/blob/main/screenshots/XSS%20result.png?raw=true)

## Impact
- Execution of malicious scripts in the user's browser  
- Theft of session cookies  
- User impersonation  
- Redirection to malicious websites  
- Manipulation of web page content  

## Tools Used
- Web Browser  
- Burp Suite (for request interception and modification)  

## Remediation
- Validate and sanitize all user inputs  
- Implement proper output encoding  
- Use Content Security Policy (CSP)  
- Escape special characters before rendering user input  
- Avoid directly rendering user input in HTML  
