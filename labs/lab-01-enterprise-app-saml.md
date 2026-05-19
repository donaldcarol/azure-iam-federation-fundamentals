# Lab 01 - Configure Enterprise Application SSO (SAML)

# Objective

Configure Single Sign-On between Microsoft Entra ID and a SaaS application using SAML.

---

# Scenario

Company:

Contoso

Requirements:

- Centralized authentication
- MFA enforcement
- SSO access
- No application-specific passwords

Application:

Salesforce

Identity Provider:

Microsoft Entra ID

---

# Architecture

```text
User  
↓  
Browser  
↓  
Salesforce  
↓   
Microsoft Entra ID    
↓  
SAML Assertion  
↓  
Salesforce  
↓  
Access granted  
```

---

# Step 1

Open:  
Entra Admin Center  
↓  
Enterprise Applications  
↓  
New Application  

---

# Step 2

Search:  
Salesforce  
↓  
Create application  

---

# Step 3

Open:  
Single Sign-On
↓  
Select:  
SAML  

---

# Step 4

Configure:

Identifier (Entity ID)

Reply URL

Sign-on URL

---

# Step 5

Configure claims

Default:

- name
- email
- userprincipalname

Optional:

- department
- groups
- jobTitle

---

# Step 6

Assign users

Users and Groups

↓

Add User

---

# Step 7

Test login

Open:

Test SSO

---

# Validation

Verify:

- Successful login
- Claims received
- User assignment
- MFA prompt

---

# Troubleshooting

Possible issues:

- Invalid Reply URL
- Expired certificate
- Missing user assignment
- Incorrect claims mapping
