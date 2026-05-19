# Lab 02 - Create App Registration for OIDC Authentication

# Objective

Create an application using OpenID Connect authentication.

---

# Scenario

Application:

Internal Web Application

Authentication:

Microsoft Entra ID

Protocol:

OIDC

---

# Step 1

Open:

Entra Admin Center

↓

App Registrations

↓

New Registration

---

# Step 2

Configure:

Name:

MyOIDCApp

Supported account types:

Single tenant

Redirect URI:

http://localhost:3000/auth/redirect

---

# Step 3

After creation note:

- Application ID
- Tenant ID

---

# Step 4

Certificates & Secrets

↓

New Client Secret

Save secret value

---

# Step 5

API Permissions

Add:

- OpenID
- profile
- email

---

# Step 6

Authentication

Enable:

ID Tokens

---

# Validation

Verify login flow:

```text
User  
 ↓  
Application  
↓    
Entra ID  
↓  
ID Token returned  
↓  
Application validates token  
```
