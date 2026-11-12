## 🔑 Error Handling Requirements

This section contains security requirements focused on handling errors so that the application fails in a safe state and does not reveal information that could help an attacker

Errors are not only a reliability problem. Attackers deliberately send unexpected input to trigger errors, then use the application's behavior and error messages to find weaknesses and plan their next steps


### 🌩 Common Risks:

Poor error handling can lead to several serious security issues, including:

1. Information Disclosure: Detailed error messages, stack traces and debug pages can reveal technologies and versions in use, file paths, database structure, queries, configuration or even credentials

2. Security Control Bypass: When an error occurs during a security check, such as authentication or authorization, the application may continue as if the check succeeded and grant access

3. Inconsistent State: Errors in the middle of an operation can leave data partially updated, which can be abused, for example to obtain goods or credits without paying

4. Denial of Service: Unhandled errors can crash the application or leave resources such as connections, files or memory locked, making the service unavailable

5. User and Data Enumeration: Different error messages or behavior for different situations can reveal whether users, files or records exist


### 📌 Requirements:

- [Fail safe](SR-APP-ERR-001.md)
- [Generic error messages](SR-APP-ERR-002.md)
- [Centralized error handling](SR-APP-ERR-003.md)
- [Production error configuration](SR-APP-ERR-004.md)


### ⬅️ Navigation 

[Back](../../README.md)
