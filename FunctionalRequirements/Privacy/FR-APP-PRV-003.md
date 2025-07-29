### 📌 Requirement
**The system must support the right to erasure of PII**


### 💡 Rationale 
Under GDPR, the right to erasure gives individuals the ability to request the deletion of their Personal Identifiable Information (PII) in certain situations. To comply with this requirement, the system must be designed from the start to support secure, auditable, and timely data deletion when such requests are made


### ⚙️ Specifications 

- 📘 Data fields containing PII must no be used as primary keys in relational databases

- 📘 Data fields containing PII must not be used as foreign keys in relational databases

- 📘 Data fields containing PII must be nullable in relational databases

- 📘 PII data must not be written in application logs 


### 🧪 Testing tips 

Review each data storage component to ensure that PII can be deleted or obfuscated without impacting system integrity. Verify that database schemas allow for null values in PII fields and that application logs do not contain any traces of sensitive personal data


### 🔗 References 
GDPR
