# Common Web Vulnerabilities — Learning

Web applications may contain vulnerabilities caused by:

- Insecure application logic
- Improper input validation
- Weak authentication
- Weak authorization
- Misconfigurations
- Unsafe file handling

Many common web vulnerabilities are covered by the `OWASP Top 10`.

---

## Broken Authentication

`Broken Authentication` occurs when authentication mechanisms can be bypassed or abused.

Possible impact includes:

- Login without valid credentials
- Session compromise
- Account takeover
- Privilege escalation

Example:

```text
' or 0=0 #
```

If vulnerable authentication logic uses this input inside an SQL query, it may cause the condition to always evaluate as true.

---

## Broken Access Control

`Broken Access Control` occurs when users can access resources or functionality outside their intended permissions.

Example:

```text
Normal User
    ↓
Access Admin Panel
```

Possible impact includes:

- Unauthorized access
- Access to other users' data
- Privilege escalation
- Administrative functionality abuse

---

## Malicious File Upload

A malicious file upload vulnerability occurs when an application does not properly validate uploaded files.

An attacker may attempt to upload executable server-side code.

Example:

```text
shell.php
```

Weak file extension checks may sometimes be bypassed using techniques such as:

```text
shell.php.jpg
```

Possible impact includes:

- Arbitrary file upload
- Remote Code Execution
- Server compromise

---

## Command Injection

`Command Injection` occurs when user-controlled input is inserted into an operating system command without proper validation or sanitization.

Example vulnerable concept:

```text
ping <USER_INPUT>
```

If shell metacharacters are accepted, additional commands may be executed.

Example:

```text
127.0.0.1 | COMMAND
```

Possible impact includes:

- Execute OS commands
- Read sensitive files
- Modify server data
- Remote Code Execution
- Full backend compromise

---

## SQL Injection (SQLi)

`SQL Injection` occurs when user-controlled input is inserted directly into SQL queries without safe handling.

Example vulnerable PHP code:

```php
$query = "select * from users where name like '%$searchInput%'";
```

If `$searchInput` is not properly handled, an attacker may manipulate the SQL query.

Possible impact includes:

- Authentication bypass
- Read database data
- Modify database data
- Delete data
- Extract credentials
- Potential server compromise

---

## Summary

```text
Broken Authentication -> Bypass login or authentication controls
Broken Access Control -> Access unauthorized resources or functions
File Upload -> Upload malicious executable files
Command Injection -> Execute operating system commands
SQL Injection -> Manipulate database queries
```

These vulnerability classes are fundamental to web application penetration testing and are covered in greater depth throughout later modules.
