### 📌 Requirement
**The application must escape untrusted data before using it in LDAP queries and distinguished names**


### 💡 Rationale 
LDAP injection happens when untrusted data is placed into an LDAP search filter or distinguished name (DN) without escaping. Characters such as `*`, `(`, `)` and `\` let an attacker change the filter, for example to bypass authentication or list all users in the directory

Most LDAP libraries have no equivalent of parameterized queries, so correct escaping for each context is the main defense


### ⚙️ Specifications 

- 📘 Untrusted data used in LDAP search filters must be escaped using a filter-escaping function from a trusted library

- 📘 Untrusted data used in distinguished names must be escaped using a DN-escaping function from a trusted library

- 📘 Untrusted values should be validated against an allowlist of expected formats (e.g. usernames limited to letters, digits and a few symbols)

- 📘 The account used by the application to connect to the directory must have only the permissions it needs, and anonymous binds must not be used for authentication

- 📘 Authentication must check that the password is not empty before binding, to avoid unauthenticated binds being accepted as valid


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Enter LDAP metacharacters and payloads (e.g. `*`, `*)(uid=*`, `admin)(&)`) in inputs used in directory queries, such as login and user search
2. Check that wildcards do not return more results than expected and that login is not bypassed
3. Try to log in with a valid username and an empty password
4. Review the code for LDAP filters built by concatenating strings without escaping


### 🔗 References 
CWE-90: Improper Neutralization of Special Elements used in an LDAP Query

OWASP LDAP Injection Prevention Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
