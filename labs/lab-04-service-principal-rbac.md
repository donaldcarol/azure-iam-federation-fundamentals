# Lab 04 - Service Principal and RBAC

# Objective

Create a Service Principal and assign permissions.

---

# Create Service Principal

PowerShell:

```powershell
Connect-AzAccount

New-AzADServicePrincipal -DisplayName "Lab-SP"
```

---

# Assign role

```powershell
New-AzRoleAssignment `
-ApplicationId <ApplicationID> `
-RoleDefinitionName Reader `
-Scope "/subscriptions/SubscriptionID"
```

---

# Validation

Verify:

IAM

↓

Role assignments

↓

Reader

↓

Lab-SP

---

# Test access

Authenticate:

```powershell
Connect-AzAccount -ServicePrincipal
```
