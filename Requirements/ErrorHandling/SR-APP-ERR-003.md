### 📌 Requirement
**The application must handle all errors, including unexpected ones, through a centralized error handling mechanism**


### 💡 Rationale 
When each part of the code handles errors in its own way, some errors are inevitably missed. Unhandled errors can crash the application, leave it in an unknown state, or fall through to the default error pages of the framework or server, which often show detailed technical information

A centralized error handler acts as a safety net: whatever error happens, it is logged in the same way and the user gets the same safe response


### ⚙️ Specifications 

- 📘 The application must have a global error handler that catches every error not handled elsewhere, at every entry point (e.g. web requests, API calls, background jobs, message consumers)

- 📘 The global error handler must log the error and return a generic response, as described in [Generic error messages](SR-APP-ERR-002.md)

- 📘 Errors must not be silently ignored (e.g. empty `catch` blocks); every caught error must be handled, logged or passed on

- 📘 Code should catch specific error types it knows how to handle, instead of catching all errors and continuing as if nothing happened

- 📘 Unhandled errors must not stop the whole application or affect other users' requests

- 📘 The application should monitor error rates and alert when they increase unexpectedly, since this can indicate an attack in progress


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Review the code and configuration for a global error handler at each entry point
2. Search the code for empty `catch` blocks and for errors that are caught and ignored
3. Trigger unexpected errors (e.g. invalid input, unavailable dependencies) and check that responses are consistent and generic, and that each error is logged
4. Trigger errors in background jobs and message consumers and check that they are logged and do not stop processing


### 🔗 References 
CWE-248: Uncaught Exception

CWE-390: Detection of Error Condition Without Action

CWE-396: Declaration of Catch for Generic Exception

OWASP Error Handling Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
