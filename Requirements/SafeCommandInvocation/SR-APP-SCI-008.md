### 📌 Requirement
**The application must not evaluate untrusted data as code at runtime**


### 💡 Rationale 
Functions that run strings as code (e.g. `eval`, `exec`, `Function()`, script engines) give an attacker direct code execution on the server, or in the user's browser for client-side code, if any part of that string comes from them

There is almost always a safer alternative, such as a parser for the expected data format or a lookup table of allowed operations


### ⚙️ Specifications 

- 📘 The application must not pass untrusted data to functions that evaluate code (e.g. `eval`, `exec`, `new Function()`, `setTimeout` with a string, `compile`, script engines)

- 📘 Data formats must be read with dedicated parsers (e.g. `JSON.parse` instead of `eval`, `ast.literal_eval` instead of `eval` in Python)

- 📘 The application must not dynamically load classes, modules or files whose names come from untrusted data, unless they are selected from an allowlist

- 📘 When the application must allow users to define logic (e.g. formulas, rules, plugins), it must use a restricted expression language or a sandbox with limited access to system functions


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Search the code for code evaluation functions and check whether any input can reach them
2. Enter code payloads suited to the language (e.g. `__import__('os').system('id')`, `require('child_process')`, `1+1`) in inputs and check that they are not executed
3. Use static analysis tools to find flows from user input to code evaluation functions


### 🔗 References 
CWE-94: Improper Control of Generation of Code ('Code Injection')

CWE-95: Improper Neutralization of Directives in Dynamically Evaluated Code ('Eval Injection')


### ⬅️ Navigation 

[Back](Readme.md)
