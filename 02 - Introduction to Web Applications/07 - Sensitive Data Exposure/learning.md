# Sensitive Data Exposure — Learning

Front-end components run on the `client-side`, so vulnerabilities usually affect the end-user rather than directly compromising the backend.

However, attacking privileged users such as administrators can lead to:

- Unauthorized access
- Sensitive data exposure
- Access to privileged functionality
- Service disruption
- Potential backend compromise

---

## Sensitive Data Exposure

`Sensitive Data Exposure` occurs when sensitive information is exposed in clear text to the user.

This information is often found in:

- HTML source code
- JavaScript files
- Comments
- Hidden links
- Debug information
- User information
- Credentials
- Password hashes
- Internal directories

The page source can be viewed using:

```text
Right Click -> View Page Source
```

or:

```text
CTRL + U
```

It can also be inspected using tools such as `Burp Suite`.

---

## Source Code Review

Reviewing the application's source code should be one of the first steps during a web assessment.

Useful locations to inspect include:

- HTML comments
- JavaScript files
- Hidden parameters
- Internal endpoints
- Test pages
- Debug functionality
- Credentials
- API endpoints

This can reveal low-hanging fruit that may provide additional access to the application.

---

## Example

A developer may accidentally leave credentials inside an HTML comment:

```html
<!-- TODO: remove test credentials test:test -->
```

These credentials may still be valid:

```text
Username: test
Password: test
```

Other useful information that may be exposed includes:

- Test accounts
- Hidden directories
- Debug parameters
- Internal functionality
- Sensitive endpoints

Such information can sometimes be leveraged to attack backend components.

---

## Prevention

Client-side source code should only contain information required for the application to function.

Developers should:

- Remove unnecessary comments
- Remove test credentials
- Remove hidden or unused links
- Avoid exposing sensitive information
- Review client-side code before deployment
- Classify which data can safely be exposed
- Inspect JavaScript for secrets

JavaScript may also be:

- Packed
- Minified
- Obfuscated

These techniques can make automated analysis more difficult, but sensitive information should never rely on obfuscation alone for protection.

