### 📌 Requirement
**The application must use parameterized XPath and XQuery expressions, so that untrusted data cannot change the structure of a query**


### 💡 Rationale 
XPath injection works like SQL injection but targets XML documents. When untrusted data is concatenated into an XPath expression, attackers can bypass authentication or read parts of the XML document they should not see. Unlike databases, XML documents usually have no access control, so the whole document can be exposed

Using variables in XPath expressions keeps the data separate from the query structure


### ⚙️ Specifications 

- 📘 XPath and XQuery expressions that include variable data must use the library's variable or parameter binding (e.g. `XPathVariableResolver` in Java)

- 📘 XPath and XQuery expressions must not be built by concatenating strings with untrusted data

- 📘 When binding is not available, untrusted values must be validated against an allowlist of expected formats and quotes must be escaped


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Enter XPath payloads (e.g. `' or '1'='1`, `'] | //* | a['`) in inputs used in XML queries
2. Check that login is not bypassed and that no extra data is returned
3. Review the code for XPath expressions built with string concatenation


### 🔗 References 
CWE-643: Improper Neutralization of Data within XPath Expressions

OWASP Web Security Testing Guide: Testing for XPath Injection


### ⬅️ Navigation 

[Back](Readme.md)
