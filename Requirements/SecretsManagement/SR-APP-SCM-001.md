### 📌 Requirement
**The application must not hard-code passwords, API keys, tokens, private keys or any other credentials in its source code, and must load them at runtime from a secure secret storage mechanism**


### 💡 Rationale 
Source code spreads much further than expected: repositories, developer laptops, build systems, backups, container images, vendors, and sometimes public sites by mistake. Anyone who can read the code gets every secret in it, and automated bots scan public repositories and find leaked keys within minutes

Hard-coded secrets also stay in version control history after they are removed, cannot be rotated without a new release, and are often the same in every environment or customer installation, so a single leak compromises all of them


### ⚙️ Specifications 

- 📘 Credentials (e.g. passwords, API keys, tokens, private keys, signing keys, connection strings containing credentials) must not be stored in source code, configuration files under version control, build artifacts or container images

- 📘 Credentials must not be embedded in client-side code (e.g. mobile apps, JavaScript bundles, desktop clients), since anything shipped to users can be extracted

- 📘 Secrets must be loaded at runtime through the project's established secure secret storage (e.g. a secret manager such as HashiCorp Vault, AWS Secrets Manager or Azure Key Vault, or environment variables injected by the deployment platform)

- 📘 Production environments should use a dedicated secret manager that provides access control, encryption and audit logs

- 📘 `.env` files may be used only for local development. They must be excluded from version control (e.g. in `.gitignore`), and a template with placeholder values (e.g. `.env.example`) should be provided instead

- 📘 Each environment must use its own secrets, and production secrets must not be used in development or test

- 📘 Secrets must not be written to logs, error messages or debugging output

- 📘 Automated secret scanning must run before code is merged (e.g. pre-commit hooks or the CI pipeline) and block changes that contain secrets

- 📘 A secret that has been committed must be treated as compromised, and must be revoked and replaced immediately. Removing it from the code or the history is not enough

- 📘 The application should allow secrets to be rotated without code changes


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Run a secret scanner over the whole repository, including its history (e.g. gitleaks, TruffleHog)
2. Search the code for common secret patterns (e.g. `password=`, `api_key`, `BEGIN PRIVATE KEY`, connection strings)
3. Inspect build artifacts, container image layers, JavaScript bundles and mobile app packages for secrets
4. Check that `.env` files are excluded from version control and do not appear in the repository history
5. Try to commit a test secret and check that the pre-commit hook or pipeline blocks it
6. Check that production secrets differ from those of other environments, and that a secret can be rotated without changing the code


### 🔗 References 
CWE-798: Use of Hard-coded Credentials

CWE-259: Use of Hard-coded Password

CWE-321: Use of Hard-coded Cryptographic Key

CWE-540: Inclusion of Sensitive Information in Source Code

OWASP Secrets Management Cheat Sheet


### ⬅️ Navigation 

[Back](Readme.md)
