### 📌 Requirement
**The application must use the latest stable versions of its third-party components and keep them up to date**


### 💡 Rationale 
New versions of components often include security fixes, sometimes without announcing them as such. Applications that stay close to the latest version get these fixes early and can apply urgent patches quickly with small, low-risk updates

Applications that fall many versions behind face large upgrades with breaking changes, so when a critical vulnerability is published, patching takes weeks instead of hours


### ⚙️ Specifications 

- 📘 New components must be added using their latest stable version

- 📘 Components must be updated regularly (e.g. at least once per release cycle or once per month)

- 📘 Security updates must be applied within defined timeframes according to their severity (e.g. critical within 7 days, high within 30 days)

- 📘 The application should use automated tools that detect new versions and propose updates (e.g. Dependabot, Renovate)

- 📘 Component versions must be pinned (e.g. with lock files) so that builds are reproducible and updates are deliberate and tested

- 📘 Pre-release versions (e.g. alpha, beta, release candidates) must not be used in production

- 📘 Updates must be verified by automated tests before release, so that updating is quick and safe


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Compare the version of each component with its latest stable version (e.g. `npm outdated`, `pip list --outdated`, `mvn versions:display-dependency-updates`)
2. Check that lock files are present and committed to the repository
3. Check that an automated update tool is configured and that its proposals are reviewed and merged regularly
4. Check the time taken to apply recent security updates against the defined timeframes


### 🔗 References 
OWASP Top 10: Vulnerable and Outdated Components

OWASP Vulnerable Dependency Management Cheat Sheet

NIST SP 800-218: Secure Software Development Framework (SSDF)


### ⬅️ Navigation 

[Back](Readme.md)
