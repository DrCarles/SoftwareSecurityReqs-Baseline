### 📌 Requirement
**The application must show generic error messages to users that do not reveal internal details, and keep the details only in internal logs**


### 💡 Rationale 
Detailed error messages are very useful to attackers. A stack trace, a database error or a file path can reveal the technologies and versions in use, the structure of the database, the internal network or the logic of the code, which helps attackers find and exploit vulnerabilities, for example by turning a blind SQL injection into an easy one

Users only need to know that something went wrong and what they can do next. Developers and support teams need the details, which can be stored in internal logs and linked to the user's message with a reference ID


### ⚙️ Specifications 

- 📘 Error messages shown to users or returned by APIs must be generic and must not include stack traces, exception messages, queries, file paths, internal hostnames or IP addresses, component names or versions, or configuration values

- 📘 Error messages should include a unique reference ID that allows support teams to find the matching log entry

- 📘 Error details (e.g. exception type, stack trace, reference ID, time, user and request) must be recorded in internal logs, without passwords, tokens, keys or other sensitive data

- 📘 Error messages must not reveal whether a user, account, file or record exists (e.g. login must return the same message for an unknown user and a wrong password)

- 📘 The application should use the same error message, status code and response time for situations that an attacker must not be able to tell apart

- 📘 API errors should follow a standard, minimal format (e.g. RFC 9457 Problem Details) with only the fields needed by clients


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Trigger errors by sending invalid input (e.g. wrong data types, very long values, special characters, missing parameters, invalid HTTP methods) and check that responses do not contain internal details
2. Request pages and API endpoints that do not exist, and check that the response does not reveal the server or framework
3. Try to log in with an unknown user and with a known user and wrong password, and check that the message, status code and response time are the same
4. Check that the reference ID shown to users can be found in the internal logs, and that the logs do not contain sensitive data


### 🔗 References 
CWE-209: Generation of Error Message Containing Sensitive Information

CWE-204: Observable Response Discrepancy

OWASP Error Handling Cheat Sheet

RFC 9457: Problem Details for HTTP APIs


### ⬅️ Navigation 

[Back](Readme.md)
