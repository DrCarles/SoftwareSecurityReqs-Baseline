### 📌 Requirement
**The system must implement protection mechanisms against brute-force password guessing attacks**


### 💡 Rationale 
Brute-force attacks involve repeatedly attempting different password combinations until the correct one is found. Without protection mechanisms, automated tools can exploit this vulnerability to gain unauthorized access. Implementing safeguards reduces the effectiveness of brute-force attempts and helps protect user accounts from compromise


### ⚙️ Specifications 

- 📘 The system must lock for 5 minutes a user after 5 incorrect login attempts

- 📘 The system must lock an IP for 5 minutes after 5 incorrect login attempts

- 📘 The system must log and notify locked user accounts or locked IPs


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Try login into the system with valid username (User A) and invalid credentials
2. Check that after 5 login attempts the user gets locked
3. Check that user lock is reported 
4. Wait 5 minutes
5. Login into the system with valid username (User A) and valid credentials
6. Check that user login is performed
7. Try login into the system with invalid username and invalid credentials
8. Check that after 5 login attempts your IP gets locked
9. Check that IP lock is reported 
10. Wait 5 minutes
11. Login into the system with valid username and valid credentials
12. Check that user login is performed


### 🔗 References 
TBD
