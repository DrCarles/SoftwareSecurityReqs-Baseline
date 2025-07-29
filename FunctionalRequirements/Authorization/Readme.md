## 🔑 User Authorization Requirements

This section contains a set of functional cybersecurity requirements specifically related to user authorization

### 🌩 Common Risks:

User authorization requirements are designed to prevent the following common risks by default:

1. Vertical Broken Access Control: This occurs when a user can access functions or data reserved for users with higher permission levels. For instance: a regular user can reset the password of any other user 

2. Horizontal Broken Access Control: This occurs when a user can access or manipulate data or resources that belong to other users. For instance: a regular user can edit his profile and the profile of other users 


### 📌 Requirements:
- [Business-logic enforcement](FR-APP-AUZ-001.md)
- [Deny by default](FR-APP-AUZ-002.md)
- [Structured permissions](FR-APP-AUZ-003.md)
- [Role-Based Access Control](FR-APP-AUZ-004.md)
- [Secure configuration by default](FR-APP-AUZ-005.md)
- [Log and traceability](FR-APP-AUZ-006.md)


### ⬅️ Navigation 

[Back](../../README.md)
