#  Man-in-the-Middle (MITM) Attack Simulation Lab

##  Project Overview
This project demonstrates a simulated Man-in-the-Middle (MITM) attack in a controlled virtual lab environment. The goal is to understand how attackers can intercept network traffic and analyze vulnerabilities in unsecured communication.

>  This experiment was conducted in a safe, isolated virtual environment for educational purposes only.

---

##  Objectives
- Simulate a MITM attack in a controlled network
- Capture and analyze network traffic using Wireshark
- Understand how ARP spoofing enables interception
- Identify risks in unencrypted communication

---

##  Tools Used
- Kali Linux (Attacker Machine)
- Ubuntu (Victim Machine)
- VMware Workstation
- Wireshark (Packet Analysis)
- arpspoof / Ettercap (MITM Tool)

---

##  Lab Setup
- Both machines connected to **VMware NAT (VMnet8)**
- Same subnet used (192.168.228.x)
- Kali acts as attacker
- Ubuntu acts as victim

---

## Methodology

### 1. Network Discovery
Identified active hosts and gateway using:
ip a
ip route


### 2. IP Forwarding Enabled (Kali)
echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward


### 3. ARP Spoofing Attack
arpspoof -i eth0 -t <victim-ip> <router-ip>
arpspoof -i eth0 -t <router-ip> <victim-ip>


### 4. Traffic Capture
Captured packets using Wireshark on interface `eth0`.

Filters used:
http
dns
arp

---

##  Findings

- DNS queries were visible in plaintext
- HTTP traffic was intercepted successfully
- ARP tables were manipulated during spoofing
- MAC address associations changed during attack

---

##  Security Risks Identified
- Plain HTTP traffic is vulnerable to interception
- ARP protocol lacks authentication
- Attackers can intercept sensitive data on local networks

---

##  Mitigation Techniques
- Use HTTPS encryption
- Implement ARP spoofing detection tools
- Use VPNs on untrusted networks
- Enable dynamic ARP inspection on routers

---

##  Evidence
Screenshots and packet capture files are included in the repository:

- Wireshark capture interface
- ARP spoofing terminal
- DNS traffic capture
- HTTP packet inspection

---

##  Files Included
/screenshots

capture.png
arp-spoof.png
dns-traffic.png

/logs

capture.pcap

analysis-report.md
README.md


---

##  Conclusion
This lab demonstrates how MITM attacks can compromise network communication in unsecured environments and highlights the importance of encryption and network security controls.
