# Identity & Federation Fundamentals

## Overview

Modern cloud environments rely heavily on Identity and Access Management (IAM). Instead of each application managing users and passwords independently, organizations centralize authentication and authorization through trusted identity systems.

Modern IAM provides:

- Centralized authentication
- Single Sign-On (SSO)
- Multi-Factor Authentication (MFA)
- Federation between systems
- Access control
- Auditing and security policies

---

# Core Definitions

## Identity

An identity represents a user, application, service, or device that can be authenticated.

Examples:

- User account
- Service account
- Application
- Virtual Machine
- Managed Identity

Examples in Azure:

- User: donald@company.com
- Application: WebApp01
- Managed Identity: VM-Identity
- Service Principal: GitHubActions-SP

---

## Authentication

Authentication answers:

> "Who are you?"

Authentication validates identity using one or more factors.

Examples:

- Username/password
- MFA
- Certificate
- Smart card
- FIDO2 key
- Biometric authentication

Example:

```text
Donald enters username and password.

Entra ID validates credentials.

Authentication successful.
```

---

## Authorization

Authorization answers:

> "What are you allowed to do?"

Authorization determines permissions after authentication.

Examples:

| Identity | Permissions |
|---|---|
| User | Read mailbox |
| Helpdesk Admin | Reset passwords |
| VM Managed Identity | Access Key Vault |
| Application | Read Microsoft Graph |

---

# How Authentication and Authorization Work Together

Modern cloud applications usually involve multiple components working together.

Authentication and authorization are related but different processes.

Authentication answers:

> Who are you?

Authorization answers:

> What are you allowed to access?

---

# Example: Teams Login Flow

When a user opens Microsoft Teams:

```text
User  
↓  
Teams Client  
↓  
Microsoft Entra ID  
↓  
Authentication  
↓  
ID Token issued  
↓  
Access Token issued  
↓  
token=ID + Acces token  
↓  
Teams receives token  
↓  
Teams calls Microsoft Graph API    
↓  
Graph validates token / Authorization    
↓  
Returns data  
↓  
Teams displays information
```
---

# What Happens During the Flow

### Step 1 — Authentication

Teams needs to identify the user.

Entra ID validates:

- Username
- Password
- MFA
- Conditional Access policies

OIDC is commonly used here.

Result:

```text
ID Token issued
```

Example:

```json
{
"name":"Donald",
"email":"donald@company.com"
}
```
---

### Step 2 — Access to Resources

Teams needs access to:

- Mailbox
- Calendar
- Chat
- Files

OAuth2 is commonly used here.

Result:

```text
Access Token issued
```

Example:

```json
{
"scp":"Mail.Read Chat.Read User.Read"
}
```

---

### Step 3 — Authorization

Applications or APIs verify:

- Is the token valid?
- Is the token expired?
- Does the user have permissions?

Examples:

- Mail.Read
- Chat.Read
- Files.Read

If validation succeeds:

```text
Access granted
```

---

# Component Responsibilities

| Component | Responsibility |
|---|---|
| Entra ID | Authenticates users |
| OIDC | User authentication flow |
| OAuth2 | Delegated authorization |
| ID Token | Identifies user |
| Access Token | Provides resource access |
| Application/API | Performs authorization |

---

# Key Takeaway

Authentication:

```text
Who are you?
```

Authorization:

```text
What can you access?
```

Modern applications often use:

```text
OIDC
    ↓
Authentication

OAuth2
    ↓
Authorization

JWT
    ↓
Token transport
```


# Identity Provider (IdP)

An Identity Provider authenticates users and issues tokens.

Typical responsibilities:

- User authentication
- MFA processing
- Token issuance
- Password policies
- Conditional Access
- SSO

Examples:

- Microsoft Entra ID
- Okta
- ADFS
- Ping Identity

---

# Service Provider (SP)

A Service Provider consumes identity information and provides services.

Examples:

| Service Provider |
|---|
| Salesforce |
| ServiceNow |
| AWS |
| Dropbox |
| Internal applications |

The Service Provider trusts the Identity Provider.

---

# Federation

Federation is a trust relationship between systems.

Instead of storing user passwords in multiple applications:

```text
Application trusts Identity Provider
```

Example:

Without federation:

```text
User  
  ↓  
Salesforce  
  ↓  
Separate password
```

With federation:

```text
User  
  ↓  
Salesforce  
  ↓  
Redirect  
  ↓  
Entra ID  
  ↓  
Authentication  
  ↓  
Token returned  
  ↓  
Access granted  
```

---

# Single Sign-On (SSO)

SSO allows users to authenticate once and access multiple applications.

Benefits:

- Fewer passwords
- Better user experience
- Improved security
- Centralized access control

Example:

```text
User logs into Windows
↓
Teams
↓
Outlook
↓
SharePoint
↓
Salesforce

(No additional login)
```

---

# Authentication vs Authorization

Authentication:

```text
Who are you?
```

Authorization:

```text
What can you do?
```

Example:

```text
Donald logs into Azure Portal
        ↓
Authentication successful
        ↓
Azure checks RBAC role
        ↓
Contributor role found
        ↓
Authorization granted
```

---

# Modern IAM Components

Typical architecture:

```text
User  
↓  
Application  
↓  
Identity Provider  
↓  
Token Service  
↓  
Application validates token  
↓  
Access to resources  
```

---

# Cloud Identity Examples

Example 1:

User → Microsoft 365

Authentication:
- Entra ID

Authorization:
- Microsoft 365 roles

---

Example 2:

Azure VM → Key Vault

Authentication:
- Managed Identity

Authorization:
- Azure RBAC

---

Example 3:

GitHub Actions → Azure

Authentication:
- OIDC Federation

Authorization:
- Service Principal permissions

---

# Key Takeaways

Modern IAM is based on several core concepts:

- Identity
- Authentication
- Authorization
- Federation
- SSO
- Tokens
- Trust relationships

Understanding these fundamentals makes SAML, OAuth2 and OIDC much easier to understand.
