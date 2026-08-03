# Pre Security Cheat Sheet

Quick reference companion to presecurity-notes.md. Organized by module.

## Module 1: Introduction to Cyber Security
• Offensive security — thinking like an attacker to find weaknesses first (pentesting, red teaming)
• Defensive security — preventing, detecting, responding (SOC, threat intel, DFIR)
• `dirb http://example.com` — brute-force discovery of hidden web pages/directories
• Career roles: Security Analyst, Security Engineer, Incident Responder, Digital Forensics Examiner, Malware Analyst, Penetration Tester, Red Teamer
• MTTD / MTTA / MTTR — mean time to detect / acknowledge / recover from an incident

## Module 2: Computer Fundamentals
• Core components: CPU, RAM, storage, motherboard
• Boot sequence: Power On → UEFI/BIOS firmware → POST (Power-On Self Test) → Select Boot Device → Bootloader loads OS into RAM
• Computer types: laptop, desktop, workstation, server, smartphone, tablet, IoT device, embedded computer
• Client-server model: client initiates request, server responds; port identifies a specific service; DNS resolves a name to an IP
• Hypervisor Type 1 (bare-metal, e.g. production/data centers) vs Type 2 (hosted, e.g. VirtualBox/VMware — labs/testing)
• VM = full virtual computer; Container = lightweight, shares host kernel, runs via Docker
• Cloud service models: IaaS (rent infrastructure) / PaaS (managed platform) / SaaS (full software, e.g. Gmail)
• Cloud deployment types: Public / Private / Hybrid
• Cloud vendors: AWS (EC2), Azure, GCP, Alibaba Cloud, IBM Cloud, Oracle Cloud

## Module 3: Operating Systems Basics
• Kernel space (privileged, direct hardware access) vs User space (restricted, uses system calls)
• OS duties: Process management, Memory management, File system management, User management, Device management
• OS categories: Desktop, Server, Mobile, Embedded, Virtual/Cloud

### Linux CLI Commands
• `pwd` — print working directory
• `ls` / `ls -l` / `ls -al` — list files (long format, incl. hidden)
• `cd <dir>` / `cd ..` — change directory / go up one level
• `cat <file>` — print file contents
• `find ~ -name <filename>` — search for a file by name under home directory
• `whoami` — current username
• `uname -a` — kernel/system info
• `df -h` — human-readable disk usage
• `cat /etc/os-release` — identify Linux distribution
• `history` — view command history (used to find leaked passwords)
• `ssh user@host` — remote login
• `su - <user>` — switch user (privilege escalation)
• `man <command>` — manual page
• `chmod` / `chown` — change permissions / ownership

### Windows CLI Commands
• `cd` — show/change current directory
• `dir` — list directory contents
• `dir /a` — show hidden files/folders
• `dir /s <filename>` — recursively search for a file
• `type <file>` — print file contents
• `whoami` — current username
• `hostname` — computer name
• `systeminfo` — OS name/version/system type
• `ipconfig` — IPv4 address, default gateway
• `tasklist` — list running processes

### OS Security
• CIA Triad basis: Confidentiality, Integrity, Availability
• Weak/reused passwords, weak file permissions, and malicious programs (Trojans, ransomware) are common OS security weaknesses
• Least privilege — give users/files only the access they need

## Module 4: Software Basics
• Bit = single binary digit (0/1); Byte = 8 bits (aka octet)
• RGB color: 3 on/off lights = 8 colors; 256 levels/channel (8 bits each) = 16,777,216 colors (24-bit/3-byte color)
• Hex digit = 4 bits (0-9, A-F for 10-15); used to compactly represent binary (e.g. color codes like `A3EA2A`)
• Number systems: Decimal (base-10), Binary (base-2), Hexadecimal (base-16), Octal (base-8, groups of 3 bits)
• ASCII — 7-bit standard (0-127) for English text; extended/regional variants: ISO-8859-1 (Western Europe), ISO-8859-2 (Central/Eastern Europe)
• Unicode — universal standard, unique code point per character/emoji across all languages (e.g. U+0041 = "A")
• UTF-8 (1-4 bytes, ASCII-compatible) / UTF-16 (2 or 4 bytes) / UTF-32 (always 4 bytes)
• Encoding ≠ Encryption: encoding is a reversible representation (not secret); encryption is for confidentiality (needs a key)

### Python Basics
• `import random` / `random.randint(1, 20)` — random integer
• `input()` — read user input (returns text/string)
• `int()` — convert text to integer
• `print()` — display output
• `if` / `elif` / `else` — conditional branching
• `while <condition>:` — loop while condition is true

### JavaScript Basics
• `let` — declare a mutable variable
• `const` — declare a constant
• `console.log()` — display output
• `Math.random()` / `Math.floor()` — generate/round random numbers
• `await rl.question("prompt")` — read user input (Node.js)
• `parseInt(text, 10)` — convert text to integer (base 10)
• `if` / `else if` / `else` — conditional branching
• `while (<condition>) { }` — loop; `!==` means "not equal"

### SQL Basics
• `SELECT * FROM table;` — view all columns/rows
• `SELECT col1, col2 FROM table;` — view specific columns
• `WHERE <condition>` — filter rows, e.g. `WHERE drink = 'Coffee'`
• `ORDER BY column [DESC]` — sort ascending (default) or descending
• Table = spreadsheet of data; Column = data type/field; Row = one full record

## Module 5: Network Fundamentals
• IP address — logical address (4 octets, e.g. 192.168.1.100); public (internet-facing) vs private (LAN-facing)
• MAC address — physical hardware address (12-char hex), burned in, spoofable
• IPv4 = 2^32 addresses (~4.3 billion); IPv6 = 2^128 addresses
• `ping <ip/host>` — uses ICMP echo request/reply to test connectivity/latency
• LAN topologies: Star (central switch, scalable, costly), Bus (single backbone cable, cheap, one point of failure), Ring (loop, easy to troubleshoot, one break = full outage)
• Subnetting — splitting a network via a subnet mask (4 octets/32 bits); Network address (start of subnet), Host address (a device), Default Gateway (off-subnet router, e.g. .1 or .254)
• ARP (Address Resolution Protocol) — maps IP ↔ MAC via ARP Request/Reply, cached locally
• DHCP handshake (DORA): Discover → Offer → Request → ACK

### OSI Model (Layer 7 down to 1)
• Application — HTTP, DNS, browsers/email clients
• Presentation — data translation/formatting, encryption (e.g. HTTPS)
• Session — establishes/maintains/closes a connection ("session")
• Transport — TCP (reliable) / UDP (fast, unreliable); ports
• Network — IP addressing, routing (OSPF, RIP); routers = "Layer 3 devices"
• Data Link — MAC addressing via NIC; frames
• Physical — cables, raw electrical signals, binary

### TCP vs UDP
• TCP: connection-based, reliable, error-checked, slower — used for file transfer, browsing, email
• UDP: connectionless, no guarantee, faster — used for streaming, voice chat, DNS/ARP/DHCP
• TCP Three-Way Handshake: SYN → SYN/ACK → ACK (also FIN to close cleanly, RST to abruptly terminate)
• TCP/IP 4-layer model: Application, Transport, Internet, Network Interface

### Common Ports
• FTP — 21
• SSH — 22
• HTTP — 80
• HTTPS — 443
• SMB — 445
• RDP — 3389
• Ports range 0–65535; ports 0–1024 are "common/well-known" ports

### Extending Networks
• Port forwarding — opens a specific port on a router so an internal service becomes internet-reachable (configured at the router)
• Firewall — Stateful (inspects whole connections, smarter, resource-heavy) vs Stateless (inspects individual packets, static rules, good vs DDoS)
• VPN technologies: PPP (auth/encryption, non-routable), PPTP (easy, weak encryption), IPSec (harder to configure, strong encryption)
• VLAN — segments departments/devices on the same switch for security
• Switches: Layer 2 (MAC-based frame forwarding) or Layer 3 (can also route by IP)

## Module 6: How The Web Works

### DNS
• DNS translates domain names to IP addresses
• Record types: A (IPv4), AAAA (IPv6), CNAME (alias), MX (mail server + priority), TXT (free text, e.g. SPF/DMARC)
• Resolution chain: local cache → recursive DNS server (ISP) → root servers → TLD server → authoritative nameserver
• TTL (Time To Live) — how long a DNS record is cached
• TLD (.com, .org) — gTLD (generic) vs ccTLD (country code, e.g. .co.uk)

### HTTP
• Methods: GET (retrieve), POST (submit/create), PUT (update), DELETE (remove)
• Status code ranges: 1xx info, 2xx success, 3xx redirect, 4xx client error, 5xx server error
• Common codes: 200 OK, 201 Created, 301/302 Redirect, 400 Bad Request, 401 Not Authorised, 403 Forbidden, 404 Not Found, 405 Method Not Allowed, 500 Internal Server Error, 503 Service Unavailable
• Request headers: Host, User-Agent, Content-Length, Accept-Encoding, Cookie
• Response headers: Set-Cookie, Cache-Control, Content-Type, Content-Encoding
• Cookies — small state saved via `Set-Cookie`, sent back on every request (commonly used for auth tokens)
• URL structure: scheme, user, host, port, path, query string, fragment

### Web/App Basics
• HTML — page structure (`<html>`, `<head>`, `<body>`, `<h1>`, `<p>`, attributes like `class`/`src`/`id`)
• JavaScript — page interactivity (`document.getElementById().innerHTML`, `onclick` events)
• Sensitive Data Exposure — secrets left in front-end source code/comments, viewable via "View Page Source"
• HTML Injection — unsanitized user input rendered as real HTML/JS by the browser
• Load Balancer — distributes traffic (round-robin/weighted), performs health checks
• CDN — hosts static files across global servers for speed
• WAF (Web Application Firewall) — filters malicious requests, applies rate limiting
• Virtual Hosts — one server hosting multiple domains via hostname matching
• Static content (never changes) vs Dynamic content (changes per request, generated server-side)

## Module 7: Attacks and Defenses

### The CIA Triad
• Confidentiality — only authorized people can access data
• Integrity — data is not modified without authorization
• Availability — data/services are accessible when needed

### Cryptography
• Plaintext (readable) → Ciphertext (scrambled) via Algorithm (public method) + Key (secret)
• Symmetric encryption — one key encrypts AND decrypts (e.g. Caesar cipher, AES); fast but has the "key distribution problem"
• Caesar cipher — shifts each letter by a fixed key number (e.g. key 3: HELLO → KHOOR)
• Asymmetric encryption — public key (shareable) + private key (secret, linked pair); solves key distribution (e.g. RSA)
• HTTPS hybrid approach — asymmetric encryption agrees a shared symmetric key, then fast symmetric encryption handles the session
• Certificate / Certificate Authority (CA) — verifies a public key truly belongs to a given website/domain

### Offensive Security Terms (Become a Hacker)
• Red Teaming — authorized simulated adversary attack to test defenses
• Penetration Test — authorized assessment to find/exploit vulnerabilities within a defined scope
• Vulnerability — a weakness that could be exploited
• Exploit — a technique that takes advantage of a vulnerability
• Scope — what is/isn't allowed to be tested
• Enumeration — collecting details about a system/users/services
• Dictionary attack — trying a wordlist of passwords/usernames
• `gobuster dir --url <target> -w <wordlist>` — automated hidden directory/file discovery
• `hydra -l <user> -P <passlist> <target> http-post-form "/login:username=^USER^&password=^PASS^:F=<fail_string>" -V` — automated login brute-force (dictionary attack)

### Defensive Security Terms (Become a Defender)
• Blue Team — defenders who protect systems and respond to threats
• Prevention — stopping threats before they happen (patching, antivirus, firewalls)
• Detection — identifying suspicious activity via logs/alerts/monitoring
• Mitigation — limiting damage during an incident (isolating systems, blocking traffic, disabling accounts)
• Analysis — investigating logs/evidence to understand what happened
• Response and Improvement — recovering and strengthening defenses afterward
• Defender principles: threat anticipation, attack awareness, risk prioritization, continuous adaptation
• Career paths: SOC (Security Operations Center), Threat Intelligence, DFIR (Digital Forensics & Incident Response)
