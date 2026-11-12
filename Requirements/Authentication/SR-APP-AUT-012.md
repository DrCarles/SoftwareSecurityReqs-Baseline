### 📌 Requirement
**The system must re-authenticate the user before allowing any security-sensitive action**


### 💡 Rationale 
Re-authentication adds an extra layer of protection when users perform security-sensitive actions such as changing a password, generating API keys, or modifying critical settings. This helps prevent unauthorized actions by an attacker who may have hijacked an active session or gained access to an unattended device, ensuring that the user's identity is verified before proceeding 


### ⚙️ Specifications 
_No specifications have been defined for this requirement_


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Log into the system as valid user
2. Make a sensitive action such as password change 
4. Check that the system requests re-authentication  


### 🔗 References 
CWE-620: Unverified Password Change

OWASP Authentication Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
