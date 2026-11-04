### 📌 Requirement
**The application must not use third-party components that are no longer maintained**


### 💡 Rationale 
When a component is no longer maintained (end-of-life, deprecated or abandoned), nobody will fix newly found vulnerabilities in it. Any vulnerability discovered in the future will stay open for as long as the application uses the component, and the only fix will be an unplanned and urgent replacement

Checking the maintenance status of a component before adopting it, and keeping track of it during the life of the application, avoids building on code that cannot be patched


### ⚙️ Specifications 

- 📘 The application must not include components that have reached end-of-life or are officially deprecated by their maintainers

- 📘 This applies to all component types, including libraries, frameworks, runtimes (e.g. language versions), operating system base images and database engines

- 📘 Before adopting a new component, its maintenance status must be checked, for example: recent releases, response to reported issues, number of active maintainers, published end-of-life dates and a security policy for reporting vulnerabilities

- 📘 Components with no release or maintainer activity for a long period (e.g. more than 12 months) should be considered abandoned and reviewed

- 📘 Components with a published end-of-life date must have a plan to upgrade or replace them before that date

- 📘 When an unmaintained component cannot be replaced immediately, the exception must be documented, approved, and covered by compensating controls with a deadline for replacement


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Generate the list of all components used by the application, including transitive dependencies (e.g. with a Software Bill of Materials)
2. Check the end-of-life status of runtimes, frameworks and base images (e.g. on endoflife.date or the vendor's lifecycle page)
3. Check the last release date and repository activity of each component, or use tools that report it (e.g. OpenSSF Scorecard)
4. Check that any unmaintained component has a documented and approved exception with a replacement date


### 🔗 References 
CWE-1104: Use of Unmaintained Third Party Components

OWASP Top 10: Vulnerable and Outdated Components

OpenSSF Scorecard


### ⬅️ Navigation 

[Back](Readme.md)
