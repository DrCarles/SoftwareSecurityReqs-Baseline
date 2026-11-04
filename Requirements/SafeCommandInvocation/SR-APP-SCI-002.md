### 📌 Requirement
**The application must build NoSQL queries in a way that prevents untrusted data from adding operators or code to the query**


### 💡 Rationale 
NoSQL databases (e.g. MongoDB, CouchDB, Elasticsearch) do not use SQL, but they are still vulnerable to injection. Attackers can send objects instead of plain values (e.g. `{"$ne": null}` instead of a password) to change the query logic, or inject JavaScript into server-side operators such as `$where`

Making sure every input has the expected type and never contains query operators keeps the query logic under the control of the application


### ⚙️ Specifications 

- 📘 Queries must be built using the database driver's query builder or API, not by concatenating strings or JSON text

- 📘 The application must check that each input used in a query has the expected type (e.g. a string, not an object or array) before using it

- 📘 The application must reject or strip keys starting with operator characters (e.g. `$` and `.` in MongoDB) in data coming from users

- 📘 Server-side JavaScript execution in the database (e.g. `$where`, `mapReduce`, `$function`) must not be used with untrusted data, and should be disabled when not needed

- 📘 The database account used by the application must have only the permissions it needs


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Send operator objects instead of plain values in JSON bodies and parameters (e.g. `{"password": {"$ne": null}}`, `username[$ne]=x`) and check that they are rejected
2. Try to log in using operator payloads and check that authentication is not bypassed
3. Review the code for queries built from strings or from request objects passed directly to the database
4. Check whether server-side JavaScript execution is disabled in the database configuration


### 🔗 References 
CWE-943: Improper Neutralization of Special Elements in Data Query Logic

OWASP Web Security Testing Guide: Testing for NoSQL Injection


### ⬅️ Navigation 

[Back](Readme.md)
