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
