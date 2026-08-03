# MyFirstHack — Days 1-25 Cheat Sheet

Quick reference of tools, commands, and keywords from the first 25 days of
the MyFirstHack Foundations program.

## Tools & Sites Used
- HaveIBeenPwned (haveibeenpwned.com) — breach exposure lookup (Day 1)
- Bitwarden (bitwarden.com) — password manager (Day 8)
- VirusTotal, URLScan.io, PhishTank — phishing/URL analysis (Day 9, 15)
- ipinfo.io, whatismyipaddress.com, whatismyip.com — public IP lookups (Day 6, 22)
- MITRE ATT&CK (attack.mitre.org) — attacker technique framework (Day 18)
- Shodan (shodan.io) — internet-exposed device/service search (Day 23)
- dnsdumpster — domain DNS footprint tool (Day 24)
- Wireshark — packet capture and analysis (Day 25)

## Commands by Day

Day 4 — Process inspection
- Mac: Activity Monitor (Cmd+Space)
- Windows: Task Manager (Ctrl+Shift+Esc)
- Linux: htop / top

Day 5 — See page requests
- Browser DevTools: F12 (Win/Linux) or Cmd+Option+I (Mac) -> Network tab

Day 7 — Basic DNS lookups
- nslookup google.com
- nslookup google.com 8.8.8.8
- nslookup google.com 1.1.1.1

Day 11 — View page source
- Ctrl+U (Windows/Linux) / Cmd+Option+U (Mac)

Day 12 — Certificate inspection
- Click padlock in browser address bar -> Certificate viewer

Day 13 — Cookie inspection
- DevTools -> Application tab (Chrome/Edge) or Storage tab (Firefox) -> Cookies

Day 14 — Router admin audit
- http://192.168.0.1 or http://192.168.1.1 (router admin login)

Day 21 — Find your default gateway/router IP
- Mac: netstat -rn
- Windows: ipconfig
- Linux: ip route show default

Day 22 — Find your own IP addresses
- Mac: ifconfig
- Windows: ipconfig
- Linux: ip addr show
- Public IP: ipinfo.io/what-is-my-ip

Day 23 — List active connections and open ports
- Mac/Windows: netstat -an
- Linux: ss -tunap

Day 24 — DNS queries against specific resolvers and record types
- dig wikipedia.org
- dig @1.1.1.1 wikipedia.org
- dig @8.8.8.8 wikipedia.org
- dig wikipedia.org MX
- dig wikipedia.org NS
- dig wikipedia.org TXT
- dig wikipedia.org AAAA
- nslookup -type=MX wikipedia.org (Windows equivalent)

Day 25 — Packet capture
- Install Wireshark, select active interface, start/stop capture
- Filter bar: tcp / udp / dns

## Core Keywords & Concepts by Theme

Identity & Access: PII, Credentials, MFA/2FA, credential stuffing,
password manager, passphrase

Email & Social Attacks: phishing, smishing, spear-phishing, social
engineering, pretexting, Cialdini principles (authority, urgency, scarcity,
reciprocity, social proof, liking)

Web & Transport Security: HTTPS, TLS/SSL, Certificate Authority (CA),
padlock icon, cookies, session cookie, Secure/HttpOnly/SameSite flags

Networking Core: IP address (public/private), NAT, DNS, port, TCP, UDP,
three-way handshake, DNS record types (A, MX, NS, TXT, AAAA), recursive
resolver, root/TLD/authoritative servers

Email Authentication: SPF, DKIM, DMARC

Attacker Frameworks: Cyber Kill Chain (Reconnaissance, Weaponization,
Delivery, Exploitation, Installation, Command & Control, Actions on
Objectives), MITRE ATT&CK technique IDs

Cloud & Infrastructure: cloud = rented data-center hardware, IAM role,
WAF (Web Application Firewall), misconfiguration risk

Wi-Fi & Devices: WPA3/WPA2/WEP, router firmware, guest network, remote
management, Find My/Find My Device

## Portfolio Milestone Days
- Day 3: Personal Security Audit Report
- Day 15: Phishing Email Analysis Report
- Day 20: Personal Threat Model
- Day 25: TCP vs UDP / first Wireshark capture
