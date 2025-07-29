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

TBD


### 🔗 References 

NIST SP 800-140C: Approved Security Functions
