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

Example:

```xml
<saml:Attribute Name="email">
donald@company.com
</saml:Attribute>
```

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
