### 📌 Requirement
**Authorization must be enforced at the business logic layer, not just in the presentation layer**


### 💡 Rationale 
Relying on presentation-layer controls (like UI elements) to enforce authorization is insecure, as these can be bypassed by manipulating requests directly, specially in web applications. Implementing authorization checks in the business logic layer ensures that access control is consistently applied, regardless of how the request is made


### ⚙️ Specifications 
_No specifications have been defined for this requirement_


### 🧪 Testing tips 
Suggested test steps for verifying this requirement (on a REST API):
1. Log in in the REST API as valid user 
2. Send requests to every API endpoints
3. Check that allowed actions are consistent with user permissions 


### 🔗 References 
TBD
