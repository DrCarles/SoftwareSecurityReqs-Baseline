### 📌 Requirement
**The application must fail safe: when an error occurs, it must deny access and leave the system in a secure and consistent state**


### 💡 Rationale 
Errors often happen in code paths that are rarely tested. If a security check fails because of an error (for example, the authorization service cannot be reached or a token cannot be parsed) and the application continues by default, attackers can trigger that error on purpose to bypass the check

Failing safe (also called failing closed) means that any unexpected situation results in the most restrictive outcome: access is denied, the operation is cancelled, and data is left as it was before the operation started


### ⚙️ Specifications 

- 📘 Security decisions (e.g. authentication, authorization, signature and token validation, input validation) must deny access by default, and grant it only when the check completes successfully

- 📘 Errors or exceptions raised during a security check must result in access being denied, never granted

- 📘 Operations that change data must be atomic: if an error occurs, all changes made by the operation must be rolled back (e.g. using database transactions)

- 📘 When an error occurs, resources such as connections, files, locks and memory must be released (e.g. using `finally` blocks or `try-with-resources`)

- 📘 When a dependency needed for a security decision is unavailable (e.g. identity provider, policy service, revocation check), the application must deny the request rather than skip the check

- 📘 Errors must not leave a user's session in an elevated or partially authenticated state


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Review the code of security checks and check that the default result is "deny" and that errors in `catch` blocks do not return "allow"
2. Send malformed tokens, signatures and session cookies and check that access is denied
3. Make security dependencies unavailable in a test environment (e.g. stop the identity provider) and check that requests are rejected
4. Cause errors in the middle of multi-step operations (e.g. payments, transfers) and check that data is rolled back to a consistent state
5. Repeatedly trigger errors and check that resources are not exhausted


### 🔗 References 
CWE-636: Not Failing Securely ('Failing Open')

CWE-755: Improper Handling of Exceptional Conditions

OWASP Error Handling Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
