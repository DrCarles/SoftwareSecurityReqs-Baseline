### 📌 Requirement
**All active user sessions must be immediately invalidated after a password change**


### 💡 Rationale 
Users often change their password because they suspect that their account has been compromised. If existing sessions stay active after the change, an attacker who already has a session, for example through a stolen session cookie or an unattended device, keeps full access to the account and the password change does not protect the user

Invalidating all active sessions ensures that only someone who knows the new password can access the account


### ⚙️ Specifications 

- 📘 The system must invalidate all of the user's active sessions on the server side after a password change, on all devices and browsers

- 📘 The session where the password was changed must either be invalidated or be given a new session identifier

- 📘 The same applies when the password is reset, whether by the user (e.g. "forgot password") or by an administrator

- 📘 Long-lived credentials linked to the old password, such as "remember me" tokens and refresh tokens, must be revoked

- 📘 The system should notify the user (e.g. by email) that their password was changed and that all sessions were closed


### 🧪 Testing tips 
Suggested test steps for verifying this requirement:
1. Log into the system as the same user from two different browsers or devices (Session A and Session B)
2. Capture the Session Id of Session B
3. Change the user password from Session A
4. Check that Session B is no longer valid and the user must log in again
5. Check that the captured Session Id of Session B can no longer be used
6. Repeat the test using the password reset function instead of the password change
7. Log in with the "remember me" option (or obtain a refresh token), change the password, and check that the token can no longer be used



### 🔗 References 
CWE-613: Insufficient Session Expiration

OWASP Session Management Cheat Sheet



### ⬅️ Navigation 

[Back](Readme.md)
