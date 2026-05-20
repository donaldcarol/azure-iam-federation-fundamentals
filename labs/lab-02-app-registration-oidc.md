# Lab 02 - Create App Registration for OIDC Authentication

# Objective

Create a local web application that authenticates users using Microsoft Entra ID and OpenID Connect.

---

# Scenario

Application:

Local Node.js web application

Authentication:

Microsoft Entra ID

Protocol:

OIDC

Local URL:

http://localhost:3000

---

# Prerequisites

Install:

- Node.js
- Visual Studio Code
- npm packages:

```bash
npm install express express-session @azure/msal-node dotenv
```

---

# Step 1

Create project folder:

```bash
mkdir MyOIDCLab
cd MyOIDCLab
```

Initialize:

```bash
npm init -y
```

---

# Step 2

Create App Registration

Open:

Entra Admin Center

↓

App Registrations

↓

New Registration

Configure:

Name:

MyOIDCApp

Supported account types:

Single tenant

Redirect URI:

```text
Web

http://localhost:3000/auth/redirect
```

---

# Step 3

Save generated values:

- Application (Client) ID
- Directory (Tenant) ID

---

# Step 4

Certificates & Secrets

↓

New Client Secret

Save:

```text
Secret Value
```

Important:

Do NOT save Secret ID

Save Secret Value

---

# Step 5

API Permissions

Add:

- openid
- profile
- email

---

# Step 6

Create .env

```text
CLIENT_ID=xxxxxxxx
TENANT_ID=xxxxxxxx
CLIENT_SECRET=xxxxxxxx
REDIRECT_URI=http://localhost:3000/auth/redirect
```

---

# Step 7

Start local application

```bash
node server.js
```

---

# Expected Flow

```text
User

↓

Local Application

↓

Entra ID

↓

Authentication

↓

ID Token

↓

Local Application

↓

Authenticated session created
```

---

# Validation

Verify:

- Browser redirects to Entra
- Login page appears
- MFA works
- ID token returned
- User session created

---

# Troubleshooting

Common issues:

AADSTS50011

Reply URL mismatch

AADSTS7000215

Invalid client secret

AADSTS9002326

Cross-origin issue
