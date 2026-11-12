### 📌 Requirement
**The application must base authorization decisions only on trusted information that users cannot manipulate, such as server-side sessions or signed tokens whose signature has been verified**


### 💡 Rationale 
Attackers control everything the client sends: form fields, URL parameters, cookies, headers and the request body. If the application decides what a user may do based on values such as `role=admin`, `isAdmin=true`, an `X-User-Id` header, or a JWT whose signature is never checked, an attacker only has to change that value to gain more privileges or access other users' data

The user's identity and permissions must come from a source the server controls (a server-side session or user store) or can verify (a signed token)


### ⚙️ Specifications 

- 📘 The identity, roles, permissions and tenant used in authorization decisions must come from a server-side session or data store, or from a token whose integrity has been verified (e.g. a signed JWT)

- 📘 The application must not use client-supplied values to decide authorization, such as hidden form fields, query parameters, request body fields, unsigned cookies, custom headers (e.g. `X-User-Id`, `X-Role`) or browser storage

- 📘 JWT signatures must be verified on every request, using an algorithm fixed on the server. Tokens with `alg: none` must be rejected, and the algorithm or key must not be taken from the token header (e.g. `alg`, `jku`, `x5u`, unrestricted `kid`)

- 📘 JWT claims must be validated, including expiration (`exp`), not-before (`nbf`), issuer (`iss`) and audience (`aud`)

- 📘 Resource identifiers sent by the client (e.g. `/orders/123`) must be checked against the authenticated user's permissions, never assumed to be authorized

- 📘 Identity headers added by an upstream component (e.g. an API gateway) may be trusted only if the application can be reached solely through that component, and that component removes any copies sent by the client

- 📘 Tokens should have short lifetimes, or permissions should be re-checked on the server for sensitive actions, so that role changes and revoked access take effect quickly


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Intercept requests and change user, role or permission values in parameters, body fields, cookies and headers (e.g. `role=admin`, another user's ID), and check that access is denied
2. Change the payload of a JWT without re-signing it and check that the token is rejected
3. Send JWTs with `alg: none`, a switched algorithm (e.g. HS256 signed with the public key), an expired date or a wrong audience (e.g. with jwt_tool), and check that they are rejected
4. Add identity headers (e.g. `X-User-Id`, `X-Forwarded-User`) to requests and check that they are ignored
5. Remove a role from a logged-in user and check that the related access is lost within the defined time


### 🔗 References 
CWE-807: Reliance on Untrusted Inputs in a Security Decision

CWE-565: Reliance on Cookies without Validation and Integrity Checking in a Security Decision

CWE-639: Authorization Bypass Through User-Controlled Key

CWE-347: Improper Verification of Cryptographic Signature

RFC 8725: JSON Web Token Best Current Practices

OWASP JSON Web Token Cheat Sheet

OWASP Authorization Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
