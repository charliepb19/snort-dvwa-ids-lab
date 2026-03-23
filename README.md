# Snort IDS Lab – DVWA Attack Detection

## Overview

This project demonstrates a simulated Intrusion Detection System (IDS) environment using **Snort** to monitor network traffic and detect malicious activity targeting a vulnerable web application (**DVWA**).

The lab simulates a real-world network where an attacker performs reconnaissance and exploitation while Snort monitors the traffic and generates alerts.

## Lab Architecture

The environment consists of three virtual machines:

- **Kali Linux** – Attacker machine
- **Ubuntu Router** – Runs Snort IDS and inspects network traffic
- **Ubuntu Web Server** – Hosts the DVWA vulnerable web application

Traffic flow:

`Kali Attacker → Snort Router → DVWA Web Server`

## Technologies Used

- Snort IDS
- Kali Linux
- Ubuntu Server
- DVWA (Damn Vulnerable Web Application)
- VirtualBox

## Custom Snort Detection Rules

### ICMP Reconnaissance Detection

Detects ping scans targeting the protected network.

```snort
alert icmp any any -> $HOME_NET any (msg:"ICMP Ping Detected"; sid:1000001; rev:2;)
SQL Injection Detection

Detects SQL injection attempts against the DVWA web server.

alert tcp any any -> $HOME_NET 80 (msg:"SQL Injection Attempt"; content:"OR"; sid:1000002; rev:4;)
Demonstration
Lab Architecture

SQL Injection Attack on DVWA

Snort Detecting ICMP Reconnaissance

Network Configuration
Kali Attacker

Router

Web Server

Learning Outcomes

Through this project, I:

Built a simulated SOC monitoring environment
Configured custom Snort intrusion detection rules
Simulated network reconnaissance and web application attacks
Analyzed IDS alerts generated from malicious traffic
Practiced network segmentation and traffic inspection
Future Improvements

Potential enhancements to this lab include:

Detecting Nmap scans
Implementing brute-force detection rules
Logging alerts for SIEM integration
Expanding detection to include additional web attack signatures
