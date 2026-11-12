### 📌 Requirement
**The system must follow the principle of data minimization**


### 💡 Rationale 
The system must only collect, process, and store the minimum amount of sensitive data necessary to fulfill its intended business purpose. Limiting the amount of sensitive data handled by the system helps reduce the risk of data breaches, lowers the impact of potential security incidents, and simplifies regulatory compliance. Storing more data than needed increases both the risk and legal exposure without adding real value


### ⚙️ Specifications 

- 📘 The system must discard non-required sensitive data received from every input source

- 📘 The system must denaturalize discarded sensitive data received when writing to log files  


### 🧪 Testing tips 

For each data input source, verify that the system only processes and stores the minimum necessary sensitive data. Ensure that unnecessary data is neither saved to the database nor written to log files. Review log entries to confirm that sensitive fields are properly removed, or obfuscated


### 🔗 References 
GDPR Article 5(1)(c): Data minimisation

ISO/IEC 29100: Privacy framework



### ⬅️ Navigation 

[Back](Readme.md)
