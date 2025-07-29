## 🔑 Data in Transit

This section contains a set of cybersecurity requirements specifically related to data communications  


### 🌩 Common Risks:

Data in transit is vulnerable to a variety of threats if not properly protected. These requirements aim to prevent the following common risks:

1. Interception: Unencrypted or weakly encrypted communications can be intercepted by attackers, allowing them to read sensitive data such as credentials, personal information, or session tokens

2. Man-in-the-Middle Attacks: Attackers may intercept and alter communications between two parties without their knowledge. This can lead to data tampering, impersonation, or unauthorized access

3. Data Integrity Violations: Without proper integrity checks, data may be altered in transit, either accidentally or maliciously, without detection

4. Weak or Misconfigured Encryption: Using outdated encryption protocols  or misconfigured TLS settings leaves communications exposed


### 📌 Requirements:

- [Limited exposure](FR-APP-DIT-001.md)
- [Secure external channels](FR-APP-DIT-002.md)
- [Secure internal channels](FR-APP-DIT-003.md)


### ⬅️ Navigation 

[Back](../../README.md)