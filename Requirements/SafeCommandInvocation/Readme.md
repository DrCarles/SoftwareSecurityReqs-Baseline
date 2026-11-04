## 🔑 Safe Command Invocation Requirements

This section contains security requirements focused on safely passing data to interpreters, such as databases, operating system shells, XML parsers, directory services and template engines, to protect the system from injection attacks

The core principle behind all of them is to keep code and data separate: untrusted data must never be able to change the structure or meaning of the command, query or document it is placed into. Input validation and output sanitization (see [Data Sanitization](../DataSanitization/Readme.md)) are useful additional layers, but they are not a replacement for safe invocation


### 🌩 Common Risks:

Invoking interpreters unsafely can lead to several serious security issues, including:

1. Data Breach: Injected queries can read, modify or delete any data the application's account can reach, including credentials and personal data

2. Remote Code Execution: Injected OS commands, templates, code or serialized objects can run arbitrary code on the server, leading to full system compromise

3. Authentication and Authorization Bypass: Injected query logic can bypass login checks or access controls

4. Server-Side Request Forgery and File Disclosure: Malicious XML can make the server read local files or connect to internal systems

5. Denial of Service: Crafted inputs, such as recursive XML entities, can exhaust server resources

6. Log and Response Tampering: Injected line breaks can forge log entries or split HTTP responses, hiding attacks or enabling other attacks against users


### 📌 Requirements:

- [SQL injection prevention](SR-APP-SCI-001.md)
- [NoSQL injection prevention](SR-APP-SCI-002.md)
- [OS command injection prevention](SR-APP-SCI-003.md)
- [XML External Entity (XXE) prevention](SR-APP-SCI-004.md)
- [LDAP injection prevention](SR-APP-SCI-005.md)
- [XPath injection prevention](SR-APP-SCI-006.md)
- [Server-side template injection prevention](SR-APP-SCI-007.md)
- [Dynamic code evaluation prevention](SR-APP-SCI-008.md)
- [Safe deserialization](SR-APP-SCI-009.md)
- [CRLF injection prevention](SR-APP-SCI-010.md)


### ⬅️ Navigation 

[Back](../../README.md)
