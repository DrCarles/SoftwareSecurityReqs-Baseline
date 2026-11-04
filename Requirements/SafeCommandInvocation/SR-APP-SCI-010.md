### 📌 Requirement
**The application must neutralize line break characters in untrusted data before writing it to HTTP headers, log entries or other line-based protocols**


### 💡 Rationale 
Many formats use carriage return and line feed characters (CRLF, `\r\n`) to separate lines or fields. When untrusted data containing these characters is written to an HTTP header, an attacker can add their own headers or split the response (HTTP response splitting)

When written to a log file, an attacker can forge fake log entries to hide their activity or mislead investigations. The same applies to email headers and other line-based protocols


### ⚙️ Specifications 

- 📘 Untrusted data written to HTTP headers (e.g. redirects, cookies, custom headers) must not contain CR or LF characters, and the application should rely on frameworks that reject them

- 📘 Untrusted data written to logs must be encoded or have CR, LF and other control characters replaced before being logged

- 📘 The application should use structured logging (e.g. JSON log entries) so that user data is always stored as a field value

- 📘 Untrusted data used in email headers (e.g. subject, recipients) must not contain CR or LF characters, and should be set through the mail library's API instead of building raw headers


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Enter values with encoded line breaks (e.g. `%0d%0aSet-Cookie:%20test=1`) in parameters reflected in response headers, such as redirect URLs, and check that no new header appears
2. Enter values with line breaks in fields that are logged (e.g. usernames on failed login) and check that they do not create new log lines
3. Enter line breaks in fields used in emails (e.g. contact forms) and check that no extra recipients or headers are added


### 🔗 References 
CWE-93: Improper Neutralization of CRLF Sequences ('CRLF Injection')

CWE-113: Improper Neutralization of CRLF Sequences in HTTP Headers ('HTTP Response Splitting')

CWE-117: Improper Output Neutralization for Logs

OWASP Logging Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
