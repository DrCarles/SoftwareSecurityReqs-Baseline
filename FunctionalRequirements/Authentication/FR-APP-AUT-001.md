### 📌 Requirement
**Each user in the system must be assigned a unique identifier that is never reused, even after the user account is deleted or deactivated**


### 💡 Rationale 
Using non-reusable unique identifiers is essential for reliable auditing and accountability

If user IDs are reused, it becomes difficult to determine which individual performed which actions, as the same ID could represent different people over time. This undermines the integrity of audit logs and incident investigations


### ⚙️ Specifications 

- 📘 The unique identifier must be a GUID to prevent IDOR attacks  

- 📘 The unique identifier must be randomly generated on user creation 


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Create a new user in the system
2. Check the GUID of the new user
3. Remove the user and create the same user again
4. Check that the new user has a different GUID and the original GUID is not reused 


### 🔗 References 
TBD


### ⬅️ Navigation 

[Back](Readme.md)
