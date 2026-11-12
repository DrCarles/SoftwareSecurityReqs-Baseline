### 📌 Requirement
**The application must disable debug features and replace default error pages in production environments**


### 💡 Rationale 
Frameworks, servers and platforms often show detailed error pages by default, and debug modes can expose source code, environment variables, configuration and sometimes even an interactive console that allows running code on the server. These features are useful during development but are a serious risk if left enabled in production

Default error pages and server headers also reveal which products and versions are in use, helping attackers look for known vulnerabilities


### ⚙️ Specifications 

- 📘 Debug modes, developer error pages and detailed error output must be disabled in production (e.g. `DEBUG=False` in Django, `ASPNETCORE_ENVIRONMENT=Production` in ASP.NET Core, `display_errors=Off` in PHP)

- 📘 Default error pages of the framework, application server, web server, proxy and load balancer must be replaced with custom generic pages

- 📘 Debug and diagnostic endpoints (e.g. Spring Boot Actuator, profilers, admin consoles, API documentation with internal details) must be disabled in production or protected by authentication and restricted to internal networks

- 📘 Responses should not include headers or content that reveal product names and versions (e.g. `Server`, `X-Powered-By`, `X-AspNet-Version`)

- 📘 Production error settings should be enforced by the deployment configuration, so that debug features cannot be enabled by mistake


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Check the production configuration for debug and error display settings
2. Trigger errors at each layer (e.g. invalid URLs, oversized requests, malformed headers) and check that every response uses a custom generic page
3. Try to access common debug and diagnostic paths (e.g. `/actuator`, `/debug`, `/console`, `/phpinfo.php`, `/trace.axd`) and check that they are not available
4. Inspect response headers and check that they do not reveal products or versions


### 🔗 References 
CWE-489: Active Debug Code

CWE-215: Insertion of Sensitive Information Into Debugging Code

OWASP Top 10: Security Misconfiguration

OWASP Web Security Testing Guide: Testing for Improper Error Handling


### ⬅️ Navigation 

[Back](Readme.md)
