# HTML Injection — Learning

`HTML Injection` occurs when unfiltered user input is rendered directly as HTML by the browser.

Input validation and sanitization should be performed on both:

- Front end
- Back end

HTML Injection may occur when user-controlled data is:

- Retrieved from the backend and rendered without sanitization
- Directly processed by JavaScript on the client-side
- Inserted into the DOM as HTML

---

## Impact

If an attacker controls rendered HTML, they may modify the page content.

Possible impacts include:

- Injecting arbitrary HTML
- Creating fake login forms
- Phishing users
- Injecting external content
- Defacing the web page
- Displaying malicious advertisements

A malicious login form could trick users into submitting credentials to an attacker-controlled server.

---

## Example

Vulnerable JavaScript:

```javascript
function inputFunction() {
    var input = prompt("Please enter your name", "");

    if (input != null) {
        document.getElementById("output").innerHTML = "Your name is " + input;
    }
}
```

The problem is that user input is inserted directly into:

```javascript
innerHTML
```

without sanitization.

A simple HTML payload can therefore be interpreted by the browser instead of displayed as plain text.

Example:

```html
<style>
body {
    background-image: url('https://academy.hackthebox.com/images/logo.svg');
}
</style>
```

If the page background changes, the application is interpreting the supplied input as HTML.

---

## Client-Side HTML Injection

In this example, the injection occurs entirely on the client-side:

```text
User Input
    ↓
JavaScript
    ↓
innerHTML
    ↓
Browser renders injected HTML
```

Because the injected content is not stored on the backend, refreshing the page restores the original state.