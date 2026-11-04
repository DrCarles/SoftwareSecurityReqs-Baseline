### 📌 Requirement
**The application must restrict access to communication endpoints, exposing them only through authorized interfaces**


### 💡 Rationale 

Limiting the exposure of communication endpoints helps reduce the system’s attack surface by ensuring that only intended users and components can interact with the application. Unnecessary or publicly exposed endpoints, such as debug interfaces, can become entry points for attackers


### ⚙️ Specifications 

_No specifications have been defined for this requirement_


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Scan the application hosts for open ports and services (e.g. with nmap) and compare the results with the list of documented interfaces
2. Check that debug, administration and management endpoints are not reachable from untrusted networks
3. Discover web paths and API endpoints (e.g. with content discovery tools or the API documentation) and check that no undocumented endpoints are exposed
4. Review firewall and network policies and check that access is restricted to authorized sources



### 🔗 References 
CWE-1125: Excessive Attack Surface

NIST SP 800-53 Rev. 5: CM-7 Least Functionality

OWASP Attack Surface Analysis Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
