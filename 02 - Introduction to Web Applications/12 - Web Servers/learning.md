# Web Servers — Learning

A `Web Server` is an application running on the backend server that handles HTTP traffic between clients and the web application.

Web servers commonly listen on:

- `80` -> HTTP
- `443` -> HTTPS

Their main responsibilities are:

- Receive HTTP requests
- Route requests to the correct resource
- Process requests
- Return HTTP responses

---

## Workflow

Typical flow:

```text
Client
  ↓ HTTP Request
Web Server
  ↓
Application / Resource
  ↓
Web Server
  ↓ HTTP Response
Client
```

Common HTTP response codes include:

| Code | Description |
| --- | --- |
| `200 OK` | Request succeeded |
| `301 Moved Permanently` | Permanent redirect |
| `302 Found` | Temporary redirect |
| `400 Bad Request` | Invalid request syntax |
| `401 Unauthorized` | Authentication required |
| `403 Forbidden` | Access denied |
| `404 Not Found` | Resource does not exist |
| `405 Method Not Allowed` | HTTP method is not allowed |
| `408 Request Timeout` | Request timed out |
| `500 Internal Server Error` | Server-side error |
| `502 Bad Gateway` | Invalid response from upstream server |
| `504 Gateway Timeout` | Upstream server did not respond in time |

Web servers can process different types of data, including:

- Text
- `JSON`
- Binary data
- File uploads

---

## cURL

Display only response headers:

```bash
curl -I https://academy.hackthebox.com
```

Example:

```http
HTTP/2 200
content-type: text/html; charset=UTF-8
```

Retrieve the page content:

```bash
curl https://academy.hackthebox.com
```

Example:

```html
<!doctype html>
<html lang="en">
<head>
<title>Cyber Security Training : HTB Academy</title>
</head>
```

---

## Apache

`Apache`, also known as `httpd`, is a popular open-source web server.

It commonly runs on:

- Linux
- Windows
- macOS

Apache is frequently used with `PHP`, but also supports:

- `.NET`
- `Python`
- `Perl`
- `Bash` through CGI

Its functionality can be extended using modules.

Example:

```text
Apache + PHP + mod_php
```

---

## NGINX

`NGINX` is an open-source web server designed to efficiently handle large numbers of concurrent connections.

Main characteristics:

- Asynchronous architecture
- Low memory usage
- Low CPU usage
- High performance
- Well suited for high-traffic applications

NGINX is commonly used as:

- Web server
- Reverse proxy
- Load balancer

---

## IIS

`IIS` (**Internet Information Services**) is Microsoft's web server.

It primarily runs on:

```text
Windows Server
```

IIS is commonly used with:

- `.NET`
- `ASP.NET`
- `PHP`
- `FTP`

It integrates closely with:

- Active Directory
- Windows Authentication

This allows users to authenticate to web applications using their Windows or Active Directory credentials.

---

## Other Web Servers

Other commonly encountered web servers include:

- `Apache Tomcat` -> Java applications
- `Node.js` -> Backend JavaScript applications

Identifying the web server during a penetration test can help determine:

- Technologies in use
- Possible configurations
- Available modules
- Known vulnerabilities
- Potential attack surface

