# HTML Injection

If the server has an input space, you can try to index the HTML code on the web page.

### Payload:

```html
<h1>Hacked</h1>
```

if your HTML tag was indexed, the app is vulnerable to HTML Injection and probably XSS as well.
