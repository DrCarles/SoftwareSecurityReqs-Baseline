### 📌 Requirement
**The system must enforce automatic user log-off after a period of inactivity**


### 💡 Rationale 
Automatic log-off after a period of inactivity helps protect user accounts from unauthorized access, especially on shared or unattended devices. If a user forgets to log out, an attacker could exploit the open session. Enforcing time-based session expiration reduces this risk by ensuring that inactive sessions are securely terminated after a defined period


### ⚙️ Specifications 

- 📘 The system must automatically log-off users after a given timeout period of inactivity

- 📘 The default timeout period of inactivity before automatic log-off should be 10 minutes

- 📘 The system should allow configuring the default timeout period of inactivity before automatic log-off


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Login into the system
2. Wait for 10 minutes of inactivity
3. Check that the system automatically logs-off the user 


### 🔗 References 
TBD
