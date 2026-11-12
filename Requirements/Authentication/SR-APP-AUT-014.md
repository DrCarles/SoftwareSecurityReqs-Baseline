### 📌 Requirement
**The system must log all successful and unsuccessful authentication attempts**


### 💡 Rationale 
Authentication logs are the main source for detecting attacks against user accounts. Brute-force, credential stuffing and password spraying attacks show up as many failed attempts, while a successful login after many failures, or from an unusual location, can indicate that an account has been compromised

During an incident investigation, these logs show which accounts were accessed, when and from where. Without them, account takeovers can go unnoticed and their impact cannot be determined


### ⚙️ Specifications 

- 📘 The system must log every successful authentication

- 📘 The system must log every failed authentication attempt, including attempts with unknown usernames

- 📘 Logging must cover every authentication method, including login forms, API keys and tokens, single sign-on, second-factor (MFA) checks and account recovery

- 📘 Each log entry must include at least the timestamp (with time zone, from a synchronized clock), the username or account ID, the result (success or failure), the source IP address and the authentication method. It should also include the failure reason (internal only) and a request or session reference

- 📘 Log entries must not contain passwords, including wrong ones, MFA codes, session tokens or other secrets

- 📘 Usernames and other user-supplied values must be neutralized before logging to prevent log injection (see [SR-APP-SCI-010](../SafeCommandInvocation/SR-APP-SCI-010.md))

- 📘 Authentication logs must be protected against unauthorized access and modification, since they contain personal data

- 📘 The system should log logouts and session expirations

- 📘 Authentication logs should be sent to a central logging or monitoring system that raises alerts on suspicious patterns (e.g. many failures for one account, many accounts tried from one IP address, success after many failures)


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Log in successfully and check that an entry with all required fields is recorded
2. Log in with a valid username and a wrong password and check that the failure is recorded
3. Log in with an unknown username and check that the attempt is recorded
4. Repeat the tests for every authentication method (e.g. API, single sign-on, failed MFA code, account recovery)
5. Check that the log entries do not contain the password entered, MFA codes or tokens
6. Enter a username containing line breaks and check that it does not create fake log entries
7. Generate many failed attempts and check that an alert is raised, if monitoring is in place


### 🔗 References 
CWE-778: Insufficient Logging

CWE-532: Insertion of Sensitive Information into Log File

NIST SP 800-53 Rev. 5: AU-2 Event Logging

NIST SP 800-53 Rev. 5: AU-3 Content of Audit Records

OWASP Logging Cheat Sheet

OWASP Top 10: Security Logging and Monitoring Failures


### ⬅️ Navigation 

[Back](Readme.md)
