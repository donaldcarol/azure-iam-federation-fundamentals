# Lab 03 - Decode JWT Token

# Objective

Understand JWT token structure.

---

# Obtain token

Methods:

- Browser Developer Tools
- Postman
- Application login
- Microsoft Graph

---

# Token format

```text
xxxxx.yyyyy.zzzzz
```

---

# Parts

Header

Payload

Signature

---

# Examine payload

Example:

```json
{
"name":"Donald",
"preferred_username":"donald@contoso.com",
"roles":["Admin"],
"aud":"Microsoft Graph"
}
```

---

# Verify

Check:

- exp
- aud
- iss
- roles
- groups

---

# Questions

Who issued the token?

Who consumes the token?

Which claims exist?

When does token expire?
