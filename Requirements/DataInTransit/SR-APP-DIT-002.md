### 📌 Requirement
**The application must use secure communication channels for external communications**


### 💡 Rationale 

Using secure communication channels ensures that data transmitted between the application and external entities is encrypted, protecting it from interception, tampering, and eavesdropping. Without proper encryption, sensitive data such as credentials, tokens, personal information, and business logic can be exposed to attackers, especially over untrusted networks like the internet

Secure channels such as TLS not only provide confidentiality, but also support integrity, and authentication by verifying the identity of the remote party


### ⚙️ Specifications 

- 📘 The application must use a supported, non-deprecated version of TLS. Older versions must be disabled

- 📘 TLS configurations must be hardened to avoid the use of weak or vulnerable cipher suites

- 📘 The application must either present a valid server certificate or verify the server’s certificate when acting as a client

- 📘 Where feasible, the application should support and enforce mutual TLS to ensure both the client and server authenticate each other  


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Scan every external endpoint with a TLS testing tool (e.g. testssl.sh, sslyze) and check that only supported TLS versions (e.g. TLS 1.2 and 1.3) and strong cipher suites are enabled
2. Check that server certificates are valid, issued by a trusted authority, not expired and match the hostname
3. Make the application, acting as a client, connect to a server with an invalid or self-signed certificate (e.g. through an interception proxy) and check that the connection is rejected
4. Check that unencrypted connections (e.g. plain HTTP) are rejected or redirected to a secure channel
5. Where mutual TLS is enforced, connect without a client certificate and check that the connection is rejected



### 🔗 References 
CWE-319: Cleartext Transmission of Sensitive Information

CWE-295: Improper Certificate Validation

NIST SP 800-52 Rev. 2: Guidelines for the Selection, Configuration, and Use of TLS Implementations

OWASP Transport Layer Security Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
