# Lab 05 - Managed Identity and Key Vault

# Objective

Allow Azure VM access to Key Vault without secrets.

---

# Architecture

```text
Azure VM

↓

Managed Identity

↓

Token request

↓

Key Vault

↓

Secret retrieval
```

---

# Step 1

Open:

Virtual Machine

↓

Identity

↓

Enable:

System Assigned Managed Identity

---

# Step 2

Open:

Key Vault

↓

Access Control (IAM)

↓

Add Role Assignment

Role:

Key Vault Secrets User

Principal:

VM Managed Identity

---

# Step 3

Connect to VM

Run:

```powershell
Connect-AzAccount -Identity
```

---

# Retrieve secret

```powershell
Get-AzKeyVaultSecret `
-VaultName "LabKeyVault"
```

---

# Validation

Verify:

- Authentication successful
- Secret retrieved
- No passwords used
