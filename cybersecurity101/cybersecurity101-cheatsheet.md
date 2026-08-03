# Cyber Security 101 Cheat Sheet (Modules 1-3)

Quick reference companion to cybersecurity101-notes.md. Organized by module.

## Module 1: Introduction to Cyber Security

• Offensive security = attacker mindset, finding weaknesses first; Defensive security = prevent/detect/respond to attacks

• dirb http://target.com — brute-force discovery of hidden web pages/directories

• SOC (Security Operations Centre) — team that monitors dashboards/alerts and responds to live attacks

• Threat intelligence — recording attacker info (group name, targeted accounts/pages) for future defense and sharing

• Incident report — written summary of an attack and the response taken, used for record-keeping and training

• Shodan — internet-wide scanner for exposed devices/services; filters include country:, port:, org:, hostname:

• VirusTotal — checks files/URLs/hashes against 70+ antivirus engines for a malicious verdict

• CVE-YEAR-NUMBER — unique vulnerability identifier; CVSS — vulnerability severity/risk score

• man <command> — view Linux manual pages; ExploitDB / GitHub — sources for PoC exploit code (verify before running, not all PoCs are trustworthy)

## Module 2: Linux Fundamentals

• echo "text" — print text; whoami — show current user

• ls / ls -a — list directory contents (including hidden files); cd — change directory; cat — output file contents; pwd — print working directory

• find -name file.txt / find -name "*.txt" — search for files by exact name or wildcard

• grep "value" file — search file contents; grep -R "value" /path/ — recursive search through subdirectories

• & — run a command in the background; && — chain commands (2nd only runs if 1st succeeds)

• > — redirect output to a file (overwrite); >> — redirect output to a file (append)

• ssh user@ip — remote login over an encrypted connection; man <cmd> or <cmd> --help — view a command's usage/options

• touch file — create empty file; mkdir dir — create folder; cp src dst — copy; mv src dst — move/rename; rm -R dir — remove (recursively for folders); file <name> — identify file type

• Permissions rwx (read/write/execute) apply per owner/group/others; numeric notation: r=4 w=2 x=1, e.g. rwxr-xr-x = 755, rw-r--r-- = 644; su -l user — switch user (inherits their environment)

• /etc — system configuration files; /var — logs and variable data; /root — root user's home folder; /tmp — volatile temporary storage (cleared on reboot)

• nano file — simple terminal text editor; vim — advanced, highly customisable editor

• wget <url> — download a file over HTTP; scp source user@ip:dest — securely copy files over SSH; python3 -m http.server — quickly serve files from the current directory

• ps aux / top — view running processes; kill <PID> — terminate a process (signals: SIGTERM clean kill, SIGKILL forced kill, SIGSTOP suspend); systemctl start/stop/enable/disable/status <service> — manage services

• Ctrl+Z or & — send a process to the background; fg — bring a backgrounded process to the foreground

• crontab -e — edit scheduled jobs; format: MIN HOUR DOM MON DOW CMD (use * as a wildcard for any value)

• apt install/remove <package> — install or remove software; GPG keys — verify a repository's software is trusted before adding it

• /var/log — central directory for service and OS logs, e.g. Apache access/error logs, fail2ban, UFW firewall logs

## Module 3: Windows and AD Fundamentals

• NTFS — modern Windows journaling file system (vs older FAT/HPFS); supports folder/file permissions, compression, encryption (EFS), and Alternate Data Streams

• %windir% — environment variable pointing to the Windows folder; C:\Windows\System32 — critical OS files, handle with care

• Administrator vs Standard User account types; profiles stored under C:\Users; lusrmgr.msc — manage local users/groups

• UAC (User Account Control) — prompts for approval before elevated-privilege actions run

• msconfig — boot/services/startup troubleshooting utility; Advanced System Settings — page file size and crash dump (Startup and Recovery) configuration

• compmgmt.msc (Computer Management) — Task Scheduler, Event Viewer, Shared Folders, Local Users and Groups, Performance Monitor (perfmon), Device Manager, Disk Management, Services

• msinfo32 — System Information tool (hardware/software/environment variables); resmon — Resource Monitor (real-time CPU/memory/disk/network per process)

• hostname / whoami / ipconfig / ipconfig /all / netstat / net help <cmd> — key Command Prompt utilities

• regedit — Windows Registry Editor; WF.msc — Windows Defender Firewall console

• Windows Update — monthly "Patch Tuesday" release cycle; updates can be postponed but not skipped indefinitely

• Windows Security app areas: Virus & threat protection, Firewall & network protection, App & browser control, Device security (green/yellow/red status)

• Firewall profiles: Domain (domain-joined networks), Private (home/trusted networks), Public (untrusted networks like public Wi-Fi)

• Microsoft Defender SmartScreen — blocks phishing/malware sites and unrecognised downloaded files

• Core Isolation / Memory Integrity — protects high-security processes from malicious code injection; TPM (Trusted Platform Module) — hardware chip for cryptographic security functions

• BitLocker — full drive encryption, strongest when paired with a TPM; VSS (Volume Shadow Copy Service) — snapshots/restore points (a common ransomware deletion target)

• Active Directory (AD) — centralised domain user/computer management; Domain Controller (DC) — server running AD services

• AD objects: Users, Machines (account name ends in $), Security Groups; default groups include Domain Admins, Server Operators, Backup Operators, Account Operators, Domain Users/Computers/Controllers

• OU (Organizational Unit) — container for applying Group Policy to a set of users/computers (one OU per object at a time); Security Group — grants resource permissions (an object can belong to many groups)

• GPO (Group Policy Object) — policy settings linked to OUs; SYSVOL — network share used to distribute GPOs; gpupdate /force — immediately force a policy refresh

• Kerberos — default modern ticket-based authentication (TGT from the KDC, then a TGS per service); NetNTLM — legacy challenge-response authentication protocol

• Tree — domains sharing one namespace; Forest — multiple trees with different namespaces; Enterprise Admins — admin group with rights across the whole forest; Trust relationship (one-way or two-way) — allows users to access resources across domains
