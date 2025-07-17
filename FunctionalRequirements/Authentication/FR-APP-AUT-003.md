### 📌 Requirement
**The system must enforce a strong password-complexity policy** 


### 💡 Rationale 
Weak passwords enable password guessing attacks


### ⚙️ Specifications 
- 📘 Passwords must be a minimum of eight characters in length and should be a minimum of 15 characters in length

- 📘 The system must permit a maximum password length of at least 64 characters

- 📘 The system should accept all printing ASCII characters and the space character in passwords

- 📘 The system should accept accept Unicode characters in passwords

- 📘 The system should not impose other composition rules (e.g., requiring mixtures of different character types) for passwords

- 📘 The system should not require users to change passwords periodically. However, the system should force a change if there is evidence of compromise of the authenticator

- 📘 The system should not permit the subscriber to store a hint that is accessible to an unauthenticated claimant

- 📘 The system should not prompt subscribers to use knowledge-based authentication (e.g., “What was the name of your first pet?”) or security questions when choosing passwords

- 📘 The system must verify the entire submitted password (i.e., not truncate it)

- 📘 When processing a request to establish or change a password, the system should compare the prospective secret against a blocklist that contains known commonly used, expected, or compromised passwords


### 🧪 Testing tips 
Ensure that password complexity requirements are consistently enforced across all password-related actions. This includes when a user creates a new account, voluntarily changes their own password, or when an administrator sets or resets a user's password. In every case, verify that the system applies the same complexity rules to maintain a consistent security standard


### 🔗 References 
- NIST Special Publication 800-63B
