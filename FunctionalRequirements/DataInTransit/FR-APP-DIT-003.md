### 📌 Requirement
**The application should use secure communication channels for internal communications**


### 💡 Rationale 

Even within internal networks, communication is not automatically secure. Using secure communication channels ensures that data transmitted between the application and internal entities is encrypted, protecting it from interception, tampering, and eavesdropping. Without proper encryption, sensitive data such as credentials, tokens, personal information, and business logic can be exposed to attackers

Secure channels such as TLS not only provide confidentiality, but also support integrity, and authentication by verifying the identity of the remote party


### ⚙️ Specifications 

- 📘 The application must use a supported, non-deprecated version of TLS. Older versions must be disabled

- 📘 TLS configurations must be hardened to avoid the use of weak or vulnerable cipher suites

- 📘 The application must either present a valid server certificate or verify the server’s certificate when acting as a client

- 📘 Where feasible, the application should support and enforce mutual TLS to ensure both the client and server authenticate each other  


### 🧪 Testing tips 
TBD


### 🔗 References 
TBD
