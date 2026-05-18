# IAM Troubleshooting Scenarios

# Scenario 1

User cannot access Salesforce.

Possible causes:

- Incorrect user assignment
- Expired certificate
- Invalid claims
- SAML configuration issue

---

# Scenario 2

Application login fails.

Possible causes:

- Incorrect redirect URI
- Invalid client secret
- Missing permissions

Common example:

AADSTS7000215

Invalid client secret provided

---

# Scenario 3

API access denied.

Possible causes:

- Missing API permissions
- Missing consent
- RBAC issue

---

# Scenario 4

Managed Identity cannot access Key Vault.

Possible causes:

- Missing RBAC assignment
- Incorrect scope
- Network restrictions

---

# Troubleshooting approach

1. Verify authentication

2. Verify token

3. Verify claims

4. Verify permissions

5. Verify logs

6. Verify application configuration
