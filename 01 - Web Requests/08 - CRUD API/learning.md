# CRUD API — Learning

A CRUD API allows a client to interact with backend data using HTTP methods.

Typical API paths identify both the resource and the specific entity being manipulated.

Example:

```bash
curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london
```

Here:

- `api.php` is the API endpoint.
- `city` identifies the resource or database entity.
- `london` identifies the specific entry.

---

## APIs

APIs often expose resources through URL paths.

General format:

```text
/api.php/<resource>/<entity>
```

Example:

```text
/api.php/city/london
```

The HTTP method determines which operation will be performed on the resource.

---

## CRUD

CRUD represents the four main operations commonly performed on data:

| Operation | HTTP Method | Description |
| --- | --- | --- |
| `Create` | `POST` | Adds new data. |
| `Read` | `GET` | Retrieves existing data. |
| `Update` | `PUT` / `PATCH` | Modifies existing data. |
| `Delete` | `DELETE` | Removes existing data. |

A common mapping is therefore:

```text
Create  -> POST
Read    -> GET
Update  -> PUT / PATCH
Delete  -> DELETE
```

Access controls determine which CRUD operations each user is allowed to perform.

---

## Read

The `GET` method is used to retrieve data from the API.

Example:

```bash
curl http://<SERVER_IP>:<PORT>/api.php/city/london
```

Example response:

```json
[{"city_name":"London","country_name":"(UK)"}]
```

The response can be formatted using `jq`:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/london | jq
```

Example:

```json
[
  {
    "city_name": "London",
    "country_name": "(UK)"
  }
]
```

Useful options:

| Option | Description |
| --- | --- |
| `-s` | Silences unnecessary cURL output. |
| `jq` | Formats JSON output. |

A partial value may return multiple matching entries:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/le | jq
```

An empty value may return all entries:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/ | jq
```

---

## Create

The `POST` method is commonly used to create a new entry.

Example:

```bash
curl -X POST 
http://<SERVER_IP>:<PORT>/api.php/city/ 
-d '{"city_name":"HTB_City","country_name":"HTB"}' 
-H 'Content-Type: application/json'
```

Important elements:

| Element | Description |
| --- | --- |
| `-X POST` | Sends a POST request. |
| `-d` | Adds the JSON data to the request body. |
| `Content-Type: application/json` | Tells the server that the request body contains JSON. |

The created entry can then be retrieved with:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/HTB_City | jq
```

Example response:

```json
[
  {
    "city_name": "HTB_City",
    "country_name": "HTB"
  }
]
```

---

## Update

The `PUT` method is commonly used to update an existing resource.

The entity being modified is usually specified directly in the URL.

Example:

```bash
curl -X PUT 
http://<SERVER_IP>:<PORT>/api.php/city/london 
-d '{"city_name":"New_HTB_City","country_name":"HTB"}' 
-H 'Content-Type: application/json'
```

This request targets:

```text
/api.php/city/london
```

and replaces its data with:

```json
{
  "city_name": "New_HTB_City",
  "country_name": "HTB"
}
```

The result can be verified using `GET`:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City | jq
```

---

## PUT vs PATCH

Both `PUT` and `PATCH` may be used to update resources.

| Method | Usage |
| --- | --- |
| `PUT` | Usually replaces or updates the entire resource. |
| `PATCH` | Usually updates only specific fields of the resource. |

Example concept:

```json
PUT:
{
  "city_name": "Paris",
  "country_name": "France"
}
```

A `PATCH` request may only modify one field:

```json
{
  "city_name": "Paris"
}
```

The `OPTIONS` method can sometimes be used to determine which HTTP methods an endpoint accepts.

```bash
curl -X OPTIONS http://<SERVER_IP>:<PORT>/api.php/city/
```

> **Note:** Some APIs may also use `PUT` to create an entry if the requested resource does not already exist.

---

## DELETE

The `DELETE` method removes a specific resource.

Example:

```bash
curl -X DELETE http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City
```

The deletion can be verified using `GET`:

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City | jq
```

If the resource no longer exists, the API may return:

```json
[]
```

---

## CRUD Summary

Example API endpoint:

```text
/api.php/city/london
```

The HTTP method determines the operation:

```text
GET     /api.php/city/london
POST    /api.php/city/
PUT     /api.php/city/london
DELETE  /api.php/city/london
```

Typical workflow:

```text
POST   -> Create an entry
GET    -> Read the entry
PUT    -> Update the entry
DELETE -> Remove the entry
```

In real applications, these operations are usually protected by authentication and authorization mechanisms.

Authentication may rely on:

- Session cookies
- `Authorization` headers
- JWT tokens
- API keys

Being able to reproduce CRUD requests directly with cURL is useful during API assessments and bug bounty testing because it allows direct interaction with backend endpoints without relying on the frontend.
