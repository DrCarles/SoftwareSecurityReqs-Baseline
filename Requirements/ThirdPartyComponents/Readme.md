## 🔑 Third-Party Components Requirements

This section contains security requirements focused on the safe selection, maintenance and replacement of third-party components, such as libraries, frameworks, packages, container images and runtimes

Most modern applications are built mainly from third-party code. A vulnerability in any of these components is a vulnerability in the application, so they must be chosen and managed with the same care as the application's own code


### 🌩 Common Risks:

Poorly managed third-party components can lead to several serious security issues, including:

1. Exploitation of Known Vulnerabilities: Attackers actively scan for applications using components with publicly known vulnerabilities, for which exploits are often freely available

2. Unpatchable Vulnerabilities: Components that are no longer maintained will not receive security fixes, leaving the application permanently exposed

3. Delayed Patching: Applications that fall far behind the current version of a component face large, risky upgrades, which slows down the response when a critical vulnerability is published

4. Vendor Lock-in: Components that are tightly coupled to the application are hard to replace when they become insecure, unmaintained or unsuitable


### 📌 Requirements:

- [Maintained components](SR-APP-TPC-001.md)
- [Up-to-date components](SR-APP-TPC-002.md)
- [No known vulnerabilities](SR-APP-TPC-003.md)
- [Replaceable components](SR-APP-TPC-004.md)


### ⬅️ Navigation 

[Back](../../README.md)
