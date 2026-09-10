# Development Frameworks & APIs — Learning

Web development frameworks provide reusable components and functionality to build modern web applications faster.

Common backend frameworks include:

- `Laravel` -> PHP
- `Express` -> Node.js
- `Django` -> Python
- `Rails` -> Ruby

Large web applications often use multiple frameworks and web servers together.

---

## APIs

`APIs` allow the front end to communicate with backend components.

Typical flow:

```text
Front End
    ↓ API Request
Back End
    ↓ Process Data
Database / Services
    ↓
API Response
    ↓
Front End
```

APIs are commonly used to:

- Send user input
- Retrieve data
- Trigger backend actions
- Connect different application components

---

## Query Parameters

Web applications commonly send parameters using `GET` or `POST`.

### GET

Parameters are included directly in the URL:

```text
/search.php?item=apples
```

General format:

```text
/path?parameter=value
```

### POST

Parameters are placed inside the request body:

```http
POST /search.php HTTP/1.1

item=apples
```

Query parameters allow the same endpoint to process different values.

---

## Web APIs

A `Web API` exposes backend functionality over HTTP.

Examples include:

- Retrieving weather information
- Searching users
- Retrieving posts
- Creating content
- Updating application data

API responses commonly use:

- `JSON`
- `XML`

Two common API standards are:

- `SOAP`
- `REST`

---

## SOAP

`SOAP` (**Simple Object Access Protocol**) exchanges structured data using XML.

Both requests and responses are generally formatted as XML.

Example:

```xml
<?xml version="1.0"?>

<soap:Envelope
xmlns:soap="http://www.example.com/soap/soap/"
soap:encodingStyle="http://www.w3.org/soap/soap-encoding">

<soap:Header>
</soap:Header>

<soap:Body>
  <soap:Fault>
  </soap:Fault>
</soap:Body>

</soap:Envelope>
```

SOAP is useful for:

- Structured data
- Complex objects
- Serialized objects
- Binary data
- Stateful operations

Its main disadvantage is that requests can become long and complex.

---

## REST

`REST` (**Representational State Transfer**) commonly uses URL paths to identify resources.

Example:

```text
/search/users/1
```

REST responses are commonly returned as:

- `JSON`
- `XML`
- `x-www-form-urlencoded`
- Raw data

Example JSON response:

```json
{
  "100001": {
    "date": "01-01-2021",
    "content": "Welcome to this web application."
  },
  "100002": {
    "date": "02-01-2021",
    "content": "This is the first post on this web app."
  }
}
```

REST APIs usually split functionality into smaller endpoints, making applications more modular and scalable.

---

## REST HTTP Methods

REST commonly uses HTTP methods to perform actions on resources:

- `GET` -> Retrieve data
- `POST` -> Create data
- `PUT` -> Create or replace data
- `DELETE` -> Remove data

Example:

```text
GET     /users/1
POST    /users
PUT     /users/1
DELETE  /users/1
```

`POST` is generally non-idempotent, while `PUT` is generally idempotent.