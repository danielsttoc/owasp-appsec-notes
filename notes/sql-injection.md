# SQL Injection

## Overview

SQL injection occurs when untrusted user input is inserted directly into SQL queries without proper validation or parameterisation.

Attackers may be able to:

- Read sensitive data
- Modify database records
- Bypass authentication
- Delete information
- Execute administrative database actions

## Example Vulnerable Query

```sql
SELECT * FROM users WHERE username = '$username' AND password = '$password';
```

## Example Payload

```sql
' OR '1'='1
```

This can cause the query to always evaluate as true and potentially bypass login systems.

## Common Causes

- Unsafe string concatenation
- Lack of parameterised queries
- Poor input validation
- Excessive database permissions

## Prevention

- Use prepared statements
- Use parameterised queries
- Apply least privilege to database accounts
- Validate and sanitise user input
- Avoid exposing database errors to users

## What I Learned

Through SecureFlag labs and OWASP practice, I learned how small input handling mistakes can lead to major security issues and why secure query handling is critical in modern web applications.
