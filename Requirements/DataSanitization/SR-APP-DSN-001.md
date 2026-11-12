### 📌 Requirement
**The application must perform input validation on all incoming data**


### 💡 Rationale 

Input validation is a fundamental security control that helps protect the application from a wide range of attacks and errors caused by unexpected or malicious input. By verifying that all inputs conform to defined rules, the system can prevent: injection attacks, data corruption and processing errors, denial of service, and unauthorized access attempts

Validating inputs at the earliest point possible, preferably both on the client and server sides, ensures that only safe, well-formed data enters the system


### ⚙️ Specifications 

- 📘 The application must enforce input validation at server-side 

- 📘 The application should enforce input validation at client-side 

- 📘 The application should perform strict input validation on all incoming data to ensure it meets expected formats, types, and constraints before processing



### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Identify all input sources, including forms, URL parameters, headers, cookies, API bodies, uploaded files and messages from other systems
2. Send invalid values directly to the server, bypassing client-side validation (e.g. with an intercepting proxy such as OWASP ZAP or Burp Suite), and check that the server rejects them
3. Send values with the wrong type, out-of-range length, unexpected format or special characters, and check that they are rejected
4. Review the code and check that every input is validated against its expected format, type and constraints before being processed



### 🔗 References 
CWE-20: Improper Input Validation

OWASP Input Validation Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
