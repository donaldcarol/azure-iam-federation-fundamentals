# Tokens, Claims and JWT

# Token

A token represents authentication or authorization information.

---

# Common Token Types

| Token | Purpose |
|---|---|
| ID Token | User identity |
| Access Token | Access resources |
| Refresh Token | Renew access |

---

# Claims

Claims contain identity attributes.

Examples:

- Name
- Email
- Groups
- Roles
- Department

Example:

```json
{
"name":"Donald",
"email":"donald@company.com",
"role":"Admin"
}
```

---

# JWT Structure

JWT consists of:

Header

Payload

Signature

Format:

```text
xxxxx.yyyyy.zzzzz
```

---

# Validation

Applications validate:

- Signature
- Expiration
- Audience
- Issuer
