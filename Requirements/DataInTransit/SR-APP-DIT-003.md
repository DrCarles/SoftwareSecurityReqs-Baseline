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
Suggested test steps for verifying this requirement:
1. Identify all communication channels between internal components (e.g. services, databases, message brokers, caches)
2. Capture the traffic between components (e.g. with tcpdump or Wireshark) and check that it is encrypted
3. Scan internal endpoints with a TLS testing tool (e.g. testssl.sh, sslyze) and check that only supported TLS versions and strong cipher suites are enabled
4. Replace the certificate of an internal service with an invalid or self-signed one and check that the other components reject the connection
5. Where mutual TLS is enforced, connect without a client certificate and check that the connection is rejected



### 🔗 References 
CWE-319: Cleartext Transmission of Sensitive Information

CWE-295: Improper Certificate Validation

NIST SP 800-52 Rev. 2: Guidelines for the Selection, Configuration, and Use of TLS Implementations

OWASP Transport Layer Security Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
