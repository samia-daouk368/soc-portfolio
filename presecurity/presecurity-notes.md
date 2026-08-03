# TryHackMe: Pre Security Path — Full Notes

Complete task-by-task notes covering all 7 modules and 31 rooms of the TryHackMe Pre Security learning path, paraphrased in my own words.

## Module 1: Introduction to Cyber Security

### Room 1: Offensive Security Intro
**Task 1 — Think like a Hacker!:** Introduces offensive security as thinking like an attacker to find weaknesses before real hackers do, contrasted with defensive security (keeping hackers out and responding when things go wrong). Uses a bank scenario to distinguish offensive actions (testing logins) from defensive actions (adding firewall rules).
**Task 2 — Starting the Lab:** Launches a simulated "FakeBank" web app in a virtual desktop split-screen to use for the rest of the room.
**Task 3 — Find Hidden Pages:** Introduces the `dirb` tool for discovering unlinked/hidden pages on a website by brute-forcing common words, e.g. `dirb http://example.com`, used here against `http://fakebank.thm`.
**Task 4 — Attack the Admin Page:** Shows that navigating directly to a discovered hidden path (`/bank-transfer`) exposes an admin panel that lets you deposit money into an account without authentication, demonstrating that hidden pages are not the same as secure pages.

### Room 2: Defensive Security Intro
**Task 1 — Introduction:** Introduces the Security Operations Centre (SOC) as the hub of defensive security work, working alongside a colleague "Cassidy."
**Task 2 — Phase 1: An Attack Begins:** Introduces SOC monitoring dashboards that surface alerts (e.g. a "Suspicious Login" alert) so analysts can see what's happening across the organisation in real time.
**Task 3 — Phase 2: Stopping the Attack:** Walks through disabling a compromised account (locking it via an "Account Management" page) to stop an in-progress attack quickly, since attackers change behaviour once they know they've been spotted.
**Task 4 — Phase 3: Investigating the Attacker:** Introduces threat intelligence — recording what a named attacker group did (targeted username/page) in a shared system so the organisation has an updated record of the threat.
**Task 5 — Phase 4: Submitting Your Report:** Introduces incident reports as a way to document what happened for future training purposes, generating a unique incident identifier as part of the exercise.

### Room 3: Careers in Cyber
**Task 1 — Introduction:** Frames cyber security careers as high-paying, in-demand, and varied, spanning offensive (pentesting) and defensive roles.
**Task 2 — Security Analyst:** Maintains an organisation's data security; analyses networks, compiles security reports, and develops security plans.
**Task 3 — Security Engineer:** Designs, monitors, and maintains security controls, networks, and systems to prevent attacks; tests software and mitigates vulnerabilities.
**Task 4 — Incident Responder:** Identifies and mitigates attacks while they are unfolding; tracked via metrics like MTTD/MTTA/MTTR (mean time to detect/acknowledge/recover).
**Task 5 — Digital Forensics Examiner:** Investigates incidents and crimes using digital evidence, following legal procedures, and documenting findings.
**Task 6 — Malware Analyst:** Reverse-engineers malicious programs to understand their behaviour, often working with low-level languages like assembly/C.
**Task 7 — Penetration Tester:** Ethically hacks systems, networks, and web apps to uncover vulnerabilities and report on real-world risk.
**Task 8 — Red Teamer:** Emulates a real adversary over an extended engagement to test an organisation's detection and response capabilities, distinct from the broader vulnerability focus of pentesting.
**Task 9 — Quiz:** A short recommendation/feedback task with no additional technical content.

## Module 2: Computer Fundamentals

### Room 4: Inside a Computer System
**Task 1 — Introduction:** Frames understanding computer components as a prerequisite to securing them ("you can't defend a castle you've never seen").
**Task 2 — Inside a Computer System:** Introduces core PC building blocks (CPU, RAM, storage, motherboard, etc.) using a human-body analogy, with a hands-on static site exercise.
**Task 3 — What Happens When You Press the Start Button?:** Walks through the boot process step by step: power on → UEFI/BIOS firmware starts → Power-On Self Test (POST) → boot device selection → bootloader loads the OS into RAM.
**Task 4 — Conclusion:** Recaps that understanding core components and the boot process matters because the boot process is sometimes targeted by attackers; transitions to the Computer Types room.

### Room 5: Computer Types
**Task 1 — Introduction:** Narrative framing (Sophia's internship) introducing that computers exist beyond laptops/phones — in fridges, doorbells, etc.
**Task 2 — Sophia's Summer of Hidden Computers – Month 1:** Distinguishes laptops (portable), desktops (fixed, sustained performance), workstations (precision components for professional work), and servers (headless, serve many users).
**Task 3 — Sophia's Summer of Hidden Computers – Month 2:** Distinguishes smartphones, tablets, IoT devices (network-connected, single purpose) and embedded computers (built into another device, may not connect to a network at all).
**Task 4 — Why Computers Come in Different Flavors:** Explains that computer design is always a trade-off — mobility costs power, reliability costs money — so there is no single "best" computer, only the right tool for the job.
**Task 5 — Summary:** Recaps the eight computer types covered and that the most important computers are often the invisible ones.

### Room 6: Client-Server Basics
**Task 1 — Introduction:** Introduces the client-server model as the basis of how interconnected systems (descended from ARPANET/CYCLADES/NPL/NSFNET) offer services to each other.
**Task 2 — Pizza Delivery:** Uses a pizza-ordering analogy to teach client/server/service, request/response, protocol (the agreed "language" and rules of communication), port (identifies a specific service on a server, like a specific door), and DNS (resolves a name to an address, like a GPS).
**Task 3 — Web Communication in Practice:** Introduces HTTP(S) as a stateless client-server protocol, the GET method, and shows a real GET request/response inspected via browser developer tools (Network tab), covering fields like scheme, host, filename, address, and status code (e.g. 200 OK).
**Task 4 — Conclusion:** Recaps the client-server model and HTTP example before moving on to virtualisation.

### Room 7: Virtualisation Basics
**Task 1 — Introduction:** Frames virtualisation as the solution to the inefficiency of "one server = one application."
**Task 2 — Virtualization Overview:** Explains the historical problem (high cost, low utilisation, slow deployment, hard to scale with one-app-per-server) and introduces the hypervisor as the "building manager" that lets multiple virtual machines (lab machines) safely share one physical server.
**Task 3 — Virtualization Components:** Covers Type 1 (bare-metal, e.g. production servers/data centers) vs Type 2 (hosted, e.g. VirtualBox/VMware for testing/labs) hypervisors, virtual machines as fully independent virtual computers, and containers as lightweight, kernel-sharing environments for a single app (commonly deployed via Docker).
**Task 4 — Managing Virtual Machines:** Hands-on exercise using a mock "Virtualization Manager" dashboard to diagnose an errored VM (Mail-SERVER), restart it, create a new VM with specified CPU/memory/disk, and review host hardware utilisation across several physical hosts.
**Task 5 — Conclusion:** Recaps key terms (virtualization, hypervisor, VM, container, container image, network ports) and benefits (cost savings, better resource usage, safe testing, faster deployment, flexibility, portability, scalability, centralized management).

### Room 8: Cloud Computing Fundamentals
**Task 1 — Introduction:** Frames cloud computing as the solution to running an application beyond a single computer/country (latency, capacity, uptime).
**Task 2 — Cloud Computing Overview:** Covers the evolution from physical servers to cloud; benefits (scalability, on-demand self-service, pay-per-use, security, high availability, global access); cloud deployment types (public, private, hybrid) and service models (IaaS, PaaS, SaaS); and major vendors (AWS, Azure, GCP, Alibaba Cloud, IBM Cloud, Oracle Cloud).
**Task 3 — Deploying a Cloud Instance:** Hands-on exercise in a mock AWS-like console: creates EC2 instances (application-interface on t3.micro, two m5.large study machines), picks a region, and reviews/optimises billing by stopping unused instances.
**Task 4 — Conclusion:** Recaps cloud terminology and benefits before moving into the Operating Systems Basics module.

## Module 3: Operating Systems Basics

### Room 9: Operating Systems: Introduction
**Task 1 — Introduction:** Frames the OS as the invisible layer tying hardware and applications together, using a "gifted old computer" scenario.
**Task 2 — The Invisible Manager:** Explains the OS as an air-traffic-control-style coordinator between hardware and apps; introduces kernel space (privileged, direct hardware access) vs user space (restricted, must make system calls); lists OS duties (process management, memory management, file system management, user management, device management) and baseline security roles (authentication, permissions, isolation, system protection); hands-on use of a System Monitor tool to inspect OS version and memory.
**Task 3 — OS Interaction and Landscape:** Contrasts GUI vs CLI interaction; surveys OS categories (desktop, server, mobile, embedded, virtual/cloud) and real-world families (Windows, macOS, Linux distros, Unix, Android, iOS, embedded Linux/RTOS, cloud/container-optimised OSes); hands-on exploration of file systems and a user's home directory.
**Task 4 — Conclusion:** Recaps kernel/user space, GUI/CLI, and previews the Windows Basics, Linux CLI Basics, and Windows CLI Basics rooms.

### Room 10: Windows Basics
**Task 1 — Introduction:** Sets up an onboarding-day scenario at a fictional company "TryHatMe" using Windows Server 2019.
**Task 2 — Exploring the Windows Workspace:** Covers login/authentication and account types (Guest, Standard, Administrator); tours the Desktop and Taskbar (Start menu, Search, Task View, pinned items, notifications); uses the "About your PC" settings page to find device name/RAM/Windows version; explores File Explorer and a shared onboarding folder for a flag.
**Task 3 — Configuring and Securing Windows:** Covers Windows Update, installing apps (Microsoft Store or downloaded installers), uninstalling apps, Windows Settings vs Control Panel, Task Manager (Processes/Performance/Users/Details/Services tabs), and Windows Security (Virus & threat protection, Firewall & network protection, App & browser control, Device security) plus Windows Defender Firewall network profiles (Domain/Private/Public); hands-on install of a test app and a custom antivirus scan that flags a safe EICAR test file.
**Task 4 — Conclusion:** Recaps Windows UI terms and security tools; previews Linux CLI Basics and Windows CLI Basics.

### Room 11: Linux CLI Basics
**Task 1 — Introduction:** Sets up a "first day as IT Support" storyline requiring terminal navigation.
**Task 2 — Navigation Mission: "Find the Missing Notes":** Teaches `pwd` (print working directory), `ls` / `ls -l` / `ls -al` (list contents, long format, include hidden dotfiles), `cd <dir>` and `cd ..` (navigate), `find ~ -name <filename>` (locate a file by name under home), and `cat <file>` (read file contents) — used together to locate and read `mission_brief.txt`.
**Task 3 — Investigating the System:** Teaches `whoami` (current user), `uname -a` (kernel/system info), `df -h` (human-readable disk usage), and reading `/etc/os-release` via `cat` to identify the Linux distribution; mini-challenge repeats the find+cd+cat pattern on `day1_report.txt`.
**Task 4 — Conclusion:** Recaps filesystem navigation, searching, and system-info gathering skills as building blocks for later permissions/users/processes topics.

### Room 12: Windows CLI Basics
**Task 1 — Introduction:** "Day 2 on the job" storyline moving from Linux CLI to Windows Command Prompt (CMD).
**Task 2 — Windows CLI: Navigating Files and Finding Your First File:** Teaches `cd` (show/change current directory), `dir` (list contents), `dir /a` (show hidden items), `dir /s <filename>` (recursively search for a file), and `type <file>` (read file contents) — used to locate and read `task_brief.txt`.
**Task 3 — Gathering System Information on Windows:** Teaches `whoami` (current user), `hostname` (computer name), `systeminfo` (OS name/version/system type), and `ipconfig` (IPv4 address, default gateway).
**Task 4 — Conclusion:** Recaps Windows CLI navigation and system/network info-gathering commands as core analyst skills.

### Room 13: Operating System Security
**Task 1 — Introduction to Operating System Security:** Defines hardware vs OS, surveys OS types (desktop/mobile/server/cross-platform like Linux), and frames security around the CIA triad (Confidentiality, Integrity, Availability).
**Task 2 — Common Examples of OS Security:** Covers weak/reused passwords (referencing the NCSC top-100k common password list), weak file permissions (violating least privilege, enabling confidentiality/integrity attacks), and malicious programs (Trojans compromising confidentiality/integrity; ransomware attacking availability by encrypting files for ransom).
**Task 3 — Practical Example of OS Security:** Hands-on attack using an AttackBox against a Linux lab machine: `ssh sammie@MACHINE_IP` with a weakly-guessed password (`dragon`), then `whoami`, `ls`, `cat <file>` to explore the account, then guessing a second user `johnny`'s password from a common-password list, using `history` to find a root password Johnny had mistakenly typed, and `su - root` to escalate and read a flag file — illustrating password guessing and privilege escalation end to end.

## Module 4: Software Basics

### Room 14: Data Representation
**Task 1 — Introduction:** Frames the room around how computers represent colors/numbers using only binary (0/1) versus the human decimal system.
**Task 2 — Representing Colors:** Explains RGB color representation: 3 on/off lights give 8 colors (3 bits); 256 levels per channel (8 bits each) give 16,777,216 colors (24 bits/3 bytes total); introduces hexadecimal digits as a compact way to represent groups of 4 bits (e.g. a color as `A3EA2A` instead of raw binary).
**Task 3 — Numbers: From Decimal to Hexadecimal:** Explains positional numbering (decimal, e.g. 213 = 2×10²+1×10¹+3×10⁰) and the same logic for binary (base-2) and hexadecimal (base-16, digits 0–F, where A–F represent 10–15), plus optional coverage of octal (base-8, groups of 3 bits).
**Task 4 — Conclusion:** Recaps decimal/binary/hex/octal systems and bit/byte/hex-color terminology; transitions to the Data Encoding room.

### Room 15: Data Encoding
**Task 1 — Introduction:** Distinguishes data representation (bits in memory) from encoding (the agreed mapping from numbers to meaning, e.g. characters).
**Task 2 — ASCII:** Introduces ASCII (American Standard Code for Information Interchange, 1963) as a 7-bit standard (0–127) mapping numbers to English letters/digits/punctuation, e.g. "TryHackMe" as a sequence of ASCII binary/hex codes; notes ISO-8859-1/2 extended ASCII variants for European languages and the display-corruption risk of mismatched encodings.
**Task 3 — Unicode:** Introduces Unicode as a universal standard assigning a unique code point to virtually every character/emoji across all languages (e.g. U+0041 for "A"), and explains UTF-8 (1–4 bytes, backward-compatible with ASCII), UTF-16 (2 or 4 bytes), and UTF-32 (always 4 bytes) as different ways of encoding those code points.
**Task 4 — Conclusion:** Recaps ASCII's limitations and Unicode/UTF-8/16/32 as the modern solution; transitions to the Python: Simple Demo room.

### Room 16: Python: Simple Demo
**Task 1 — Introduction:** Sets up building a "Guess the Number" Python game as the vehicle for learning variables, conditionals, and loops.
**Task 2 — Variables:** Introduces `import random`, `random.randint(1, 20)` to pick a secret number, plain variables (`secret`, `tries`, `guess`), and `print()` for output.
**Task 3 — Conditional Statements:** Introduces `input()` to read a guess, `int()` to convert it to a number, and `if` / `elif` / `else` to compare the guess against the secret and print "too low/too high/out of range/correct" feedback.
**Task 4 — Iterations:** Introduces the `while guess != secret:` loop so the player can keep guessing until correct, wrapping the earlier conditional logic inside it.
**Task 5 — Conclusion:** Recaps variables, conditionals (if/elif/else), and while-loops as the three pillars covered, encouraging comparison with the upcoming JavaScript version.

### Room 17: JavaScript: Simple Demo
**Task 1 — Introduction:** Sets up the same "Guess the Number" game concept, this time in JavaScript (run via Node.js), to compare language design directly against the Python version.
**Task 2 — Variables:** Introduces `let` for mutable variables (`tries`, `guess`), `const` for constants (`secret`, via `Math.floor(Math.random() * 20) + 1`), and `console.log()` for output.
**Task 3 — Prompting the User for Input:** Introduces `await rl.question("Take a guess: ")` for input and `parseInt(text, 10)` to convert it to a number.
**Task 4 — Conditional Statements:** Introduces `if` / `else if` / `else` (JavaScript's spelling of "else if") to give "too low/too high/out of range/correct" feedback based on comparing `guess` to `secret`.
**Task 5 — Iterations:** Introduces the `while (guess !== secret) { ... }` loop (`!==` meaning "not equal") to let the player keep guessing.
**Task 6 — Conclusion:** Recaps variables/constants, conditionals, and while-loops, and previews the Database SQL Basics room next.

### Room 18: Database SQL Basics
**Task 1 — Introduction:** Frames databases as the solution to a growing café's need to search/manage order data faster than a paper notebook allows.
**Task 2 — Understanding Tables, Rows, and Columns:** Explains that a database stores information in tables, where columns define the type of data and each row is one complete record (e.g. one café order); introduces SQL as the language used to query (ask questions of) this data without altering it.
**Task 3 — Writing Your First SQL Query:** Teaches `SELECT * FROM Orders;` (view everything), `SELECT drink, price FROM Orders;` (specific columns), `WHERE` (filter rows, e.g. `WHERE drink = 'Coffee'`), and `ORDER BY` / `ORDER BY ... DESC` (sort ascending/descending) using a café Orders/Menu database.
**Task 4 — Conclusion:** Recaps SELECT/FROM/WHERE/ORDER BY and poses a thought question about what could go wrong if anyone could freely modify or delete café order records (setting up future injection/access-control topics).

## Module 5: Network Fundamentals

### Room 19: What is Networking?
**Task 1 — What is Networking?:** Defines a network as things connected (analogous to friendship circles, city transit, power grids), applied to computing devices from laptops to traffic lights.
**Task 2 — What is the Internet?:** Explains the internet as many small (private) networks joined by public networks; briefly covers ARPANET (1960s) and Tim Berners-Lee's invention of the World Wide Web (1989).
**Task 3 — Identifying Devices on a Network:** Introduces IP addresses (four octets, can change, public vs private) and MAC addresses (12-character hex, burned in at the factory, spoofable); IPv4 (2^32 addresses) vs IPv6 (2^128 addresses); hands-on MAC spoofing lab to bypass a paywalled hotel Wi-Fi simulation.
**Task 4 — Ping (ICMP):** Introduces `ping` and ICMP echo request/reply for testing connectivity/latency, e.g. `ping 10.10.10.10`.
**Task 5 — Continue Your Learning: Intro to LAN:** Pointer task linking to the next room.

### Room 20: Intro to LAN
**Task 1 — Introducing LAN Topologies:** Covers star (central switch/hub, scalable but costly), bus (single backbone cable, cheap but bottleneck-prone with one point of failure), and ring (loop, easy to troubleshoot but one break breaks everything) topologies; defines switches (efficient, port-aware traffic forwarding) and routers (connect/route between networks).
**Task 2 — A Primer on Subnetting:** Defines subnetting as splitting a network into smaller pieces via a subnet mask (four octets/32 bits, each 0–255); covers network address (start of a subnet, e.g. 192.168.1.0), host address (identifies a device, e.g. 192.168.1.100), and default gateway (device that forwards traffic off-subnet, e.g. 192.168.1.254).
**Task 3 — ARP:** Explains ARP (Address Resolution Protocol) as mapping IP addresses to MAC addresses via ARP Request/ARP Reply broadcasts, cached locally for future use.
**Task 4 — DHCP:** Explains automatic IP assignment via the DORA sequence: DHCP Discover → DHCP Offer → DHCP Request → DHCP ACK.
**Task 5 — Continue Your Learning: OSI Model:** Pointer task to the next room.

### Room 21: OSI Model
**Task 1 — What is the OSI Model?:** Introduces the 7-layer OSI (Open Systems Interconnection) model as the framework for how networked devices send/receive/interpret data, and encapsulation as the process of adding info at each layer.
**Task 2 — Layer 1 (Physical):** Covers the physical hardware/cabling (e.g. ethernet cables) transmitting raw binary as electrical signals.
**Task 3 — Layer 2 (Data Link):** Covers MAC addressing via the Network Interface Card (NIC), physically identifying the receiving endpoint.
**Task 4 — Layer 3 (Network):** Covers routing/reassembly using IP addresses; mentions OSPF (Open Shortest Path First) and RIP (Routing Information Protocol) as path-selection protocols, and routers as "Layer 3 devices."
**Task 5 — Layer 4 (Transport):** Contrasts TCP (Transmission Control Protocol — reliable, connection-based, error-checked, slower; used for file transfer/browsing/email) with UDP (User Datagram Protocol — fast, connectionless, no guarantee; used for streaming/DNS/ARP/DHCP).
**Task 6 — Layer 5 (Session):** Covers establishing/maintaining/closing a unique connection ("session") between two devices, including checkpointing to save bandwidth after data loss.
**Task 7 — Layer 6 (Presentation):** Covers translating/standardising data formats between sender and receiver (e.g. different email clients), and notes encryption (like HTTPS) occurs at this layer.
**Task 8 — Layer 7 (Application):** Covers the user-facing layer — GUIs like browsers/email clients and protocols like DNS.
**Task 9 — Practical - OSI Game:** A drag/order "escape the dungeon" style game reinforcing the correct order of the 7 OSI layers, yielding a flag.
**Task 10 — Continue Your Learning: Packets & Frames:** Pointer task to the next room.

### Room 22: Packets & Frames
**Task 1 — What are Packets and Frames:** Distinguishes a packet (Layer 3, has IP addressing info) from a frame (Layer 2, encapsulates the packet with MAC addressing) using a letter/envelope analogy; lists common IP packet headers (Time to Live, Checksum, Source/Destination Address).
**Task 2 — TCP/IP (The Three-Way Handshake):** Covers the 4-layer TCP/IP model (Application, Transport, Internet, Network Interface); TCP headers (Source/Destination Port, Source/Destination IP, Sequence Number, Acknowledgement Number, Checksum, Data, Flag); and the SYN → SYN/ACK → ACK three-way handshake sequence (plus FIN to close and RST to abruptly terminate a connection).
**Task 3 — Practical - Handshake:** Drag-and-drop lab reordering a TCP handshake conversation between "Alice" and "Bob" to reveal a flag.
**Task 4 — UDP/IP:** Reinforces UDP as stateless/connectionless (no three-way handshake), simpler headers than TCP, and best suited to loss-tolerant traffic like streaming or voice chat.
**Task 5 — Ports 101 (Practical):** Explains ports (0–65535) as harbour-dock analogies for directing traffic to the right application; lists common ports (FTP 21, SSH 22, HTTP 80, HTTPS 443, SMB 445, RDP 3389); hands-on connecting to an IP on a specific port (8.8.8.8:1234) to retrieve a flag.
**Task 6 — Continue Your Learning: Extending Your Network:** Pointer task to the next room.

### Room 23: Extending Your Network
**Task 1 — Introduction to Port Forwarding:** Explains port forwarding (configured on a router) as opening a specific port so a service on a private network becomes reachable from the public internet, distinct from firewalls (which decide if traffic on open ports is allowed).
**Task 2 — Firewalls 101:** Explains firewalls as traffic border-control based on source/destination/port/protocol; contrasts stateful firewalls (inspect whole connections, more resource-intensive, smarter) with stateless firewalls (inspect individual packets against static rules, lighter, good against high-volume attacks like DDoS).
**Task 3 — Practical - Firewall:** Hands-on exercise configuring firewall rules to block malicious traffic on port 80 while allowing legitimate traffic to reach a web server, yielding a flag.
**Task 4 — VPN Basics:** Explains VPNs as encrypted tunnels connecting devices/networks over the internet as if on one private network; covers benefits (connecting remote offices, privacy on public Wi-Fi, anonymity) and technologies PPP (auth/encryption, non-routable), PPTP (easy but weak encryption), and IPSec (harder to set up, strong encryption).
**Task 5 — LAN Networking Devices:** Recaps routers (Layer 3, path selection) and switches (Layer 2 — MAC-based frame forwarding, or Layer 3 — can also route by IP); introduces VLANs (Virtual LANs) for segmenting departments on the same switch for security.
**Task 6 — Practical - Network Simulator:** Hands-on network simulator sending a TCP packet between two simulated computers, observing each hop/step (including handshake log entries) to reveal a flag.

## Module 6: How The Web Works

### Room 24: DNS in Detail
**Task 1 — What is DNS?:** Defines DNS (Domain Name System) as translating human-readable domain names into IP addresses (e.g. tryhackme.com → 104.26.10.229).
**Task 2 — Domain Hierarchy:** Explains TLDs (top-level domains, gTLD like .com/.org vs ccTLD like .co.uk/.ca), second-level domains (max 63 chars, a–z/0–9/hyphens), and subdomains (same rules, up to 253 chars total, unlimited number of subdomains).
**Task 3 — Record Types:** Covers A (IPv4), AAAA (IPv6), CNAME (alias to another domain), MX (mail server, with priority), and TXT (free text, e.g. SPF/DMARC/domain verification) DNS record types.
**Task 4 — Making A Request:** Walks through the DNS resolution chain: local cache → recursive DNS server (usually from your ISP) → root servers → TLD server → authoritative/nameserver for the domain, with results cached according to a TTL (Time To Live) value.
**Task 5 — Practical:** Hands-on DNS lookup tool used to find a CNAME, TXT record value, MX priority, and A record IP address for a practice domain.

### Room 25: HTTP in Detail
**Task 1 — What is HTTP(S)?:** Defines HTTP (HyperText Transfer Protocol) as the rule set for transferring web page data, and HTTPS as its encrypted, identity-verified counterpart.
**Task 2 — Requests And Responses:** Breaks down URL structure (scheme, user, host, port, path, query string, fragment) and walks through an example raw HTTP GET request/response, covering headers like Host/User-Agent/Referer and response fields like status code/Server/Date/Content-Type/Content-Length.
**Task 3 — HTTP Methods:** Covers GET (retrieve), POST (submit/create), PUT (update), and DELETE (remove) methods.
**Task 4 — HTTP Status Codes:** Covers the 5 status code ranges (1xx informational, 2xx success, 3xx redirection, 4xx client error, 5xx server error) and common codes (200 OK, 201 Created, 301/302 redirects, 400 Bad Request, 401 Not Authorised, 403 Forbidden, 404 Not Found, 405 Method Not Allowed, 500 Internal Server Error, 503 Service Unavailable).
**Task 5 — Headers:** Covers common request headers (Host, User-Agent, Content-Length, Accept-Encoding, Cookie) and response headers (Set-Cookie, Cache-Control, Content-Type, Content-Encoding).
**Task 6 — Cookies:** Explains cookies as small pieces of state saved via the `Set-Cookie` response header and sent back on every subsequent request, commonly used for authentication tokens; shows viewing cookies via browser dev tools' Network tab.
**Task 7 — Making Requests:** Hands-on HTTP request-builder emulator practicing GET (with query parameters), DELETE, PUT (with body parameters), and POST (login with username/password) requests.

### Room 26: How Websites Work
**Task 1 — How websites work:** Introduces the front end (client-side rendering in the browser) vs back end (server-side processing) split of a website.
**Task 2 — HTML:** Introduces HTML structure (`<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`, `<h1>`, `<p>` tags) and attributes (`class`, `src`, `id`); hands-on editing/fixing HTML in a live-render sandbox, including adding an `<img>` tag.
**Task 3 — JavaScript:** Shows JavaScript embedded via `<script>` tags or `src` attribute, using `document.getElementById("demo").innerHTML = "..."` to change page content, and `onclick` event handlers on elements like buttons.
**Task 4 — Sensitive Data Exposure:** Defines sensitive data exposure as a vulnerability where sensitive plaintext info (e.g. credentials left in comments) is left in front-end source code, exploitable by simply viewing page source.
**Task 5 — HTML Injection:** Defines HTML injection as a vulnerability where unsanitised user input is reflected into the page, letting an attacker submit their own HTML/JavaScript (e.g. injecting a malicious link) that the browser then renders as real page content.

### Room 27: Putting it all together
**Task 1 — Putting It All Together:** Summarises the full request lifecycle: DNS resolves the server's IP, HTTP is used to communicate with the server, and the server returns HTML/CSS/JS/images for the browser to render.
**Task 2 — Other Components:** Covers load balancers (distribute traffic across multiple servers using algorithms like round-robin or weighted, with health checks for failover), CDNs (host static files across many global servers for speed), databases (store/recall data, e.g. MySQL/MSSQL/MongoDB/Postgres), and WAFs (Web Application Firewalls — filter malicious requests and apply rate limiting).
**Task 3 — How Web Servers Work:** Covers web server software (Apache/Nginx/IIS/NodeJS) serving files from a root directory; virtual hosts (one server hosting multiple domains via hostname matching); static vs dynamic content; and backend/scripting languages (PHP/Python/Ruby/NodeJS/Perl) processing requests server-side, invisible to the client (e.g. a PHP `$_GET` example).
**Task 4 — Quiz:** Drag-and-drop ordering game reinforcing the full request lifecycle to reveal a flag.

## Module 7: Attacks and Defenses

### Room 28: The CIA Triad
**Task 1 — Introduction:** Frames cyber security as protecting three core aspects of digital data, building on all previous modules.
**Task 2 — Understanding the CIA Triad:** Defines Confidentiality (only authorized people can access data, e.g. protecting against credential interception on public Wi-Fi), Integrity (data isn't modified without authorization, e.g. protecting a bank transfer from tampering), and Availability (data/services are accessible when needed, e.g. surviving a flood of requests without going down); works through real-world "was it achieved?" examples for each pillar.
**Task 3 — The Security Mindset:** Frames CIA as a professional mindset for assessing incidents ("was data exposed / modified / made unavailable?"); hands-on drag-and-drop exercise classifying nine security incidents against the correct CIA pillar to reveal a flag.
**Task 4 — Conclusion:** Recaps Confidentiality/Integrity/Availability definitions; transitions to Cryptography Concepts.

### Room 29: Cryptography Concepts
**Task 1 — Introduction:** Poses the question of what actually protects data as it travels the internet, introducing cryptography as the practical tool for confidentiality/integrity.
**Task 2 — Hiding Information - Symmetric Encryption:** Defines plaintext, ciphertext, key, and algorithm; uses a lockbox analogy and the Caesar cipher (shift-by-N, e.g. key of 3: HELLO → KHOOR) to teach symmetric encryption (one shared key encrypts and decrypts); notes the key distribution problem (how do two parties safely share that one key?); hands-on "Secret Message Rescue" Caesar cipher game.
**Task 3 — Sharing Keys Safely: Asymmetric Encryption:** Introduces asymmetric encryption's two linked keys — a public key (shareable, like a mail slot) and a private key (secret, like the mailbox's lock) — solving the key distribution problem; explains how HTTPS uses a hybrid approach (asymmetric encryption to agree a shared symmetric key, then fast symmetric encryption for the actual session) and how certificates/Certificate Authorities let a browser trust a public key belongs to the real website.
**Task 4 — Conclusion:** Recaps plaintext/ciphertext/key/algorithm and symmetric vs asymmetric encryption, and previews Become a Hacker / Become a Defender.

### Room 30: Become a Hacker
**Task 1 — What Is Offensive Security?:** Frames offensive security/penetration testing as ethically, legally testing systems from an attacker's perspective to find weaknesses before real attackers do.
**Task 2 — Finding Weaknesses:** Defines red teaming, penetration test, vulnerability, exploit, and scope; hands-on discovery of a hidden `/admin`-style page on a mock "onlineshop.thm" site both manually and via `gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt`.
**Task 3 — Exploiting Weaknesses:** Covers the "chained weaknesses" mindset (small flaws combine into bigger impact) and defender-mindset-in-reverse principles (ask "what if", test the unexpected, chain small weaknesses, think like an adversary); hands-on manual password guessing against an `admin` login, then automated with `hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V` (a dictionary attack) to find the working password and log in.
**Task 4 — Where to Go From Here:** Recaps terminology (scope, vulnerability, exploit, enumeration, credentials, authentication, dictionary attack) and lists offensive career paths (Penetration Tester/Ethical Hacker, Vulnerability Researcher, Red Team Operator).

### Room 31: Become a Defender
**Task 1 — What Is Defensive Security?:** Frames defensive security (the "Blue Team") as understanding what to protect and implementing prevention/detection/mitigation aligned with the CIA triad, building on the attacker mindset from Become a Hacker.
**Task 2 — Understanding Your Environment:** Uses a "city" analogy to map client infrastructure (employee devices=homes, web server=shop, mail server=post office, firewall=city gate, internet=outside the city) and defines the 5 defender activities: Prevention, Detection, Mitigation, Analysis, and Response and Improvement; hands-on infrastructure-mapping exercise for a flag.
**Task 3 — Defending Your Environment:** Introduces defender principles (threat anticipation, attack awareness, risk prioritization, continuous adaptation) and layered defenses per component (antivirus/patching for employee devices, safe-traffic/HTTPS for web servers, spam filters/attachment scanning for mail servers, firewall rules for the gate, restricting/monitoring inbound traffic from the internet); hands-on "defend the city" exercise for a flag.
**Task 4 — Where to Go From Here:** Recaps terminology (Blue Team, client infrastructure, visibility, threat, prevention, detection, mitigation, risk) and lists defensive career paths (SOC, Threat Intelligence, DFIR) — marks the completion of the full Pre Security path.

---
*Notes compiled from the TryHackMe "Pre Security" learning path (31 rooms, 7 modules) in my own words as a personal study reference, covering every task within every room.*
