### 📌 Requirement
**The application architecture must make it easy to replace third-party components**


### 💡 Rationale 
Sooner or later, a component may need to be replaced because it has a vulnerability that is not fixed, it is no longer maintained, its license changes or it no longer meets the application's needs. When the component is used directly all over the code, replacing it becomes a large, slow and risky project, and the application may stay exposed in the meantime

Isolating components behind clear interfaces limits the code that depends on them, so they can be replaced quickly and safely


### ⚙️ Specifications 

- 📘 Components that provide important functions (e.g. cryptography, authentication, data access, parsing, messaging, payments) should be accessed through interfaces or wrappers owned by the application, instead of being called directly from all over the code

- 📘 Component-specific types, classes and exceptions should not be exposed outside the wrapper that uses them

- 📘 The application should prefer components that implement open standards and protocols (e.g. OpenID Connect, SQL, OpenTelemetry), so that other implementations can be used

- 📘 Configuration specific to a component should be kept in one place and not spread across the application

- 📘 Automated tests must cover the behavior provided by important components, so that a replacement can be checked to behave the same

- 📘 The number of components should be kept to the minimum needed, and unused components must be removed


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Review the architecture and check that important components are accessed through application-owned interfaces
2. Search the code for direct uses of important components outside their wrappers (e.g. imports of the library in many modules)
3. Check that tests exist for the behavior provided by important components
4. Check for unused components in the dependency list (e.g. `depcheck`, `deptry`, `mvn dependency:analyze`)


### 🔗 References 
NIST SP 800-218: Secure Software Development Framework (SSDF)

NIST SP 800-161: Cybersecurity Supply Chain Risk Management Practices


### ⬅️ Navigation 

[Back](Readme.md)
