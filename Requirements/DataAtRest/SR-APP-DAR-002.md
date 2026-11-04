### 📌 Requirement

**The application must enforce the principle of least privilege on all data access, ensuring users and processes can only access the data necessary for their roles and tasks**


### 💡 Rationale 

Enforcing least privilege minimizes the risk of accidental or intentional misuse of sensitive data by restricting access strictly to what is required. Limiting data access reduces the attack surface, making it harder for attackers to gain unauthorized information if they compromise a user account or a component

This approach also helps contain potential damage caused by insider threats, application bugs, or compromised credentials by preventing unnecessary access to sensitive or critical data

For example, if an application module only needs to collect usage statistics from the database, it should connect using a read-only user that has permission to access only the specific tables required. It should not use a full database administrator account with broad access to all data


### ⚙️ Specifications 

_No specifications have been defined for this requirement_


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. List the accounts used by the application and its components to access data (e.g. database users, service accounts, storage roles)
2. Review the permissions granted to each account and check that they are limited to what its task requires
3. Using each account, try to access data or perform operations outside its task (e.g. write with a read-only account, read other tables) and check that access is denied
4. Check that administrator accounts are not used for normal operation



### 🔗 References 
CWE-272: Least Privilege Violation

NIST SP 800-53 Rev. 5: AC-6 Least Privilege



### ⬅️ Navigation 

[Back](Readme.md)
