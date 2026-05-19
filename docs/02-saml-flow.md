# SAML Authentication Flow

## Overview

SAML (Security Assertion Markup Language) is an XML-based standard used for authentication and Single Sign-On (SSO) between an Identity Provider (IdP) and a Service Provider (SP).

SAML is commonly used in enterprise environments for integrating cloud and SaaS applications.

Examples:

- Microsoft Entra ID → Salesforce
- Entra ID → ServiceNow
- Entra ID → AWS
- Entra ID → Internal applications

---

# Main Components

| Component | Role |
|---|---|
| User | Requests access |
| Browser | Transfers authentication messages |
| Identity Provider (IdP) | Authenticates users |
| Service Provider (SP) | Provides application access |

---

# SAML Authentication Flow

```text
1. User opens Salesforce

2. Salesforce checks session

3. User not authenticated

4. Browser redirected to Entra ID

5. User enters credentials

6. MFA performed if required

7. Entra creates SAML Assertion

8. Browser sends assertion to Salesforce

9. Salesforce validates assertion

10. Access granted
```

---

# SAML Assertion

A SAML assertion contains identity information.

Typical data:

- Name
- Email
- Username
- Department
- Groups
- Roles

---

# Is SAML Assertion a Token?

SAML Assertions function similarly to tokens because they transport identity information between trusted systems.

However, SAML Assertions and JWT tokens are not identical technologies.

---

# Comparison

| Feature | SAML Assertion | JWT Token |
|---|---:|---:|
| Purpose | Transport identity information | Transport identity and access information |
| Format | XML | JSON |
| Appearance | XML document | xxxxx.yyyyy.zzzzz |
| Commonly used by | SAML | OAuth2 / OIDC |
| Contains claims | ✅ | ✅ |
| Digitally signed | ✅ | ✅ |
| Can be encrypted | ✅ | ✅ |
| Browser redirect dependent | Usually | Less dependent |

---

# SAML Assertion Example

```xml
<saml:Assertion>

<saml:Subject>
donald@company.com
</saml:Subject>

<saml:Attribute Name="email">
donald@company.com
</saml:Attribute>

<saml:Attribute Name="role">
Admin
</saml:Attribute>

</saml:Assertion>
```

---

# JWT Example

```json
{
"name":"Donald",
"email":"donald@company.com",
"role":"Admin"
}
```
JWT encoded:

```text
xxxxx.yyyyy.zzzzz
```

---

# Conceptual Comparison

SAML authentication:

```text
User  
↓  
Entra ID  
↓  
SAML Assertion  
↓  
Salesforce  
```

OIDC authentication:

```text
User  
↓  
Entra ID  
↓  
JWT Token  
↓  
Application  
```

---

# Key Takeaway

SAML Assertions and JWT tokens serve similar purposes:

- carry identity information
- contain claims
- are digitally signed
- establish trust between systems

The primary difference is the format:

- SAML → XML
- OIDC/OAuth2 → JSON
---

# Advantages

- Mature enterprise protocol
- Strong SSO support
- Widely adopted
- Centralized authentication

---

# Limitations

- XML based
- Larger payloads
- Browser redirect dependent
- More complex than OIDC

---

# Real-world Example

Company:

Contoso uses:

- Microsoft Entra ID
- Salesforce

Users authenticate once through Entra ID and access Salesforce without separate passwords.
