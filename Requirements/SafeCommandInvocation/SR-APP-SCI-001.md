### 📌 Requirement
**The application must use parameterized queries when sending data to SQL databases, so that untrusted data can never change the structure of a query**


### 💡 Rationale 
SQL injection happens when untrusted data is concatenated into a query string and the database interprets part of that data as SQL code. An attacker can then read, modify or delete data, bypass authentication, or in some cases execute commands on the database server

Parameterized queries (prepared statements) send the query structure and the data separately, so the database always treats the data as a value and never as code. This removes the root cause instead of trying to detect dangerous characters


### ⚙️ Specifications 

- 📘 All SQL queries that include variable data must use parameterized queries or prepared statements

- 📘 SQL queries must not be built by concatenating or formatting strings with untrusted data

- 📘 ORM features that accept raw SQL (e.g. raw queries, native queries, query fragments) must be used with parameters, the same as plain SQL

- 📘 Stored procedures must not build dynamic SQL from their parameters unless it is parameterized inside the procedure

- 📘 Query parts that cannot be parameterized, such as table names, column names or sort direction, must be selected from an allowlist of fixed values defined in the code

- 📘 The database account used by the application must have only the permissions it needs (e.g. no administrative or schema-changing rights for normal operation)


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Review the code for SQL built with string concatenation, interpolation or formatting functions
2. Enter SQL metacharacters and payloads (e.g. `'`, `' OR '1'='1`, `'; --`) in every input that reaches the database and check that they are stored or searched as plain text
3. Test sort, filter and column-selection parameters with values outside the allowed list and check that they are rejected
4. Run an automated scanner (e.g. sqlmap) against the application in a test environment
5. Check the permissions granted to the application's database account


### 🔗 References 
CWE-89: Improper Neutralization of Special Elements used in an SQL Command

OWASP SQL Injection Prevention Cheat Sheet

OWASP Query Parameterization Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
