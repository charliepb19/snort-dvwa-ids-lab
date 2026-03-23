# Snort IDS Lab – DVWA Attack Detection

## Overview

This project demonstrates a simulated intrusion detection environment using Snort IDS to detect malicious network activity targeting a vulnerable web application.

The lab consists of:

• Kali Linux attacker  
• Ubuntu router running Snort IDS  
• DVWA vulnerable web application  

Snort monitors network traffic and detects:

• ICMP reconnaissance  
• SQL injection attacks

---

## Lab Architecture

Kali Attacker → Snort Router → DVWA Web Server

---

## Technologies Used

Snort  
Kali Linux  
Ubuntu Server  
DVWA  
VirtualBox

---

## Custom Detection Rules

### ICMP Detection


alert icmp any any -> $HOME_NET any (msg:"ICMP Ping Detected"; sid:1000001; rev:2;)


### SQL Injection Detection


alert tcp any any -> $HOME_NET 80 (msg:"SQL Injection Attempt"; content:"OR"; sid:1000002; rev:4;)


---

## Demonstration

### SQL Injection Attack

![SQL Injection](screenshots/dvwa-sqli-attack.png)

### ICMP Detection

![ICMP Detection](screenshots/snort-icmp-detection.png)

### SQL Detection

![SQL Detection](screenshots/snort-sql-detection.png)

---

## Learning Outcomes

• Built a simulated SOC monitoring environment  
• Created custom Snort IDS detection rules  
• Simulated web application attacks  
• Analyzed IDS alerts
