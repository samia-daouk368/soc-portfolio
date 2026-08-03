# MyFirstHack — Foundations Track, Days 1-25 Notes

Notes from the MyFirstHack 90-day Foundations program (Phase 1: Understanding
the Digital World, Days 1-20; Phase 1.2: How Networks Actually Work, Days 21-25+).

## Day 1: The Cybersecurity Landscape
Intro framing: cybersecurity = protecting computers, networks, data and people
from digital attacks. Hands-on: checked personal email exposure using
HaveIBeenPwned to see which past breaches it appeared in.

## Day 2: Why Most Beginners Fail (And How You Won't)
Covers the common reasons learners quit a self-paced course (overwhelm,
tutorial hell, boredom, life getting in the way) and the fix: consistency
over intensity. Task: block a recurring daily study slot on a calendar.

## Day 3: Your First Security Audit
Introduced a five-step personal audit methodology: Scope, Intelligence,
Exposure, Severity, Remediation. Task: scope key accounts/devices/network,
then produce a personal security audit report with findings ranked by
severity and a remediation plan.

## Day 4: How Computers Actually Work
Covered hardware, running processes, the file system, and background network
activity, with the point that sensitive data (passwords, keys) lives in RAM
while a machine runs. Task: inspect running processes and research
unfamiliar ones to build endpoint triage instincts.

## Day 5: How the Internet Works
Walked through the roughly seven stops a request makes (DNS lookup, TCP
handshake, TLS negotiation, HTTP request, server response, render) between
typing a URL and a page loading. Task: use browser DevTools' Network tab to
see every domain a single page actually loads from.

## Day 6: IP Addresses
Explained public vs private IP addresses and what a public IP reveals about
a user (rough location, ISP, connection type). Task: look up your own public
IP and compare results across lookup services.

## Day 7: DNS (Week 1 wrap-up)
First real look at DNS as the system translating domain names into IP
addresses, plus a Week 1 reflection checkpoint. Task: run DNS lookups
against the default resolver and explicit public resolvers, and compare
results.

## Day 8: Passwords
History of password complexity rules (traced to a widely cited 2003 NIST
guideline later disavowed by its own author) and why length + uniqueness +
MFA matter far more than complexity rules. Covered credential stuffing as an
attack pattern. Task: install a password manager and save a first account
in it.

## Day 9: Phishing
Used the 2016 Podesta email compromise as a case study; phishing is
implicated in a large majority of successful breaches per major industry
reports. Framed phishing as exploiting three psychological levers: urgency,
authority, curiosity. Task: find a real phishing email in inbox/spam and
examine sender domain, real link destination (via hover), and which
psychological lever it used.

## Day 10: Data
Introduced three categories of valuable data that attackers target and
defenders protect: PII, Credentials, and Proprietary data. Reframed the
entire field around one question: what data lives here, and why would
someone want it? Task: map personal data footprint across the three
categories, aiming for 15-20 services.

## Day 11: The Web
Distinguished "the internet" (moves data) from "the web" (pages + browsers
rendering that data), and looked at how many third-party scripts/trackers a
typical page loads. Task: View Page Source on a familiar site and count
script tags and recognizable tracker/analytics domains.

## Day 12: HTTPS
Clarified what the browser padlock actually proves (the channel is
encrypted) versus what it doesn't (that the site is legitimate or safe).
Covered Certificate Authorities and certificate lifetimes. Task: inspect a
real TLS certificate on a trusted site (issuer, validity window).

## Day 13: Cookies
Explained cookies as the mechanism sites use to remember identity between
page loads, and why a stolen session cookie can bypass MFA entirely since
authentication already happened when the cookie was issued. Task: inspect a
site's cookies via DevTools (Application/Storage tab), noting session cookie
name and its Secure/HttpOnly/SameSite flags.

## Day 14: Wi-Fi
Framed the home router as three things at once: network gateway, security
boundary, and a piece of software that's often years out of date. Task: run
a full router audit — admin password (default or changed), Wi-Fi encryption
mode (WPA3/WPA2/WEP/Open), firmware age, guest network status, remote
management setting, and connected device list.

## Day 15: Phishing Email Analysis (Portfolio Milestone)
First capstone project combining Days 11-14: a full technical write-up of a
real phishing email in SOC-analyst report format — header analysis
(SPF/DKIM/DMARC), sender domain analysis (registration age, typosquatting),
content indicators, link/landing-page analysis, verdict with confidence and
severity, and recommended actions.

## Day 16: Mobile Devices
Covered how the mobile threat model differs from desktop (different
permissions model, patch cycle, and attack surface), and smishing as an SMS
analogue of phishing. Task: six-point phone audit — OS version vs latest,
app permissions review, lock screen strength, 2FA method (SMS vs
authenticator app vs hardware key) on key accounts, unused app cleanup, and
Find My/Find My Device status.

## Day 17: The Cloud
Reframed "the cloud" plainly as rented hardware in someone else's data
center, and used the 2019 Capital One breach as the canonical example of a
cloud breach caused by the customer's own misconfiguration (WAF, IAM role)
rather than a flaw in the cloud platform itself. Task: inventory every cloud
service you depend on and its MFA status.

## Day 18: How Attacks Actually Work
Introduced the Cyber Kill Chain (Reconnaissance, Weaponization, Delivery,
Exploitation, Installation, Command & Control, Actions on Objectives) and
the MITRE ATT&CK framework as the industry-standard way to describe attacker
behavior. Task: map a real recent breach to the seven kill-chain stages and
identify at least two matching MITRE ATT&CK technique IDs.

## Day 19: Social Engineering
Used the 2023 MGM Resorts breach (Scattered Spider's help-desk pretext call)
to show how a single social engineering call caused roughly $100 million in
losses without any malware or exploit. Introduced Cialdini's persuasion
principles (authority, urgency, scarcity, reciprocity, social proof, liking).
Task: OSINT yourself, then write a plausible pretext attack against yourself
and identify which psychological triggers it relies on.

## Day 20: Build Your Threat Model (Portfolio Milestone — end of Phase 1.1)
Capstone project consolidating Days 1-19 into a formal personal threat model:
asset inventory ranked by tier (critical/important/minor), adversary types
(opportunistic, targeted criminal, personal, larger actors), specific threat
scenarios rated by likelihood and impact, current mitigations vs a 90-day
action plan, and an explicit "out of scope" section.

## Day 21: Networks Are Just Conversations (Start of Networks track)
Opens the second 25-day track (How Networks Actually Work) by defining a
network simply as any two devices having a conversation, requiring a sender,
receiver, common language, and route. Task: inventory every device on your
home network via the router's admin panel.

## Day 22: IP Addresses (Networks track, deeper pass)
Revisited IP addressing in more technical depth: IPv4 structure (32-bit,
dotted-decimal, network+host parts), private vs public ranges, and NAT as
the workaround that has kept IPv4 alive decades past its expected
exhaustion. Task: find both your private and public IP addresses using
OS-level commands and compare multiple public IP lookup tools.

## Day 23: Ports
Explained how a port number lets a single IP address run many simultaneous
network conversations, covered well-known port ranges, and used Shodan to
show how many exposed services (e.g. RDP on port 3389) are discoverable on
the public internet. Task: use netstat/ss to list your machine's active
connections and listening ports.

## Day 24: DNS (Networks track, deeper pass)
Went deeper into DNS mechanics: the recursive resolver chain (root → TLD →
authoritative server) and DNS record types (A, MX, NS, TXT, AAAA). Used the
2018 MyEtherWallet BGP-hijack-plus-DNS incident as a case study of a layered
DNS attack. Task: query multiple DNS resolvers and record types for the same
domain and compare results.

## Day 25: TCP vs UDP (Portfolio Milestone)
Contrasted TCP (reliable, ordered, handshake-based — used for web, email,
banking) with UDP (fast, connectionless, no retransmission — used for DNS,
voice, video, gaming). Task: installed Wireshark, ran a first packet
capture, and filtered traffic by protocol (tcp / udp / dns) to see the real
protocol mix on a live machine.
