# MITM Attack Analysis Report

## Introduction
A Man-in-the-Middle (MITM) attack occurs when an attacker secretly intercepts communication between two systems without their knowledge.

---

## Attack Simulation
The attack was simulated in a controlled VMware environment using Kali Linux as the attacker and Ubuntu as the victim.

ARP spoofing was used to position the attacker between the victim and the gateway.

---

## Observations

### 1. Network Traffic Interception
Using Wireshark, the following were observed:
- DNS requests exposed visited domains
- HTTP traffic was visible in plaintext
- Packet flow was redirected through attacker machine

### 2. ARP Table Manipulation
The victim machine's ARP table was modified, associating the attacker's MAC address with the gateway IP.

---

## Security Implications
- Sensitive data can be exposed on unencrypted networks
- Attackers can perform session hijacking
- Users are vulnerable on public Wi-Fi networks

---

## Conclusion
MITM attacks are highly effective on unencrypted protocols. Proper encryption and secure network configuration are essential to prevent such attacks.
