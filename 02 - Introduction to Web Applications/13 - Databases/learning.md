# Databases — Learning

Databases are used by web applications to store and retrieve data.

They may contain:

- User accounts
- Passwords
- Posts
- Files
- Images
- Application content
- Configuration data

Important database characteristics include:

- `Speed`
- `Storage capacity`
- `Scalability`
- `Cost`

---

## Relational Databases (SQL)

`SQL` databases store data using:

- Tables
- Rows
- Columns
- Keys
- Relationships

Example:

```text
users
├── id
├── username
├── first_name
└── last_name

posts
├── id
├── user_id
├── date
└── content
```

Tables can be linked using keys.

Example:

```text
users.id
   ↓
posts.user_id
```

This allows data from different tables to be related without duplicating all information.

The structure and relationships between tables form the database `Schema`.

---

## Common SQL Databases

| Database | Description |
| --- | --- |
| `MySQL` | Popular open-source relational database |
| `MSSQL` | Microsoft SQL Server, commonly used with Windows and IIS |
| `Oracle` | Enterprise-focused relational database |
| `PostgreSQL` | Open-source and highly extensible relational database |

Other examples include:

- `SQLite`
- `MariaDB`
- `Amazon Aurora`
- `Azure SQL`

---

## Non-Relational Databases (NoSQL)

`NoSQL` databases do not necessarily use traditional tables, rows, columns, or fixed schemas.

They are generally more flexible and scalable for unstructured or changing datasets.

Common storage models include:

- Key-Value
- Document-Based
- Wide-Column
- Graph

---

## Key-Value Model

Data is stored as a key associated with a value.

Example:

```json
{
  "100001": {
    "date": "01-01-2021",
    "content": "Welcome to this web application."
  }
}
```

Conceptually:

```text
key -> value
```

This is similar to dictionaries or maps in programming languages.

---

## Document-Based Model

Document-based databases store data as structured documents, commonly using JSON-like objects.

Example:

```json
{
  "username": "user1",
  "email": "user@example.com",
  "role": "user"
}
```

Each document may contain its own structure and metadata.

---

## Common NoSQL Databases

| Database | Description |
| --- | --- |
| `MongoDB` | Document-based NoSQL database using JSON-like documents |
| `Elasticsearch` | Optimized for searching and analyzing large datasets |
| `Apache Cassandra` | Highly scalable distributed NoSQL database |

Other examples include:

- `Redis`
- `Neo4j`
- `CouchDB`
- `Amazon DynamoDB`

---

## SQL vs NoSQL

### SQL

Best suited for:

- Structured data
- Strong relationships
- Defined schemas
- Complex relational queries

### NoSQL

Best suited for:

- Flexible data structures
- Large datasets
- Rapidly changing data
- Horizontal scalability

---

## Use in Web Applications

Backend applications connect to databases to store and retrieve data.

Example PHP connection to MySQL:

```php
$conn = new mysqli("localhost", "user", "pass");
```

Create a database:

```php
$sql = "CREATE DATABASE database1";
$conn->query($sql);
```

Connect to a specific database:

```php
$conn = new mysqli("localhost", "user", "pass", "database1");
```

Execute a query:

```php
$query = "SELECT * FROM table_1";
$result = $conn->query($query);
```

---

## User Input and Databases

Web applications often use user input inside database queries.

Example:

```php
$searchInput = $_POST['findUser'];
$query = "SELECT * FROM users WHERE name LIKE '%$searchInput%'";
$result = $conn->query($query);
```

The result may then be displayed to the user:

```php
while ($row = $result->fetch_assoc()) {
    echo $row["name"]."<br>";
}
```

General flow:

```text
User Input
    ↓
Web Application
    ↓
Database Query
    ↓
Database
    ↓
Result
    ↓
User
```

If user input is inserted into database queries without proper validation or safe query handling, vulnerabilities such as `SQL Injection` may occur.