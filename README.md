<link rel="stylesheet" href="style.css">

# pfSense Network Security Simulation Project

## Overview
This project demonstrates the setup of a secure virtual network using **pfSense** and **Snort** to simulate and analyze attacks from a Kali Linux machine. The objective was to configure a firewall and intrusion detection system (IDS) to monitor and log potential threats, thereby providing insights into network security practices.

## Project Objectives
- Configure a virtualized environment with **pfSense**, **Snort**, and **Kali Linux**.
- Simulate a cyberattack using tools from Kali Linux.
- Monitor and analyze attack logs using Snort on pfSense.
- Strengthen understanding of intrusion detection and prevention in a networked environment.

## Environment Setup
This project was implemented using **Oracle VirtualBox**. The network included:

1. **pfSense Firewall and IDS**
   - Acts as the firewall and intrusion detection system for the network.
   - Configured with Snort for monitoring and alerting.
2. **Kali Linux Attacker Machine**
   - Used to simulate various attacks against the pfSense system.

### Network Configuration
- **pfSense WAN (NAT):** Provides internet access to pfSense.
- **pfSense LAN (Internal Network):** Connects to the attacker machine.
- **Static IP Assignments:**
  - pfSense LAN: `192.168.1.1`
  - Kali Linux Attacker: `192.168.1.200`

## Setup Instructions

### 1. pfSense Installation
Created a Virtual Machine for pfSense in VirtualBox.
Configured two network adapters:
   - **Adapter 1 (NAT)**: Provides internet access.
   - **Adapter 2 (Internal Network)**: Connects to the local network.
<div align="center">
  <img src="https://i.imgur.com/jsT2j3g.png" alt="Internal Network Setup" width="600">
</div>

Installed and configured pfSense:
   - Assigned WAN to Adapter 1 and LAN to Adapter 2.
   - Set the LAN static IP to `192.168.1.1`.
<div align="center">
  <img src="https://i.imgur.com/yDTOdlh.png" alt="Configured IP" width="600">
</div>

### 2. Kali Linux Attacker Machine Setup
1. Installed Kali Linux on a VirtualBox VM.
2. Configured a single network adapter as **Internal Network**.
3. Set the static IP to `192.168.1.200` and the gateway to `192.168.1.1`.

### 3. Snort Configuration
1. Installed Snort on pfSense via the Package Manager.
2. Enabled Snort on the LAN interface with default rule sets.
3. Configured logging and alerts for detected threats.
<div align="center">
  <img src="https://i.imgur.com/9kKqpcm.png" alt="Snort Interface" width="600">
</div>

## Attack Simulation
### Reconnaissance
- Conducted an `nmap` scan from Kali Linux to identify open ports and services on the pfSense system:

   `nmap -A -Pn 192.168.1.1`
 
<div align="center">
  <img src="https://i.imgur.com/IhQTRTL.png" alt="Kali Nmap Scan" width="600">
</div>

## Results and Analysis
- **Snort Alerts:**
  - Detected and logged malicious activities originating from Kali Linux.
  - Alerts displayed details such as source IP, destination IP, and type of attack.
- **pfSense Logs:**
  - Provided additional insight into network traffic and firewall activity.
<div align="center">
  <img src="https://i.imgur.com/xHETTDJ.png" alt="Snort Alert" width="600">
</div>

## Skills Demonstrated
- Setting up and configuring a secure virtual network.
- Deploying and managing pfSense as a firewall and IDS.
- Using Snort for real-time network monitoring and threat detection.
- Conducting ethical hacking techniques for network analysis.
- Analyzing logs to identify and respond to security threats.

## Tools and Technologies
- **VirtualBox**: Virtualization platform.
- **pfSense**: Open-source firewall and router.
- **Snort**: Intrusion detection system.
- **Kali Linux**: Penetration testing platform.

## Conclusion
This project showcased the process of designing and securing a virtualized network environment. By leveraging pfSense and Snort, it was possible to detect and log malicious activity, reinforcing the importance of proactive monitoring and defense mechanisms in network security.

---


