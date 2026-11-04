### 📌 Requirement

**The system must securely delete data when it is no longer needed, ensuring it cannot be recovered**


### 💡 Rationale 

Secure data disposal is essential to prevent unauthorized recovery of sensitive information after it is no longer required. Simply deleting a file or database entry is often insufficient, as data may still be retrievable from storage media, logs, backups, or caches

Improper data disposal increases the risk of data leakage, especially when devices are repurposed, decommissioned, or compromised. Secure disposal techniques help ensure that personal, confidential, or regulated data is permanently and irreversibly removed


### ⚙️ Specifications 

_No specifications have been defined for this requirement_


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Delete a record containing sensitive data through the application
2. Check directly in the database that the data is removed, and not only marked as deleted
3. Check that copies of the data in logs, caches, temporary files and search indexes are also removed
4. Check that backups containing the data expire according to the retention policy, or that the data is made unrecoverable (e.g. by deleting its encryption key)
5. Review the procedure for decommissioning storage media and check that it follows a recognized media sanitization guideline (e.g. NIST SP 800-88)



### 🔗 References 

GDPR


### ⬅️ Navigation 

[Back](Readme.md)
