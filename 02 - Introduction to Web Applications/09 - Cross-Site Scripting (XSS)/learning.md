# Cross-Site Scripting (XSS) — Learning

`Cross-Site Scripting (XSS)` occurs when attacker-controlled JavaScript is executed in another user's browser.

It is similar to `HTML Injection`, but instead of only injecting HTML, XSS allows JavaScript execution on the client-side.

Possible impact includes:

- Session theft
- Account takeover
- Actions performed as the victim
- Access to sensitive data
- Client-side manipulation

---

## XSS Types

| Type | Description |
| --- | --- |
| `Reflected XSS` | User input is immediately reflected in the response, such as in a search result or error message. |
| `Stored XSS` | User input is stored by the application and executed later when another user loads it. |
| `DOM XSS` | User input is processed directly by client-side JavaScript and written into the DOM. |

---

## Example

A DOM XSS payload may be:

```html
#"><img src=/ onerror=alert(document.cookie)>
```

If the application inserts this input into the DOM without sanitization, the browser may interpret it as HTML and execute the JavaScript event handler.

The payload accesses:

```javascript
document.cookie
```

and displays the current cookie value.

---

## Attack Flow

```text
Attacker-controlled input
        ↓
Application renders input
        ↓
Browser interprets injected HTML / JavaScript
        ↓
JavaScript executes in victim's browser
        ↓
Victim session or data may be exposed
```

A stolen session cookie may allow an attacker to impersonate the victim if the session is reusable.

XSS is therefore more dangerous than simple HTML Injection because it enables arbitrary client-side JavaScript execution.
