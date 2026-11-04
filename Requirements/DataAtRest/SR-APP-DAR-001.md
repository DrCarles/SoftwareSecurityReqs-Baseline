### 📌 Requirement

**The application must encrypt all sensitive data at rest using strong, industry-standard encryption algorithms**


### 💡 Rationale 

Encrypting data at rest ensures that sensitive information remains protected even if storage media is accessed without authorization. Without encryption, attackers who gain access to storage systems can easily read and extract sensitive data

Note that full-disk or hard drive encryption alone is not sufficient. While it protects data when the device is powered off, it does not prevent access when the system is running and the disk is mounted. Data at rest encryption ensures that data remains protected even if attackers gain access to the operating system, files, or storage services


### ⚙️ Specifications 

- 📘 The application should encrypt all data 

- 📘 The application must encrypt sensitive data 

- 📘 Data encryption must rely on strong encryption approved security function by NIST

- 📘 Data encryption must cover cover all storage layers, including primary databases, logs, and backups

- 📘 The application must perform proper encrypting key management


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Identify every place where sensitive data is stored, including databases, files, logs, caches and backups
2. Access each storage directly (e.g. query the database with an administration tool, open the files, restore a backup) and check that sensitive data cannot be read in clear text
3. Check that the encryption algorithms in use are approved by NIST (e.g. AES) and that deprecated algorithms or modes (e.g. DES, 3DES, RC4, ECB) are not used
4. Check that encryption keys are not stored together with the encrypted data or in the source code, and that they are protected and rotated



### 🔗 References 

NIST SP 800-140C: Approved Security Functions


### ⬅️ Navigation 

[Back](Readme.md)
