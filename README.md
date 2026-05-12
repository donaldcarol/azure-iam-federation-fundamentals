
# Azure IAM & Federation Fundamentals

A practical hands-on repository focused on modern Identity and Access Management (IAM) concepts in Microsoft Entra ID and cloud environments.

This repository covers:

- Identity & Federation fundamentals
- Authentication vs Authorization
- SAML
- OAuth2
- OpenID Connect (OIDC)
- Enterprise Applications
- App Registrations
- Service Principals
- Managed Identities
- Tokens & Claims
- JWT token analysis
- RBAC integration
- Modern cloud authentication flows
- IAM troubleshooting scenarios

---

# Objectives

The goal of this repository is to build a strong practical and conceptual foundation for modern cloud identity systems used in:

- Microsoft Azure
- Microsoft Entra ID
- Microsoft 365
- SaaS integrations
- Enterprise SSO environments
- Zero Trust architectures
- Cloud-native applications

This repository is designed for:

- Cloud Engineers
- IAM Engineers
- Infrastructure Engineers
- Azure Administrators
- Security Engineers
- DevOps Engineers
- Architects

---

# Core Concepts

## Identity Provider (IdP)

An Identity Provider authenticates users and issues authentication tokens.

Examples:

- Microsoft Entra ID
- Okta
- Ping Identity
- ADFS
- Google Identity

---

## Federation

Federation allows multiple systems to trust a centralized identity provider.

Example:

A user signs into Salesforce using Microsoft Entra ID credentials without Salesforce managing the password directly.

---

## Single Sign-On (SSO)

SSO enables users to authenticate once and access multiple applications securely.

---

## Authentication vs Authorization

### Authentication
Verifies identity.

Examples:
- Password
- MFA
- Certificate
- FIDO2

### Authorization
Determines permissions and access rights.

Examples:
- Access to Azure resources
- Access to SaaS applications
- Administrative privileges

---

# Technologies Covered

| Technology | Purpose |
|---|---|
| SAML | Enterprise federation & SSO |
| OAuth2 | Delegated authorization |
| OpenID Connect | Authentication layer over OAuth2 |
| JWT | Token format |
| RBAC | Resource authorization |
| Managed Identity | Passwordless Azure authentication |

---

# Repository Structure

```text
azure-iam-federation-fundamentals/
│
├── README.md
├── docs/
├── diagrams/
├── labs/
└── notes/
```

---

# Planned Topics
## Documentation
- Identity & Federation Fundamentals
- SAML Authentication Flow
- OAuth2 Authorization Flow
- OpenID Connect Authentication
- Enterprise Apps vs App Registrations
- Service Principals
- Managed Identities
- JWT Tokens & Claims
- RBAC Integration
- IAM Security Best Practices

# Practical Labs
- Configure Enterprise Application SSO
- Create App Registrations
- Configure OAuth permissions
- Decode and analyze JWT tokens
- Create Service Principals
- Assign Azure RBAC permissions
- Configure Managed Identity access to Key Vault
- Troubleshoot authentication flows

 # Authentication Flow Overview

Typical modern authentication flow:

```
User
  ↓
Browser
  ↓
Application
  ↓
Identity Provider (Entra ID)
  ↓
Token Issuance
  ↓
Application validates token
  ↓
Access granted

```

# Learning Goals

After completing this repository, the reader should understand:

- How modern cloud authentication works
- How federation enables SSO
- Differences between SAML, OAuth2 and OIDC
- How tokens and claims work
- Enterprise Applications vs App Registrations
- Service Principal architecture
- Managed Identity authentication
- Common IAM troubleshooting scenarios

  ---

# Real-World Scenarios

This repository includes practical enterprise scenarios such as:
- SaaS integrations
- Azure authentication
- API access
- GitHub OIDC federation
- Key Vault access
- Conditional Access integration
- RBAC authorization
- Zero Trust identity models

--- 

# Related Technologies

- Microsoft Entra ID
- Azure RBAC
- Azure Key Vault
- Azure Managed Identity
- Microsoft Graph
- Conditional Access
- Privileged Identity Management (PIM)
---

# Status

Repository currently under active development.

Planned additions:

- Mermaid diagrams
- Authentication flow visualizations
- Enterprise troubleshooting scenarios
- Hands-on Azure labs
- Token analysis examples
---
  
# Author

Cloud & Infrastructure Engineering learning repository focused on modern IAM architecture and Azure identity technologies.
