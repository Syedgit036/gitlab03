# PROGRAM – 01

## Experiment 1: Network Reconnaissance & Foot printing

### Procedure

## 1. Open Command Prompt and type:

### Get IP Address Details of System

```bash
ipconfig
```

- Note down your **IPv4 Address** and **Subnet Mask**, and perform Nmap on it.

Example:

```text
192.168.1.3 / 255.255.255.0
```

CIDR:

```text
/24
```

## 2. Discover Live Hosts in the Network

```bash
nmap -sn 192.168.1.1
```

## 3. Choose a Live Host IP and Perform Detailed Scan

```bash
nmap -sS -sV -O 192.168.1.1
```

This gives:

- Open ports
- Running services
- Guessed OS

## 4. Aggressive Scan with OS, Version, Script, and Traceroute

```bash
nmap -A 192.168.1.0/24
```

# Step 2. Perform Amass for Sub-domain Enumeration (External Reconnaissance Using Amass)

## 1. On Kali/Linux Terminal, Use the Command

```bash
amass enum -d <domain name>
```

Example:

```bash
amass enum -d microsoft.com
```

## 2. Note the Following Details

- IP Addresses
- ASN (Autonomous System Number)
- Hosting Provider Details
