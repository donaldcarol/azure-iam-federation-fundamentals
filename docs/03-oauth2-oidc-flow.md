# OAuth2 and OpenID Connect (OIDC)

# OAuth2 Overview

OAuth2 is an authorization framework.

OAuth2 answers:

> "Can application X access resource Y?"

OAuth2 itself does NOT authenticate users.

---

# Main Components

| Component | Role |
|---|---|
| Resource Owner | User |
| Client | Application |
| Authorization Server | Entra ID |
| Resource Server | API |

---

# OAuth2 Flow

```text
User

↓

Application

↓

Authorization Server

↓

Access Token issued

↓

API

↓

Access granted
```

---

# OpenID Connect (OIDC)

OIDC adds authentication on top of OAuth2.

OIDC answers:

> "Who is the user?"

---

# OIDC Tokens

| Token | Purpose |
|---|---|
| ID Token | User identity |
| Access Token | Resource access |
| Refresh Token | Obtain new tokens |

---

# Typical OIDC Flow

```text
User

↓

Application

↓

Redirect to Entra ID

↓

Authentication

↓

ID Token + Access Token

↓

Application validates token

↓

Access granted
```

---

# Why OIDC became popular

- JSON based
- JWT support
- REST APIs
- Mobile friendly
- Easier integration
