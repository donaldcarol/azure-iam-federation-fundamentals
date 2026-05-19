# Enterprise Applications vs App Registrations

Many people confuse these concepts.

---

# App Registration

An App Registration defines an application.

Contains:

- Client ID
- Redirect URI
- API permissions
- Certificates
- Secrets

Think of App Registration as:

> Application blueprint

---

# Enterprise Application

Enterprise Application is the application instance inside your tenant.

Contains:

- User assignments
- SSO settings
- Claims
- Permissions
- Provisioning

Think of Enterprise App as:

> Operational instance

---

# Relationship

```text
App Registration  
↓
Service Principal created  
↓
Enterprise Application appears  
```

# When to use Enterprise Applications vs App Registrations

One of the most common areas of confusion in Microsoft Entra ID is understanding when to create an Enterprise Application and when to create an App Registration.

---

# Decision Table

| Scenario | Enterprise Applications → New Application | App Registrations → New Registration |
|---|---:|---:|
| Integrate Salesforce with Entra ID | ✅ | ❌ |
| Integrate ServiceNow | ✅ | ❌ |
| Integrate AWS | ✅ | ❌ |
| Integrate Zoom | ✅ | ❌ |
| Internal Node.js application | ❌ | ✅ |
| Company ASP.NET application | ❌ | ✅ |
| Internal API | ❌ | ✅ |
| React application developed internally | ❌ | ✅ |
| Application using Microsoft Graph API | ❌ | ✅ |
| GitHub OIDC integration with Azure | ❌ | ✅ |
| Application using client secrets or certificates | ❌ | ✅ |
| Configure SAML SSO for existing SaaS application | ✅ | ❌ |
| User assignment and SSO for existing application | ✅ | ❌ |

---

# What Each Option Creates

| Action | Result |
|---|---|
| Enterprise Applications → New Application | Service Principal (local instance in tenant) |
| App Registrations → New Registration | App Registration + Service Principal + Enterprise Application |

---

# Simple Decision Rule

```text
Does the application already exist?  
        ↓  
      YES  
        ↓  
Create Enterprise Application


Does the application need to be created by you?  
        ↓  
      YES  
        ↓  
Create App Registration  
```

---

# Real-world Examples

## Example 1  
Scenario:

```text
Entra ID → Salesforce → SAML SSO
```

Configuration:

```text
Enterprise Applications  
↓  
New Application  
↓  
Salesforce  
```

Result:

```text
Enterprise Application
(Service Principal)
```

---

## Example 2

Scenario:

```text
Node.js application  
↓  
Login with Microsoft  
↓  
Call Microsoft Graph API  
```

Configuration:

```text
App Registrations
↓
New Registration
```

Result:

```text
App Registration  
↓  
Service Principal  
↓  
Enterprise Application  
```

---

## Example 3

Scenario:

```text
GitHub Actions  
↓  
OIDC Federation  
↓  
Azure  
```

Configuration:

```text
App Registrations  
↓  
New Registration  
↓  
Federated Credentials  
```

Reason:

GitHub requires:

- Client ID
- Tenant ID
- Token trust relationship  
 ---

# Key Takeaway

In most cases:

```text
Existing SaaS application  
↓  
Enterprise Application  


Application developed by your organization  
↓  
App Registration  
```

---

# Example

Create:

MyWebApplication

App Registration created:

- Client ID generated

Automatically:

Enterprise Application created

Now administrators configure:

- SSO
- users
- groups
- access policies
