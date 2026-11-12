### 📌 Requirement
**The application must avoid calling operating system commands, and when it must, it must invoke them without a shell and pass untrusted data only as separate arguments**


### 💡 Rationale 
OS command injection happens when untrusted data is placed into a command string that is run by a shell. Characters such as `;`, `|`, `&`, `$()` or backticks let the attacker chain their own commands, which usually leads to full compromise of the server

The safest option is to use a library or language feature instead of an external program. When an external program is needed, starting it directly with an argument list (without a shell) means the data is never interpreted as shell syntax


### ⚙️ Specifications 

- 📘 The application should use built-in libraries or APIs instead of calling OS commands (e.g. a file API instead of `cp`, an image library instead of a command line tool)

- 📘 OS commands must be started directly with an array of arguments, without a shell (e.g. `subprocess.run([...], shell=False)` in Python, `ProcessBuilder` in Java, `execFile` instead of `exec` in Node.js)

- 📘 Functions that pass a single command string to a shell (e.g. `system()`, `os.system`, `Runtime.exec(String)`, `shell_exec`) must not be used with untrusted data

- 📘 The program to run must be fixed in the code or chosen from an allowlist, and must be referenced by its full path

- 📘 Untrusted data must not be able to add options to the command (argument injection), e.g. by validating that values do not start with `-` and by using `--` to mark the end of options when the program supports it

- 📘 Untrusted values passed as arguments should be validated against an allowlist of expected formats

- 📘 The process running the command must have only the permissions it needs


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Review the code for calls that start OS commands and check how arguments are built
2. Enter shell metacharacters and payloads (e.g. `; id`, `| whoami`, `$(sleep 10)`) in inputs that reach commands and check that they are not executed
3. Use time-based or out-of-band payloads (e.g. `sleep`, DNS lookups) to detect blind command injection
4. Enter values starting with `-` or `--` and check that they are not treated as options
5. Check the permissions of the account running the application


### 🔗 References 
CWE-78: Improper Neutralization of Special Elements used in an OS Command

CWE-88: Improper Neutralization of Argument Delimiters in a Command

OWASP OS Command Injection Defense Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
