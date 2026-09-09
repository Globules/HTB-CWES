# Introduction — Learning

Web applications are interactive applications that run inside a web browser and generally follow a **client-server architecture**.

They are commonly composed of:

- **Front end** -> Runs in the browser and represents what the user sees.
- **Back end** -> Runs on the server and handles application logic, databases, and data processing.

Examples of web applications include:

- `Gmail`
- `Amazon`
- `Google Docs`

---

## Web Applications vs. Websites

Traditional websites are generally static and display the same content to every user.

Web applications are dynamic and can modify their content depending on user interaction.

### Website

- Mostly static content
- Limited interaction
- Content usually changed manually by developers
- Often associated with `Web 1.0`

### Web Application

- Dynamic content
- Interactive functionality
- Can provide different content for different users
- Often associated with `Web 2.0`

Web applications are also generally:

- Modular
- Platform-independent
- Compatible with different screen sizes

---

## Web Applications vs. Native Applications

Web applications run inside a browser and generally do not need to be installed locally.

Advantages:

- Platform-independent
- No local installation required
- All users use the same version
- Updates are deployed centrally on the server
- Lower maintenance costs

Native applications have other advantages:

- Better performance
- Direct access to operating system libraries
- Better access to local hardware
- Deeper integration with the operating system

Hybrid and progressive web applications combine characteristics of both approaches.

---

## Web Application Distribution

Web applications can be either open-source or proprietary.

### Open-Source

Examples:

- `WordPress`
- `OpenCart`
- `Joomla`

Their source code is publicly available and can usually be customized.

### Closed-Source

Examples:

- `Wix`
- `Shopify`
- `DotNetNuke`

These applications are generally developed and maintained by a company and distributed through licenses or subscriptions.

---

## Security Risks of Web Applications

Web applications often expose a large attack surface because they are publicly accessible and interact with:

- Users
- Databases
- Backend servers
- APIs
- Authentication systems
- Other internal services

A successful attack can lead to:

- Sensitive data exposure
- Account compromise
- Database compromise
- Server compromise
- Remote Code Execution
- Business disruption

Web applications should therefore be regularly tested and updated.

A common testing methodology is the **OWASP Web Security Testing Guide**.

---

## Web Application Testing

A typical web application assessment starts by analyzing front-end components:

- `HTML`
- `CSS`
- `JavaScript`

Potential vulnerabilities include:

- Sensitive Data Exposure
- Cross-Site Scripting (`XSS`)

The assessment then moves toward backend functionality and communication between the browser and server.

Testing should generally be performed from both:

- Unauthenticated perspective
- Authenticated perspective

This helps maximize attack surface coverage.

---

## Attacking Web Applications

Web applications are common attack targets because they are dynamic and constantly changing.

A small code change can introduce vulnerabilities that may lead to:

- Sensitive data disclosure
- Authentication bypass
- Privilege escalation
- File access
- Remote Code Execution

Multiple vulnerabilities can also be chained together to increase their impact.

---

## Common Web Vulnerabilities

### SQL Injection

`SQL Injection` occurs when user-controlled input is handled unsafely in database queries.

Possible impact:

- Read sensitive database data
- Modify database data
- Read or write files
- Obtain usernames
- Potential Remote Code Execution

SQL Injection may also expose Active Directory usernames, which could later be used for password spraying attacks.

---

### File Inclusion

A `File Inclusion` vulnerability may allow an attacker to read unintended files.

Possible impact:

- Read source code
- Discover hidden endpoints
- Access sensitive configuration
- Potential Remote Code Execution

---

### Unrestricted File Upload

An unrestricted file upload vulnerability occurs when the application does not properly validate uploaded files.

Example:

```text
Expected: image file
Uploaded: malicious server-side code
```

Possible impact:

- Upload malicious files
- Execute code on the server
- Take control of the web application server

---

### IDOR

`IDOR` stands for **Insecure Direct Object Reference**.

It occurs when an application exposes internal object identifiers without properly checking authorization.

Example:

```text
/user/701/edit-profile
/user/702/edit-profile
```

If changing `701` to `702` allows access to another user's data, the application may be vulnerable to IDOR.

Possible impact:

- Access other users' data
- Modify other users' resources
- Bypass authorization controls

---

### Broken Access Control

Broken Access Control occurs when users can perform actions outside their intended permissions.

Example registration request:

```text
username=bjones&password=Welcome1&email=bjones@inlanefreight.local&roleid=3
```

If the `roleid` parameter can be modified:

```text
roleid=1
```

and this creates an administrator account, the application is vulnerable to privilege escalation.

---

## Attack Chaining

A vulnerability does not always need to provide full compromise by itself.

Example attack chain:

```text
SQL Injection
    ↓
Extract usernames
    ↓
Password spraying
    ↓
Valid credentials
    ↓
Access VPN / Email / Internal resources
```

Combining several weaknesses can dramatically increase the impact of an attack.

Understanding how vulnerabilities interact is therefore an important part of web application penetration testing.
