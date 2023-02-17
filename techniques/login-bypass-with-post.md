# Login bypass with POST

## Context:
> If an application uses GET to show prompt() login to the access page, try to use POST to get access to the final page.

<br>**Example**: <br>
<img src="https://i.imgur.com/1tXI15V.png" height=230px width=700px>

**Bypass:** 
```bash
curl -X POST url > index.html
```
<br>

**Note:**
> The CURL used POST to get the final page and is saved on index.html
