# TryHackMe: Pre Security Path — Full Notes

Complete notes covering all 7 modules and 31 rooms of the TryHackMe Pre Security learning path, summarized in my own words.

## Module 1: Introduction to Cyber Security

### Offensive Security Intro
Offensive security is the practice of thinking like an attacker to find weaknesses before real adversaries do. Covers the basic mindset of penetration testing: reconnaissance, scanning, exploitation, and reporting. Introduces the idea of "scope" — testers only attack systems they have written permission to test. First hands-on task walks through exploiting a simple web application to retrieve a flag, showing how a single overlooked input field can lead to full compromise.

### Defensive Security Intro
Defensive security focuses on preventing, detecting, and responding to attacks rather than causing them. Introduces core blue-team functions: Security Operations Centre (SOC) analysts monitoring alerts, threat intelligence teams tracking attacker behaviour, and digital forensics/incident response (DFIR) teams investigating breaches after the fact. Explains the layered "defense in depth" approach and how logging/monitoring tools (SIEMs) feed alerts to analysts.

### Careers in Cyber
Surveys the many career paths in the industry: penetration tester, SOC analyst, incident responder, malware analyst, security engineer, GRC (governance, risk, compliance) analyst, and security researcher among others. Distinguishes red team (offensive), blue team (defensive), and purple team (collaborative) roles. Emphasizes that a cyber career doesn't require a single fixed background — many entrants come from IT, software, or non-technical fields, and certifications/labs help build practical skills alongside formal education.

## Module 2: Computer Fundamentals

### Inside a Computer System
Breaks down the core hardware components: the CPU (executes instructions), RAM (temporary working memory), storage (HDD/SSD for persistent data), and motherboard (connects everything). Explains the fetch-decode-execute cycle at a high level and how the operating system sits between hardware and user applications to manage resources.

### Computer Types
Covers the range of computing devices: desktops, laptops, servers, mobile devices, and embedded/IoT systems. Discusses how servers differ from desktops in that they are optimized for uptime, remote management, and serving many simultaneous clients rather than a single user's interactive workload.

### Client-Server Basics
Introduces the client-server model where clients (browsers, apps) send requests and servers respond with data or services. Walks through a hands-on example of a simple web server responding to browser requests, illustrating request/response flow and the role of ports in directing traffic to the correct service on a host.

### Virtualisation Basics
Explains virtual machines (VMs) as software-emulated computers running on a hypervisor (Type 1 bare-metal vs Type 2 hosted), allowing multiple isolated operating systems to run on one physical machine. Covers benefits for security testing: snapshotting, isolation, and disposability, which is why most TryHackMe labs run inside VMs.

### Cloud Computing Fundamentals
Introduces cloud service models — IaaS, PaaS, and SaaS — and deployment models (public, private, hybrid). Covers the shared responsibility model, where the cloud provider secures the underlying infrastructure while the customer is responsible for securing what they configure and deploy on top of it.

## Module 3: Operating Systems Basics

### Operating Systems: Introduction
Defines an OS as the software layer that manages hardware resources and provides a consistent interface for applications. Covers the main functions: process management, memory management, file systems, and device drivers, and briefly compares the major OS families (Windows, Linux, macOS).

### Windows Basics
Tours the Windows desktop environment: File Explorer, Control Panel/Settings, Task Manager, and the registry as a central configuration database. Introduces user account types (administrator vs standard) and where system logs and key directories live.

### Linux CLI Basics
Hands-on introduction to the Linux terminal and core commands such as ls, cd, pwd, cat, mkdir, cp, mv, rm, and man for reading documentation. Covers the Linux filesystem hierarchy (root /, home directories, /etc for configuration) and basic permission concepts (read/write/execute for user/group/other).

### Windows CLI Basics
Introduces the Windows Command Prompt and equivalent commands to Linux, such as dir, cd, copy, move, del, and type. Covers navigating the Windows directory structure and running basic diagnostic commands like ipconfig and systeminfo.

### Operating System Security
Covers baseline OS hardening concepts: keeping systems patched/updated, disabling unnecessary services, enforcing least privilege for accounts, and using host-based firewalls and antivirus/EDR tools. Explains why a hardened, minimal system has a smaller attack surface than a default install.

## Module 4: Software Basics

### Data Representation
Explains how computers represent data in binary, and how binary maps to hexadecimal and decimal number systems. Covers bits/bytes, and how text is represented using character encodings.

### Data Encoding
Covers common encoding schemes such as ASCII, Unicode/UTF-8, Base64, and URL encoding. Distinguishes encoding (reversible representation, not secrecy) from encryption (confidentiality), a distinction that matters when analyzing captured traffic or obfuscated data.

### Python: Simple Demo
A gentle hands-on introduction to Python syntax: variables, print statements, basic input/output, and simple conditional logic. Shows how a short script can automate a repetitive task, motivating scripting as a useful skill for both offense and defense.

### JavaScript: Simple Demo
Introduces JavaScript as the language that makes web pages interactive, running in the browser. Covers basic syntax, DOM manipulation, and how JavaScript executing client-side can be inspected/modified via browser developer tools — relevant background for later web-based attack concepts.

### Database SQL Basics
Introduces relational databases, tables, rows/columns, and basic SQL statements (SELECT, INSERT, UPDATE, WHERE clauses). Provides the groundwork for later understanding how improperly sanitized SQL queries can be abused by attackers.

## Module 5: Network Fundamentals

### What is Networking?
Defines a network as a collection of connected devices that share information, introducing IP addresses as unique identifiers for devices and the general concept of routing packets between networks.

### Intro to LAN
Covers Local Area Networks, switches vs hubs, MAC addresses, and private IP addressing (e.g., 192.168.x.x ranges). Introduces the ARP protocol for resolving IP addresses to MAC addresses on a local segment.

### OSI Model
Walks through all seven OSI layers (Physical, Data Link, Network, Transport, Session, Presentation, Application) and gives an example protocol/device at each layer, building a mental model for how data is encapsulated as it moves down the stack and decapsulated as it moves up on the receiving end.

### Packets & Frames
Explains encapsulation in practice: how application data becomes a segment (Transport layer, TCP/UDP headers), then a packet (Network layer, IP headers), then a frame (Data Link layer, MAC headers) before transmission. Introduces basic packet capture concepts for inspecting this traffic.

### Extending Your Network
Covers devices that connect and extend networks beyond a single LAN: routers, switches, access points, and repeaters. Introduces NAT (Network Address Translation) for sharing a single public IP across many private devices, and basic firewall placement at network boundaries.

## Module 6: How The Web Works

### DNS in Detail
Explains DNS as the system that translates human-readable domain names into IP addresses. Covers the record types (A, AAAA, CNAME, MX, TXT, NS) and the resolution hierarchy from root servers to TLD servers to authoritative name servers.

### HTTP in Detail
Covers the HTTP request/response cycle, common methods (GET, POST, PUT, DELETE), status code ranges (2xx success, 3xx redirect, 4xx client error, 5xx server error), and important headers (Host, User-Agent, Cookie, Content-Type). Also introduces HTTPS and the role of TLS in encrypting HTTP traffic.

### How Websites Work
Ties together DNS, HTTP, and client-server concepts to explain the full lifecycle of loading a webpage: DNS resolution, TCP/TLS handshake, HTTP request, server processing (often involving a backend and database), and the browser rendering the returned HTML/CSS/JavaScript.

### Putting it all together
A capstone room that reinforces the full request lifecycle learned across the networking and web modules, tracing a single user action (like submitting a login form) through DNS, TCP, HTTP, and back, to see how every earlier concept fits into one real-world flow.

## Module 7: Attacks and Defenses

### The CIA Triad
Introduces Confidentiality (preventing unauthorized disclosure), Integrity (preventing unauthorized modification), and Availability (ensuring systems/data remain accessible) as the three foundational goals security controls aim to protect, and gives examples of attacks that violate each.

### Cryptography Concepts
Covers the difference between symmetric encryption (single shared key, fast) and asymmetric encryption (public/private key pairs, used for key exchange and digital signatures), plus hashing as a one-way function used for integrity checks and password storage.

### Become a Hacker
A practical capstone walking through a simple offensive workflow — reconnaissance, identifying a vulnerability, and exploiting it to capture a flag — tying together the offensive mindset introduced in Module 1 with the technical foundations built throughout the path.

### Become a Defender
A practical capstone from the defender's perspective — reviewing logs/alerts, identifying signs of malicious activity, and taking response actions — reinforcing the detection-and-response mindset introduced in Module 1's defensive security overview.

---
*Notes compiled from the TryHackMe "Pre Security" learning path (31 rooms, 7 modules) in my own words as a personal study reference.*
