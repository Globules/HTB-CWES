# Sensitive Data Exposure — Practice

Check the above login form for exposed passwords. Submit the password as the answer.

---

## Solve

Inside the login page source code : 

```html
<form action="#" method="post">

    <div class="container">
        <label for="uname"><b>Username</b></label>
        <input type="text" required>

        <label for="psw"><b>Password</b></label>
        <input type="password" required>

        <!-- TODO: remove test credentials admin:HiddenInPlainSight -->

        <button type="submit">Login</button>
    </div>
</form>
```