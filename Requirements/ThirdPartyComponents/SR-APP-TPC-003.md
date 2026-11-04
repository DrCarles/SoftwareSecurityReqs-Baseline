### 📌 Requirement
**The application must not use third-party components with known vulnerabilities**


### 💡 Rationale 
Once a vulnerability is published, attackers can use the public details, and often public exploits, to attack any application that uses the affected component. These attacks are cheap and often automated, which makes known vulnerabilities one of the most common causes of breaches

Checking components for known vulnerabilities continuously, and not only when the application is built, makes sure new vulnerabilities in existing components are found and fixed in time


### ⚙️ Specifications 

- 📘 All components, including transitive dependencies, must be checked against vulnerability databases (e.g. NVD, GitHub Advisory Database, OSV) using a Software Composition Analysis (SCA) tool

- 📘 The check must run automatically in the build pipeline, and builds must fail when components with critical or high severity vulnerabilities are found

- 📘 Applications already in production must be checked continuously, so that newly published vulnerabilities in existing components are detected

- 📘 Vulnerabilities must be fixed within defined timeframes according to their severity, giving priority to those known to be exploited (e.g. listed in the CISA Known Exploited Vulnerabilities catalog)

- 📘 When a vulnerability does not affect the application (e.g. the vulnerable function is never used), this must be analyzed, documented and approved, for example with a VEX statement

- 📘 The application should maintain a Software Bill of Materials (SBOM) so that affected applications can be found quickly when a new vulnerability is published


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Run an SCA tool against the application (e.g. OWASP Dependency-Check, Trivy, Grype, `npm audit`, `pip-audit`) and check that no critical or high vulnerabilities are reported
2. Check that the build pipeline fails when a component with a known critical vulnerability is added
3. Check that production applications are scanned regularly and that alerts reach the responsible team
4. Check that every accepted vulnerability has a documented and approved analysis


### 🔗 References 
CWE-1395: Dependency on Vulnerable Third-Party Component

OWASP Top 10: Vulnerable and Outdated Components

OWASP Dependency-Check

CISA Known Exploited Vulnerabilities Catalog


### ⬅️ Navigation 

[Back](Readme.md)
