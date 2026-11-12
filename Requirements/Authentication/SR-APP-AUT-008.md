### 📌 Requirement
**The system must log all relevant user management activities**


### 💡 Rationale 
Logging all relevant user management activities—such as account creation, deletion, password changes and lockouts—is essential for security monitoring, auditing, and incident response. These logs provide a traceable record of actions that can help detect suspicious behaviour, support forensic investigations, and demonstrate compliance with security and privacy regulations


### ⚙️ Specifications 

- 📘 The system must log user creation 

- 📘 The system must log user deletion 

- 📘 The system must log user password change   

- 📘 The system must log user password reset  

- 📘 The system must log user lockout 

- 📘 The system must log user unlock 


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Create a new user in the system  
2. Check that user creation is logged 
3. Delete an existent user 
4. Check that user deletion is logged 
5. Change the password of an existent user 
6. Check that password change is logged 
7. Reset the password of an existent user 
8. Check that password reset is logged 
9. Lock an existent user 
10. Check that user lockout is logged 
11. Unlock an existent user 
12. Check that user unlock is logged 


### 🔗 References 
CWE-778: Insufficient Logging

NIST SP 800-53 Rev. 5: AU-2 Event Logging

OWASP Logging Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
