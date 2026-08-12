# Cyber Security 101 Cheat Sheet (Modules 1-4)

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

## Module 4: Command Line

• cmd.exe — default Windows command-line interpreter; append /? to almost any command to display its help page

• set — show environment variables and the Path; ver — OS version; systeminfo — OS, host, processor and memory details; help — command help; cls — clear the screen

• command | more — page long output (Spacebar = next page, CTRL+C = quit); more file.txt — display a text file

• ipconfig / ipconfig /all — IP, subnet mask and gateway / plus physical (MAC) address, DHCP status, lease times and DNS servers

• ping host — ICMP reachability test with round-trip times; tracert host — trace the routers on the path to a target; nslookup domain [nameserver] — resolve a domain

• netstat — active connections and listening ports; netstat -abon — all (-a), owning program (-b), PID (-o), numeric (-n)

• cd / cd target / cd .. — show, enter, or move up a directory; dir / dir /a / dir /s — list contents, include hidden and system files, recurse; tree — visual folder structure

• mkdir, rmdir — create/remove directories; type — display a file; copy, move, del or erase — file operations; * — wildcard for multiple files (e.g. copy *.md C:\Markdown)

• tasklist / tasklist /FI "imagename eq sshd.exe" — list processes with an optional filter; taskkill /PID 4567 — terminate a process by PID

• chkdsk — check file systems and volumes for errors; driverquery — list installed device drivers; sfc /scannow — scan and repair system files

• PowerShell — object-oriented shell, scripting language and configuration framework built on .NET; objects carry properties (data) and methods (actions), so output never needs text parsing

• Cmdlets use a Verb-Noun naming convention, e.g. Get-Content, Set-Location, New-Item

• Get-Command — list all available cmdlets/functions/aliases/scripts (filter with -CommandType "Function" or -Verb Remove); Get-Help cmdlet -examples — usage examples; Get-Alias — legacy command shortcuts (dir, cd, cat, echo)

• Find-Module -Name "PowerShell*" / Install-Module -Name "PowerShellGet" — search and install modules from the PowerShell Gallery

• Get-ChildItem (dir/ls), Set-Location (cd), New-Item -ItemType File|Directory, Remove-Item, Copy-Item, Move-Item, Get-Content (type/cat) — file and folder cmdlets

• Pipe | passes objects, not text; Sort-Object Length — sort by a property; Where-Object -Property Extension -eq ".txt" — filter; Select-Object Name,Length — pick properties; Select-String -Path file -Pattern text — search inside files (grep/findstr, regex supported)

• Comparison operators: -eq (equal), -ne (not equal), -gt / -ge (greater than / or equal), -lt / -le (less than / or equal), -like (wildcard match)

• Get-ComputerInfo — full OS/hardware/BIOS snapshot (richer than systeminfo); Get-LocalUser — local accounts with status and description

• Get-NetIPConfiguration — interfaces, IP, gateway, DNS; Get-NetIPAddress — every configured address, including inactive ones

• Get-Process — running processes with CPU/memory; Get-Service — service status (spot anomalous services); Get-NetTCPConnection — active TCP connections, OwningProcess = the process behind the connection

• Get-FileHash -Path file — file hash for integrity checks and malware triage; Get-Item -Path file -Stream * — list Alternate Data Streams (:$DATA is the normal NTFS stream, anything else is an ADS)

• Invoke-Command -ComputerName Host -ScriptBlock { Get-Service } — run commands remotely; -FilePath script.ps1 — run a local script on a remote host

• Shell — the facilitator between the user and the OS; Bash is the default shell on most Linux distributions

• pwd, cd, ls, cat, grep "word" file — core Linux shell commands; history — list previously executed commands of the session

• echo $SHELL — current shell; cat /etc/shells — installed shells; type a shell's name to switch for the session; chsh -s /usr/bin/zsh — change the default shell permanently

• Bash (Bourne Again Shell) — widely used, best scripting compatibility, tab completion, history file; no syntax highlighting or spell correction

• Fish (Friendly Interactive Shell) — most user-friendly, simple syntax, auto spell correction, built-in syntax highlighting, themes; limited scripting

• Zsh (Z Shell) — advanced tab completion, auto spell correction, strong scripting, deep customisation via oh-my-zsh and plugins (syntax highlighting available); slower

• #!/bin/bash — shebang declaring the interpreter; .sh — script file extension; # — comment

• read var / $var — take and reference user input; for i in {1..10}; do ... done — loop; if [ ... ]; then ... elif ... else ... fi — conditional; && — require multiple conditions

• chmod +x script.sh — grant execute permission; ./script.sh — run a script from the current directory (it is not in PATH); sudo su — become root
