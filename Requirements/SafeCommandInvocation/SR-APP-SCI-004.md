### 📌 Requirement
**The application must configure all XML parsers to disable external entities and DTD processing**


### 💡 Rationale 
Many XML parsers resolve external entities by default. An attacker who can send XML (including files such as DOCX, XLSX, SVG or SAML messages) can define entities that make the server read local files, connect to internal systems (server-side request forgery), or expand recursively until the server runs out of memory ("billion laughs" attack)

Disabling DTDs and external entities removes these features, which most applications do not need


### ⚙️ Specifications 

- 📘 All XML parsers must be configured to disallow DTDs (DOCTYPE declarations) completely, when the application does not need them

- 📘 When DTDs cannot be disabled, external general entities, external parameter entities and loading of external DTDs must be disabled

- 📘 XInclude processing must be disabled unless it is required

- 📘 Entity expansion must be limited to prevent denial of service

- 📘 The secure configuration must also apply to parsers used indirectly, such as XSLT processors, SOAP and SAML libraries, and document or image libraries that process XML-based formats

- 📘 The application should use a simpler format such as JSON when XML is not required


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Find every place where the application parses XML, including file uploads (DOCX, XLSX, SVG), SOAP, SAML and RSS
2. Send XML with an external entity that reads a local file (e.g. `<!ENTITY xxe SYSTEM "file:///etc/passwd">`) and check that its content is not returned
3. Send an external entity pointing to a server you control and check that no request is received
4. Send a document with nested entity expansion and check that the application rejects it without high CPU or memory use
5. Review the parser configuration in the code


### 🔗 References 
CWE-611: Improper Restriction of XML External Entity Reference

CWE-776: Improper Restriction of Recursive Entity References in DTDs

OWASP XML External Entity Prevention Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
