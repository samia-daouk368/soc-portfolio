# Pre Security Cheat Sheet

Quick reference companion to presecurity-notes.md.

## Linux CLI Commands
- pwd — print working directory
- ls / ls -la — list files (all, long format)
- cd <dir> — change directory
- cat <file> — print file contents
- mkdir / rm / cp / mv — create, remove, copy, move
- man <command> — manual page for a command
- chmod / chown — change permissions / ownership

## Windows CLI Commands
- dir — list directory contents
- cd — change directory
- copy / move / del — copy, move, delete files
- type <file> — print file contents
- ipconfig — show network configuration
- systeminfo — show system details
- tasklist — list running processes

## Networking Basics
- IP address — unique identifier for a device on a network
- MAC address — hardware address of a network interface
- ARP — resolves IP address to MAC address on a LAN
- NAT — translates private IPs to a shared public IP
- Router — connects and routes between networks
- Switch — connects devices within a LAN
- Firewall — filters traffic based on rules

## OSI Model (top to bottom)
1. Application — HTTP, FTP, DNS
2. Presentation — encryption, encoding
3. Session — session establishment/management
4. Transport — TCP/UDP, ports
5. Network — IP, routing
6. Data Link — MAC addresses, switches
7. Physical — cables, signals

## Encapsulation
Data → Segment (Transport) → Packet (Network) → Frame (Data Link) → Bits (Physical)

## DNS Record Types
- A — domain to IPv4 address
- AAAA — domain to IPv6 address
- CNAME — alias to another domain
- MX — mail server
- TXT — arbitrary text (verification, SPF)
- NS — authoritative name server

## HTTP Methods
- GET — retrieve data
- POST — submit data
- PUT — update/replace resource
- DELETE — remove resource

## HTTP Status Codes
- 2xx — success
- 3xx — redirect
- 4xx — client error (e.g. 404 Not Found)
- 5xx — server error

## Common HTTP Headers
- Host — target domain
- User-Agent — client software info
- Cookie — session/state data
- Content-Type — format of the body

## Data Encoding vs Encryption
- Encoding (Base64, URL, Hex) — reversible representation, NOT secret
- Encryption (AES, RSA) — designed for confidentiality, needs a key

## Cryptography
- Symmetric encryption — one shared key, fast (e.g. AES)
- Asymmetric encryption — public/private key pair (e.g. RSA)
- Hashing — one-way function for integrity/password storage (e.g. SHA-256)

## The CIA Triad
- Confidentiality — prevent unauthorized disclosure of data
- Integrity — prevent unauthorized modification of data
- Availability — keep systems and data accessible when needed

## Virtualisation & Cloud
- Hypervisor — software that runs virtual machines (Type 1 bare-metal, Type 2 hosted)
- IaaS / PaaS / SaaS — infrastructure / platform / software as a service
- Shared responsibility model — provider secures infrastructure, customer secures what they configure

## Security Roles & Terms
- Red team — offensive, simulates attackers
- Blue team — defensive, monitors and responds
- Purple team — collaboration between red and blue
- SOC analyst — monitors alerts and investigates incidents
- DFIR — digital forensics and incident response
- Scope — the systems/assets a tester is authorized to test
- Defense in depth — layered security controls

## Quick Definitions
- Vulnerability — a weakness that could be exploited
- Exploit — a method that takes advantage of a vulnerability
- Patch — an update that fixes a vulnerability
- Least privilege — giving users only the access they need
