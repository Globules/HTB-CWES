# Front End vs. Back End — Learning

Web applications are generally divided into two main parts:

- `Front End` -> Runs on the client-side inside the browser.
- `Back End` -> Runs on the server-side and handles application logic, data, and services.

A developer working with both is commonly called a `Full Stack` developer.

---

## Front End

The front end contains everything the user directly sees and interacts with in the browser.

The three main front-end technologies are:

- `HTML` -> Structure and content
- `CSS` -> Styling and visual design
- `JavaScript` -> Dynamic behavior and functionality

Example:

```html
<p><strong>Welcome to Hack The Box Academy</strong></p>
<p><em>This is some italic text.</em></p>
<p><span style="color: #0000ff;">This is some blue text.</span></p>
```

Other front-end responsibilities include:

- Visual design
- `UI` design
- `UX` design
- Responsive design
- Cross-browser compatibility

Front-end code is interpreted directly by the browser and should work across different:

- Devices
- Screen sizes
- Browsers
- Operating systems

---

## Back End

The back end contains the core functionality of the web application and runs on the server.

Without a back end, a web application would mostly behave like a collection of static pages.

Main back-end components include:

### Back End Servers

The systems hosting the application.

Common environments:

- `Linux`
- `Windows`
- Containers

---

### Web Servers

Web servers receive and process HTTP connections.

Examples:

- `Apache`
- `NGINX`
- `IIS`

---

### Databases

Databases store and retrieve application data.

Relational databases:

- `MySQL`
- `MSSQL`
- `Oracle`
- `PostgreSQL`

Non-relational databases:

- `NoSQL`
- `MongoDB`

---

### Development Frameworks

Frameworks are used to build the application's backend logic.

Examples:

- `Laravel` -> PHP
- `ASP.NET` -> C#
- `Spring` -> Java
- `Django` -> Python
- `Express` -> NodeJS / JavaScript

---

## Back End Responsibilities

Common backend responsibilities include:

- Application logic
- Core functionality
- Database management
- Libraries and dependencies
- Business logic
- API implementation
- Third-party integrations
- Cloud services integration

---

## Component Isolation

Backend components can be isolated using separate servers or containers.

Example:

```text
Container 1 -> Web Application
Container 2 -> Database
Container 3 -> Additional Service
```

This improves segmentation and can limit the impact of a compromise.

Technologies such as `Docker` can be used for this purpose.

---

## Securing Front End and Back End

Access to the backend source code is usually not available during a normal external penetration test.

However, vulnerabilities may still be discovered by interacting with the application.

Examples:

- SQL Injection
- Command Injection
- Local File Inclusion
- Authentication flaws
- Access control issues

---

## Whitebox vs. Blackbox Pentesting

### Whitebox Pentesting

The tester has access to source code or internal implementation details.

This enables:

- Code review
- Logic analysis
- Identification of hardcoded secrets
- Identification of hidden vulnerabilities

Front-end code is often directly available to the tester.

---

### Blackbox Pentesting

The tester does not have access to source code and must test the application externally.

This is common for backend components.

However, source code may sometimes become available through:

- Open-source projects
- Local File Inclusion
- Source code disclosure
- Misconfigurations

Once obtained, backend code can be reviewed for:

- Passwords
- Secrets
- API keys
- Vulnerable functions
- Hidden functionality

---

## Common Developer Security Mistakes

Common mistakes include:

1. Permitting invalid data into databases
2. Treating security as a final step
3. Creating custom security mechanisms
4. Storing passwords in plaintext
5. Using weak passwords
6. Storing unencrypted sensitive data
7. Trusting client-side validation
8. Trusting third-party code
9. Hardcoding backdoor accounts
10. Improper SQL handling
11. Remote File Inclusion
12. Insecure data handling
13. Weak encryption
14. Poor cryptographic implementations
15. Web Application Firewall misconfigurations

---

## OWASP Top 10

Common web application vulnerability categories include:

1. Broken Access Control
2. Cryptographic Failures
3. Injection
4. Insecure Design
5. Security Misconfiguration
6. Vulnerable and Outdated Components
7. Identification and Authentication Failures
8. Software and Data Integrity Failures
9. Security Logging and Monitoring Failures
10. Server-Side Request Forgery (`SSRF`)

These vulnerabilities form the foundation of many web penetration testing techniques and should be understood, exploited safely, and explained clearly during assessments.

- 
