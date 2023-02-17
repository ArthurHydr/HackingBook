---
'0': A
'1': p
'2': p
'3': l
'4': i
'5': c
'6': a
'7': t
'8': i
'9': o
'10': 'n'
'11': ' '
'12': 'n'
'13': e
'14': e
'15': d
'16': s
'17': ' '
'18': t
'19': o
'20': ' '
'21': u
'22': s
'23': e
'24': ' '
'25': G
'26': E
'27': T
'28': ' '
'29': m
'30': e
'31': t
'32': h
'33': o
'34': d
description: The application needs to use GET method
---

# Login bypass with POST

**Context:**

> If an application uses GET to show prompt() login to the access page, try to use POST to get access to the final page.

**Context Page:**

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Context Example</p></figcaption></figure>

**Bypass:**

```bash
curl -X POST url > index.html
```

**Note:**

> The CURL used POST to get the final page and is saved on index.html
