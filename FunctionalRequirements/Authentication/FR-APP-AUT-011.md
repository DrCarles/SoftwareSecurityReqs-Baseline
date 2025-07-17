### 📌 Requirement
**User session must be immediately invalidated on the server side after user logs off**

_Note that stateless tokens like JWTs (JSON Web Tokens) cannot be easily invalidated on the server once issued. To help contain the risk of session hijacking, it's important to keep token expiration times short, so that compromised tokens become invalid quickly_

### 💡 Rationale 
Invalidating the session on the server after user log-off is critical to ensure that the session cannot be reused by unauthorized parties. Relying solely on client-side session termination is insufficient, as session tokens may still be active on the server and could be exploited if intercepted or reused.
Proper server-side invalidation ensures complete session termination, reducing the risk of session hijacking and unauthorized access


### ⚙️ Specifications 
_No specifications have been defined for this requirement_


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Log into the system as valid user
2. Capture the Session Id
3. Log off
4. Check that Session Id is no longer valid 


### 🔗 References 
TBD
