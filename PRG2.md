# PROGRAM – 02

## Experiment 2: Vulnerability Scanning & Assessment

### Steps

## Step 1: Open DVWA Website by Starting It with Following Commands in Kali Root Terminal

```bash
systemctl start apache2
```

```bash
systemctl start mysql
```

- Copy the URL of the website:

```text
127.0.0.1/DVWA
```

- Paste it in Firefox.
- If prompted, use:

```text
Username: admin
Password: password
```

## Step 2: Open Kali Machine

Type command:

```bash
nikto -h http://127.0.0.1/DVWA/
```

We obtain various details, such as:

- Server name
- Paths
- Other vulnerability information

## Step 3: Copy the Extensions Such as /DVWA/config and Paste It to the Existing URL

Example:

```text
http://127.0.0.1/DVWA/config/
```

Similarly, try with other extensions to the existing URL:

```text
http://127.0.0.1/DVWA/tests/
```

# YOU CAN CARRY OUT THE SAME PROCEDURE FOR JUICE SHOP

By typing the following command:

```bash
juice-shop
```

Then run:

```bash
nikto -h "<juice shop url>"
```
