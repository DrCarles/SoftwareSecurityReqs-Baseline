### 📌 Requirement

**The application must sanitize all outgoing data before transmitting it to external systems, ensuring it does not contain executable or unsafe content**


### 💡 Rationale 

Output sanitization is critical to protecting users and systems from a range of attacks, particularly Cross-Site Scripting, and data leakage vulnerabilities. Even if data is safely stored, it may become dangerous when reflected back to users, especially if it includes user-generated content or inputs from untrusted sources

By sanitizing output, the application ensures that executable content such as HTML, JavaScript, or CSS is properly escaped or removed before reaching the frontend. This helps prevent the accidental exposure of sensitive internal data and makes it significantly harder for attackers to exploit reflected or stored vulnerabilities. It also protects against threats like session hijacking, unauthorized actions, and data exfiltration


### ⚙️ Specifications 

- 📘 The application must encode output for the context where it is used (e.g. HTML body, HTML attribute, JavaScript, URL, CSS)



### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Enter script payloads (e.g. `<script>alert(1)</script>`, `"><img src=x onerror=alert(1)>`) in inputs that are later displayed, and check that they are shown as text and not executed
2. Repeat the test for data displayed in different contexts, such as HTML attributes, JavaScript, URLs and CSS
3. Check that stored data is also safely displayed in other pages and to other users
4. Review the templates and check that automatic output encoding is enabled and that raw output functions are not used with untrusted data



### 🔗 References 
CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')

CWE-116: Improper Encoding or Escaping of Output

OWASP Cross Site Scripting Prevention Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
