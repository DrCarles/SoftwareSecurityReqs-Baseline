### 📌 Requirement
**The system must store passwords in a secure, non-reversible format using a strong, industry-standard cryptographic hashing algorithm**


### 💡 Rationale 
Users often reuse the same password across multiple services. By storing passwords in a secure, non-reversible (hashed) format, the system prevents anyone with access to the database from seeing users' plain-text passwords and using them to try to log in to other websites or applications as those users


### ⚙️ Specifications 

- 📘 Hashing function must be a secure hash approved security function by NIST
  
- 📘 Hashed passwords must be salted 


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Create a new user (User A) with a known valid password
2. Check that the password in the database is not stored in cleartext
3. Create another user (User B) with the same known valid passsword
4. Check that hashed passwords of User A and User B are not identical  


### 🔗 References 
NIST SP 800-140C: Approved Security Functions


### ⬅️ Navigation 

[Back](Readme.md)
