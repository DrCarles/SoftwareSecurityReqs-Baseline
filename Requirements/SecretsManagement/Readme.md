## 🔑 Secrets Management Requirements

This section contains security requirements focused on protecting the secrets the application uses, such as passwords, API keys, tokens, certificates and cryptographic keys

Secrets give direct access to databases, third-party services and other systems. A single leaked secret can bypass every other security control, so secrets must be kept out of the code and handled through mechanisms designed to protect them


### 🌩 Common Risks:

Poorly managed secrets can lead to several serious security issues, including:

1. Credential Leakage: Secrets stored in source code, configuration files or build artifacts are exposed to anyone who can read them, including through public repositories, backups or shared container images

2. Unauthorized Access: Attackers who obtain a secret can access databases, cloud resources and third-party services with the application's privileges, often without being detected

3. Wide Impact: Secrets shared across environments or customer installations allow a single leak to compromise all of them

4. Slow Recovery: Secrets that are hard-coded or spread across many places are difficult to rotate, leaving systems exposed for longer after a leak


### 📌 Requirements:

- [No hard-coded secrets](SR-APP-SCM-001.md)


### ⬅️ Navigation 

[Back](../../README.md)
