### 📌 Requirement
**The application must log all authorization decisions**


### 💡 Rationale 
Logging authorization decisions provides visibility into access control enforcement, supports auditing and incident investigation, and helps detect unauthorized or suspicious access attempts. It ensures that every access decision is traceable


### ⚙️ Specifications 

- 📘 For every authorization decision the application must log which user initiated the action   

- 📘 For every authorization decision the application must log what action was triggered 

- 📘 For every authorization decision the application must log what assets were affected 

- 📘 For every authorization decision the application must log when the action was initiated   


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Perform any action in the system
2. Check that the application has recorded a log trace
3. Check that the log trace contains the initiator user 
4. Check that the log trace contains the action triggered
5. Check that the log trace contains the affected asset 
6. Check that the log trace contains the timestamp 


### 🔗 References 
TBD
