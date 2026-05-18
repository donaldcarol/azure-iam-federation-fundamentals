# Service Principals and Managed Identities

# Service Principal

A Service Principal is an identity used by applications and services.

Purpose:

- Authenticate applications
- Access Azure resources
- Apply permissions

Example:

GitHub workflow accesses Azure resources.

---

# Service Principal components

- Client ID
- Tenant ID
- Secret or certificate

---

# Managed Identity

Managed Identity is an Azure-managed Service Principal.

Azure automatically:

- Creates identity
- Rotates credentials
- Manages lifecycle

---

# Benefits

- No secrets
- No password rotation
- Improved security

---

# Example

```
Azure VM
↓
Managed Identity
↓
Token requested
↓
Key Vault
↓
Access granted
```
