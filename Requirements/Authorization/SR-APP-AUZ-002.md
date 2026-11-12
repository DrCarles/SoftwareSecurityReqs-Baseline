### 📌 Requirement
**The system must follow a deny by default approach, allowing actions only when explicitly authorized**


### 💡 Rationale 
A "deny by default" policy helps minimize security risks by ensuring that no user or process can perform an action unless it has been explicitly granted permission. This reduces the chances of unintended access due to misconfiguration or oversight


### ⚙️ Specifications 
_No specifications have been defined for this requirement_


### 🧪 Testing tips 

- Attempt to perform various actions with user accounts or roles that have no explicit permissions assigned; verify that all actions are denied by default

- Test users with specific permissions to confirm that only authorized actions are allowed, and any other actions are blocked

- Review system behavior after adding new actions or features to ensure that access is denied until permissions are explicitly granted

- Perform negative testing by sending unauthorized requests (e.g., API calls, UI actions) and verify that the system consistently enforces denial without exception

- Check logs or audit trails to confirm that denied access attempts are properly recorded for accountability 


### 🔗 References 
CWE-285: Improper Authorization

OWASP Top 10: Broken Access Control

OWASP Authorization Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
