# HTML Injection — Practice

What text would be displayed on the page if we use the following payload as our input: <a href="http://www.hackthebox.com">Click Me</a>

---

## Solve


![alt text](images/solve.png)

Answer : 

```html
<p id="output">Your name is <a href="http://www.hackthebox.com">Click Me</a></p> -> "Your name is Click Me"
```

