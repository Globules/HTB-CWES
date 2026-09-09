# HTML — Learning

`HTML` (**HyperText Markup Language**) is the main language used to structure web pages.

It defines elements such as:

- Titles
- Paragraphs
- Forms
- Images
- Links
- Scripts
- Styles

The browser interprets the HTML code and renders the page for the user.

---

## Basic HTML Structure

Example:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <h1>A Heading</h1>
        <p>A Paragraph</p>
    </body>
</html>
```

Basic structure:

```text
document
 └── html
     ├── head
     │   └── title
     └── body
         ├── h1
         └── p
```

The main `<html>` element contains the entire HTML document.

---

## HTML Elements

HTML elements are generally composed of:

```html
<tag>Content</tag>
```

Example:

```html
<p>A Paragraph</p>
```

Elements can also contain attributes such as:

```html
<p id="para1">Text</p>
```

Common attributes include:

- `id`
- `class`

These attributes can be used by CSS, JavaScript, and DOM manipulation.

---

## Main HTML Elements

### Head

The `<head>` element contains information that is generally not directly displayed inside the page.

Example:

```html
<head>
    <title>Page Title</title>
</head>
```

---

### Body

The `<body>` contains the main visible content of the page.

Example:

```html
<body>
    <h1>A Heading</h1>
    <p>A Paragraph</p>
</body>
```

---

### Style

The `<style>` element can contain CSS code.

```html
<style>
    p {
        color: blue;
    }
</style>
```

---

### Script

The `<script>` element can contain JavaScript code.

```html
<script>
    console.log("Hello");
</script>
```

---

## URL Encoding

`URL Encoding`, also known as `Percent-Encoding`, is used to encode characters that cannot safely appear directly inside URLs.

The general format is:

```text
%XX
```

where `XX` represents the hexadecimal value of the character.

Examples:

| Character | Encoding |
| --- | --- |
| space | `%20` |
| `!` | `%21` |
| `"` | `%22` |
| `#` | `%23` |
| `$` | `%24` |
| `%` | `%25` |
| `&` | `%26` |
| `'` | `%27` |
| `(` | `%28` |
| `)` | `%29` |

Example:

```text
' -> %27
space -> %20
```

Spaces may also sometimes be represented using:

```text
+
```

Tools such as Burp Suite can encode and decode URL values.

---

## DOM

The `DOM` (**Document Object Model**) represents the structure of an HTML document as a tree of objects.

Example:

```text
document
 └── html
     ├── head
     └── body
         ├── h1
         └── p
```

The DOM allows scripts to dynamically access and modify:

- Content
- Structure
- Styles

The DOM is divided into:

- `Core DOM` -> Standard model for all documents
- `XML DOM` -> Standard model for XML documents
- `HTML DOM` -> Standard model for HTML documents

---

## DOM Element Selection

HTML elements can be identified using:

- `id`
- Tag name
- Class name

Example elements:

```html
<p id="para1" class="text">Hello</p>
```

The DOM structure makes it possible to locate and manipulate specific elements through JavaScript.

Understanding the DOM is particularly useful when analyzing front-end vulnerabilities such as `XSS`, where an attacker may attempt to modify existing elements or inject new ones.
