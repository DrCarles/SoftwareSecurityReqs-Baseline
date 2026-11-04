### 📌 Requirement
**The application must never use untrusted data as template code, and must pass it to template engines only as data**


### 💡 Rationale 
Template engines (e.g. Jinja2, Twig, Freemarker, Velocity, Thymeleaf, Handlebars) are powerful languages. When user input becomes part of the template itself, instead of a value rendered by it, attackers can run expressions that often lead to remote code execution on the server

Keeping templates fixed in the code and passing user data as variables prevents this


### ⚙️ Specifications 

- 📘 Templates must be loaded from trusted sources (e.g. files in the application) and must not be built from untrusted data

- 📘 Untrusted data must be passed to templates only as variables (context data)

- 📘 Template engines must have automatic output escaping enabled

- 📘 When users must be able to edit templates (e.g. email templates), the application must use a logic-less template engine or the engine's sandbox mode, and limit the objects and functions available to the template

- 📘 The same rules apply to expression languages used outside templates (e.g. Spring Expression Language, OGNL, Java EL)


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Enter template expressions in inputs that are rendered back (e.g. `{{7*7}}`, `${7*7}`, `<%= 7*7 %>`, `#{7*7}`) and check that the result is not `49`
2. Review the code for templates created from strings that include user data
3. Check that auto-escaping is enabled in the template engine configuration
4. If users can edit templates, check that the sandbox blocks access to system classes and functions


### 🔗 References 
CWE-1336: Improper Neutralization of Special Elements Used in a Template Engine

CWE-917: Improper Neutralization of Special Elements used in an Expression Language Statement

OWASP Web Security Testing Guide: Testing for Server-side Template Injection


### ⬅️ Navigation 

[Back](Readme.md)
