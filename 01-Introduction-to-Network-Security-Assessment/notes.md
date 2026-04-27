# Module 1: Introduction to Network Security Assessment

---

## 🔑 Key Terminologies

### Vulnerability

A security weakness in a system that can be exploited by an attacker.

### Exploit

A method or tool used to take advantage of a vulnerability.

### Threat

Anything that has the potential to cause harm to a system.

### Attack

A technique used to exploit a vulnerability.

### Threat Vectors

Paths or methods used by attackers to gain access to a system.
Examples:

* Direct access
* Wireless networks
* Emails

---

## 🛡️ Need for Network Security

* Protect organizational assets from threat actors
* Prevent unauthorized access
* Maintain:

  * **Confidentiality**
  * **Integrity**
  * **Availability** (CIA Triad)

---

## 🌐 Network Services and Ports

### Network Protocols

Protocols define how data is transmitted across a network.
Each protocol is associated with a specific port number.

---

### Common Protocols

| Protocol | Description                             | Port                    |
| -------- | --------------------------------------- | ----------------------- |
| SSH      | Secure remote access with encryption    | 22                      |
| Telnet   | Unsecure remote access (no encryption)  | 23                      |
| DNS      | Resolves domain names to IP addresses   | 53                      |
| FTP      | File transfer between client and server | 20 (data), 21 (control) |

---

## 🔍 Network Scanning & Enumeration

### Scanning

Technique used to:

* Discover live hosts
* Identify open ports
* Detect running services
* Identify operating system

---

### Enumeration

Process of gathering detailed information such as:

* Usernames and groups
* Network shares
* Running services
* Routing tables
* Banner information

---

## 🧪 Practical (Nmap)

### 🔹 Ping Sweep

nmap -sn 192.168.241.0/24

---

### 🔹 Default Port Scan

nmap 192.168.241.19

---

### 🔹 Aggressive Scan

nmap -A 192.168.241.19

---

### 🔹 Full Port + Fast Scan

nmap -A -T4 -p- 192.168.241.19

---

## 🧪 Enumeration using Metasploit

### Steps:

msfconsole
search smb_version
use auxiliary/scanner/smb/smb_version
show options
set rhosts 192.168.241.19
run

✔ Used to detect SMB version

---

### SMB Enumeration Tool

smbmap -H 192.168.241.19

---

## ⚠️ Identifying Vulnerabilities

A vulnerability is a weakness that can be exploited by a threat actor.

---

### 🔻 Common Misconfigurations

* Default configurations
* Weak encryption
* Unsecure protocols
* Open permissions
* Unsecured root account
* Open ports and services

---

## 🛠️ Vulnerability Scanning using Nessus

### Steps:

1. Create a new scan
2. Choose Basic or Advanced Scan
3. Enter target IP
4. Launch the scan

---

### 📊 Results Include:

* List of vulnerabilities
* Severity ratings
* Remediation steps

---

### 📄 Reporting

* Export reports as:

  * Executive report
  * Custom report
* Supported format: PDF

---

## ✅ Key Takeaways

* Network assessment helps identify security weaknesses
* Scanning and enumeration are critical steps
* Misconfigurations are a major source of vulnerabilities
* Tools like Nmap, Metasploit, and Nessus are essential

---
