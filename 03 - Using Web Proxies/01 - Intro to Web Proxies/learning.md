# Intro to Web Proxies — Learning

## Intro to Web Proxies

Modern web and mobile applications continuously communicate with backend servers.

Web application penetration testing therefore relies heavily on analyzing and manipulating the traffic exchanged between:

```text
Client
  ↓
Web Proxy
  ↓
Back-End Server
```

A `Web Proxy` allows a tester to intercept this traffic and inspect or modify HTTP requests and responses.

---

## What Are Web Proxies?

A web proxy acts as a `Man-in-the-Middle (MITM)` between the client and the server.

Typical flow:

```text
Browser / Mobile App
        ↓
     Web Proxy
        ↓
   Back-End Server
```

Web proxies mainly focus on web traffic such as:

- `HTTP/80`
- `HTTPS/443`

Unlike tools such as `Wireshark`, which capture general network traffic, web proxies are specifically designed for analyzing web requests and responses.

They allow testers to:

- Capture requests
- Inspect responses
- Modify requests
- Replay requests
- Analyze backend behavior

---

## Uses of Web Proxies

Web proxies can be used for:

- Web vulnerability scanning
- Web fuzzing
- Web crawling
- Application mapping
- HTTP request analysis
- Configuration testing
- Code review support

The two main tools covered are:

- `Burp Suite`
- `OWASP ZAP`

---

## Burp Suite

`Burp Suite` is one of the most widely used web proxies for web penetration testing.

Main features include:

- HTTP interception
- Request modification
- Request replay
- Built-in Chromium browser
- Intruder
- Repeater
- Extensions
- Web vulnerability scanning

Burp is available in:

- `Community` -> Free
- `Professional` -> Paid
- `Enterprise` -> Paid

Some paid-only features include:

- Active web application scanner
- Faster Intruder
- Certain extensions and advanced functionality

The Community edition is sufficient for many manual web penetration testing tasks.

---

## OWASP ZAP

`OWASP ZAP` (**Zed Attack Proxy**) is a free and open-source web proxy maintained by the OWASP community.

It provides features similar to Burp, including:

- HTTP interception
- Request manipulation
- Crawling
- Vulnerability scanning
- Web application mapping
- Fuzzing

Its main advantage is that it is completely free and does not restrict features behind a paid license.

---

## Burp Suite vs ZAP

### Burp Suite

- Very mature
- Widely used professionally
- Strong manual testing workflow
- Large extension ecosystem
- Advanced features available in `Burp Pro`

### ZAP

- Free
- Open-source
- No paid feature restrictions
- Community maintained
- Includes automated scanning capabilities

Both tools can perform most common web proxy tasks, and learning both provides flexibility during penetration tests.
