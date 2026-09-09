# JavaScript — Learning

`JavaScript` is one of the main programming languages used in web development.

It is primarily executed on the **client-side** inside the browser, but it can also be used on the back end with technologies such as `NodeJS`.

While:

- `HTML` -> Defines the structure
- `CSS` -> Controls the appearance
- `JavaScript` -> Controls functionality and interaction

Without JavaScript, most web pages would be mostly static.

---

## Example

JavaScript can be embedded directly into HTML using the `<script>` tag:

```html
<script type="text/javascript">
    // JavaScript code
</script>
```

External JavaScript files can also be loaded using `src`:

```html
<script src="./script.js"></script>
```

Example DOM manipulation:

```javascript
document.getElementById("button1").innerHTML = "Changed Text!";
```

This selects the HTML element with the ID `button1` and changes its content.

---

## Usage

JavaScript is commonly used to:

- Update page content dynamically
- Process user input
- Manipulate HTML elements
- Perform client-side calculations
- Create interactive interfaces
- Control animations
- Send HTTP requests
- Communicate with backend APIs

Example flow:

```text
User Action
    ↓
JavaScript
    ↓
HTTP Request
    ↓
Back End
    ↓
Response
    ↓
Update Page
```

Technologies such as `Ajax` allow JavaScript to send and receive data from the server without reloading the entire page.

Modern browsers include JavaScript engines capable of executing code directly on the client-side.

---

## JavaScript and the DOM

JavaScript can interact with the `DOM` to dynamically modify the web page.

It can modify:

- Text
- HTML elements
- Attributes
- CSS styles
- Forms
- Events

Example:

```javascript
document.getElementById("example").innerHTML = "New content";
```

This capability is fundamental to dynamic web applications and is also important when analyzing client-side vulnerabilities such as `XSS`.

---

## Frameworks

Modern web applications often use JavaScript frameworks and libraries instead of writing everything from scratch.

Common examples include:

- `Angular`
- `React`
- `Vue`
- `jQuery`

These frameworks simplify the development of:

- Dynamic interfaces
- User authentication flows
- Reusable components
- Real-time updates
- Complex frontend functionality

Some frameworks use JavaScript directly, while others use languages or syntax that are compiled into JavaScript before being executed by the browser.

