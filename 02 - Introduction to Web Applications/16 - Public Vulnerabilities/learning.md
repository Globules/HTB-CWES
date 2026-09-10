# Public Vulnerabilities — Learning

Public vulnerabilities are known security flaws affecting web applications or their components.

They are often caused by:

- Coding mistakes
- Vulnerable dependencies
- Misconfigurations
- Outdated software
- Vulnerable plugins or extensions

Public vulnerabilities may sometimes allow attackers to compromise a backend server remotely.

---

## Public CVE

A `CVE` (**Common Vulnerabilities and Exposures**) is a public identifier assigned to a known security vulnerability.

Typical workflow:

```text
Identify Application
        ↓
Identify Version
        ↓
Search for Public CVEs
        ↓
Search for Public Exploits
        ↓
Verify Applicability
        ↓
Test Safely
```

The application version may sometimes be found in:

- Page source
- Application files
- Version endpoints
- Open-source repositories
- HTTP headers
- Static assets

Example:

```text
version.php
```

Once the version is known, public vulnerabilities can be searched using:

- `Exploit-DB`
- `Rapid7 DB`
- `Vulnerability Lab`
- `NVD`

External components should also be checked separately.

Examples:

```text
Application
├── Core
├── Plugin
├── Library
└── Framework
```

Each component may have its own vulnerabilities.

---

## CVE Priority

Public exploits with the highest impact are generally prioritized first.

Examples:

- Remote Code Execution (`RCE`)
- Authentication bypass
- Privilege escalation
- Arbitrary file upload
- Critical information disclosure

High CVSS scores can help identify potentially severe vulnerabilities.

---

## Common Vulnerability Scoring System (CVSS)

`CVSS` (**Common Vulnerability Scoring System**) is used to measure the severity of vulnerabilities.

Scores range from:

```text
0.0 -> 10.0
```

CVSS considers three groups of metrics:

- `Base`
- `Temporal`
- `Environmental`

The `Base` score describes the inherent characteristics of the vulnerability.

`Temporal` metrics account for factors that may change over time.

`Environmental` metrics adapt the score to a specific organization's environment.

---

## CVSS v2

| Severity | Score |
| --- | --- |
| Low | `0.0 - 3.9` |
| Medium | `4.0 - 6.9` |
| High | `7.0 - 10.0` |

---

## CVSS v3

| Severity | Score |
| --- | --- |
| None | `0.0` |
| Low | `0.1 - 3.9` |
| Medium | `4.0 - 6.9` |
| High | `7.0 - 8.9` |
| Critical | `9.0 - 10.0` |

---

## Back-End Server Vulnerabilities

Public vulnerabilities should not only be searched for the web application itself.

Other components should also be reviewed:

- Web server
- Operating system
- Database
- Framework
- Plugins
- Libraries
- Services

Web servers are particularly important because they may be directly exposed to the internet.

Example:

```text
Internet
   ↓
Web Server
   ↓
Application
   ↓
Database
```

A vulnerability affecting the web server may allow remote compromise of the backend server.

---

## Shellshock Example

`Shellshock` is an example of a critical vulnerability that affected systems using vulnerable versions of Bash.

In some web environments, specially crafted HTTP requests could trigger command execution through vulnerable CGI configurations.

Possible impact:

```text
HTTP Request
     ↓
Vulnerable CGI / Bash
     ↓
Command Execution
     ↓
Backend Server Compromise
```

---

## Internal Back-End Vulnerabilities

Some vulnerabilities are not directly exploitable from the internet.

They may become useful after gaining access to:

- The backend server
- The internal network
- Another compromised host

These vulnerabilities may then be used for:

- Privilege escalation
- Lateral movement
- Database compromise
- Compromise of additional servers

Even if a vulnerability is not externally exploitable, it should still be patched because it may become critical after an attacker gains an initial foothold.