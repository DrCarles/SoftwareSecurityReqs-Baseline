### 📌 Requirement
**The application must not deserialize untrusted data using formats or libraries that can create arbitrary objects**


### 💡 Rationale 
Native serialization formats (e.g. Java serialization, .NET `BinaryFormatter`, Python `pickle`, PHP `unserialize`, YAML with object tags) can create any object available to the application while reading the data. Attackers can chain existing classes ("gadgets") to run code, often leading to remote code execution without any bug in the application's own code

Using data-only formats such as JSON, and limiting which types can be created, removes this risk


### ⚙️ Specifications 

- 📘 Untrusted data must be exchanged in data-only formats (e.g. JSON, Protocol Buffers) instead of native object serialization

- 📘 Unsafe deserialization functions (e.g. Java `ObjectInputStream`, .NET `BinaryFormatter`, Python `pickle`, PHP `unserialize`) must not be used with untrusted data

- 📘 YAML must be parsed with safe loaders that only create basic data types (e.g. `yaml.safe_load` in Python)

- 📘 JSON and XML libraries must have polymorphic type handling disabled, or limited to an allowlist of expected types (e.g. Jackson default typing, Json.NET `TypeNameHandling`)

- 📘 When native deserialization cannot be avoided, the data must be signed and its integrity verified before deserializing, and the classes allowed must be limited to an allowlist (e.g. Java serialization filters)


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Find places where the application receives serialized data, such as cookies, hidden fields, API bodies, message queues and cache entries
2. Look for known serialization signatures (e.g. `rO0` or `AC ED` for Java, `AAEAAAD` for .NET, `O:` for PHP)
3. Review the code and dependency configuration for unsafe deserialization functions and polymorphic typing
4. Use tools such as ysoserial in a test environment to check whether gadget chains are accepted


### 🔗 References 
CWE-502: Deserialization of Untrusted Data

OWASP Deserialization Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
