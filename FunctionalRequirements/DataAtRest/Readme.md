## 🔑 Data at Rest Requirements

This section contains a set of cybersecurity requirements specifically related to data stored in persistent systems, such as databases, file systems, backups, and local storage


### 🌩 Common Risks:

Data at rest is vulnerable to a variety of threats if not properly protected. These requirements are designed to mitigate the following common risks:

1. Unauthorized Access: Improper access controls, misconfigured storage permissions, or weak authentication can allow attackers or unauthorized users to access sensitive data stored on disk

2. Data Theft or Breach: If storage systems are compromised, unencrypted data may be stolen and exfiltrated, leading to data breaches

3. Insider Threats: Employees or administrators with unnecessary access to stored data may misuse or leak it, either intentionally or accidentally

4. Data Loss: Without proper encryption secure backup strategies data can be lost due to corruption, deletion, mismanagement, or system failures—impacting business continuity


### 📌 Requirements:

- [Backup and Restore](FR-APP-DAR-003.md)
- [Data Encryption](FR-APP-DAR-001.md)
- [Least Privilege](FR-APP-DAR-002.md)


### ⬅️ Navigation 

[Back](../../README.md)