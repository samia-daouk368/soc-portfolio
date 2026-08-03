# Cyber Security 101 — Modules 1-3 Notes

Task-by-task notes covering Modules 1-3 of the TryHackMe Cyber Security 101 path: Introduction to Cyber Security, Linux Fundamentals, and Windows and AD Fundamentals. Content is paraphrased in my own words from the hands-on rooms.

## Module 1: Introduction to Cyber Security

### Room 1: Offensive Security Intro
**Task 1 – Think like a Hacker!:** Contrasts offensive security (thinking like an attacker to find weaknesses first, e.g. testing weak logins) with defensive security (blocking/responding to attacks, e.g. adding firewall rules), using two bank employees as an example.
**Task 2 – Starting the Lab:** Deploys a simulated "FakeBank" web app in a virtual desktop to serve as the practical target for the rest of the room.
**Task 3 – Find Hidden Pages:** Introduces the dirb tool for brute-forcing unlinked/hidden website directories using common wordlists, run against the FakeBank site.
**Task 4 – Attack the Admin Page:** Shows that a hidden admin panel found via dirb (/bank-transfer) allows unauthenticated money transfers, demonstrating that hidden pages are not the same as secured pages.

### Room 2: Defensive Security Intro
**Task 1 – Introduction:** Frames the room around joining FakeBank's Security Operations Centre (SOC) to investigate a live attack.
**Task 2 – Phase 1: An Attack Begins:** Introduces a security monitoring dashboard and shows how reviewing a suspicious login alert reveals the targeted username.
**Task 3 – Phase 2: Stopping the Attack:** Covers incident containment by locking the targeted user account before the attacker can succeed.
**Task 4 – Phase 3: Investigating the Attacker:** Introduces threat intelligence — logging what the "ShadowFigures" attacker group attempted so the information can be shared and referenced later.
**Task 5 – Phase 4: Submitting Your Report:** Covers writing an incident report summarizing the attack and response, used for record-keeping and training.

### Room 3: Search Skills
**Task 1 – Introduction:** Sets up the goal of learning to search effectively for security information online using specialised tools and docs.
**Task 2 – Shodan (TryScanMe):** Introduces Shodan as an internet-wide scanner for exposed devices/services, with filters such as country, port, org, and hostname for narrowing results.
**Task 3 – VirusTotal (TryDetectMe):** Introduces VirusTotal, which checks submitted files, URLs, or hashes against dozens of antivirus engines to gauge whether something is malicious.
**Task 4 – Vulnerability Databases (CVE):** Explains the CVE identifier system (CVE-YEAR-NUMBER) for uniquely referencing vulnerabilities, and the CVSS scoring system used to prioritise risk.
**Task 5 – Technical Documentation (MAN):** Covers using Linux manual pages (man) to find official, reliable documentation and usage examples for command-line tools.
**Task 6 – GitHub:** Discusses using GitHub to find proof-of-concept exploit code and vulnerability write-ups tied to a CVE, with a caution that not all public PoCs are safe or reliable to run.

## Module 2: Linux Fundamentals

### Room 1: Linux Fundamentals Part 1
**Task 1 – Introduction:** Overview of what the three-part Linux Fundamentals series will cover.
**Task 2 – A Bit of Background on Linux:** Explains how widespread Linux is and introduces distribution "flavours" such as Ubuntu and Debian.
**Task 3 – Interacting With Your First Linux Machine (In-Browser):** Deploys an in-browser Ubuntu machine to practice on.
**Task 4 – Running Your First Few Commands:** Introduces echo (print text back to the terminal) and whoami (show the currently logged-in user).
**Task 5 – Interacting With the Filesystem!:** Covers ls (list contents), cd (change directory), cat (output file contents), and pwd (print working directory).
**Task 6 – Searching for Files:** Introduces find for locating files by name or wildcard, and grep for searching file contents, including recursive search with -R.
**Task 7 – An Introduction to Shell Operators:** Covers the &, &&, >, and >> operators for backgrounding commands, chaining commands, and redirecting output (overwrite vs append).
**Task 8 – Conclusions & Summaries:** Recaps the commands and concepts covered in the room.
**Task 9 – Linux Fundamentals Part 2:** Transition task linking to the next room and instructing the learner to terminate their machine.

### Room 2: Linux Fundamentals Part 2
**Task 1 – Introduction:** Overview of Part 2's goals: remote login, deeper filesystem commands, and permissions.
**Task 2 – Accessing Your Linux Machine Using SSH (Deploy):** Introduces SSH as an encrypted remote-login protocol and has the learner deploy an AttackBox plus a target machine, connecting with ssh user@ip.
**Task 3 – Introduction to Flags and Switches:** Covers command flags/arguments (e.g. ls -a to show hidden files) and using --help or man pages to learn a command's available options.
**Task 4 – Filesystem Interaction Continued:** Introduces touch (create file), mkdir (create folder), cp (copy), mv (move/rename), rm (remove, with -R for folders), and file (identify file type).
**Task 5 – Permissions 101:** Covers the read/write/execute permission model for owner/group/others, converting symbolic permissions to numeric form (e.g. rwxr-xr-x = 755), and switching users with su.
**Task 6 – Common Directories:** Explains key root directories: /etc (system configuration), /var (logs and variable data), /root (the root user's home folder), and /tmp (volatile temporary storage).
**Task 7 – Conclusions and Summaries:** Recaps SSH, flags, filesystem commands, permissions, and directories covered in the room.
**Task 8 – Linux Fundamentals Part 3:** Transition task linking to the final room and instructing the learner to terminate their machine.

### Room 3: Linux Fundamentals Part 3
**Task 1 – Introduction:** Overview of the final room's focus: text editors, utilities, processes, automation, package management, and logs.
**Task 2 – Deploy Your Linux Machine:** Deploys the lab machine and AttackBox and connects via SSH using provided credentials.
**Task 3 – Terminal Text Editors:** Introduces nano for simple in-terminal editing and mentions VIM as a more advanced, customisable alternative.
**Task 4 – General/Useful Utilities:** Covers wget for downloading files over HTTP, scp for securely copying files between machines over SSH, and Python's built-in http.server module for quickly serving files from a directory.
**Task 5 – Processes 101:** Covers viewing processes with ps and top, terminating them with kill and signals (SIGTERM, SIGKILL, SIGSTOP), managing services with systemctl, and backgrounding/foregrounding jobs with &, Ctrl+Z, and fg.
**Task 6 – Maintaining Your System: Automation:** Introduces cron and the crontab syntax (minute, hour, day of month, month, day of week, command) for scheduling recurring tasks.
**Task 7 – Maintaining Your System: Package Management:** Covers the apt package manager, trusting new repositories via GPG keys, and installing/removing software.
**Task 8 – Maintaining Your System: Logs:** Covers /var/log as the central location for service and OS logs, using examples like Apache access/error logs, fail2ban, and UFW.
**Task 9 – Conclusions & Summaries:** Recaps the room and points to further Linux-focused rooms such as Bash Scripting and Regular Expressions.

## Module 3: Windows and AD Fundamentals

### Room 1: Windows Fundamentals 1
**Task 1 – Windows Editions:** Brief history of Windows versions from XP through 11 and Windows Server, noting differences between Home and Pro editions such as device encryption support.
**Task 2 – The Desktop (GUI):** Tours the Windows graphical interface: desktop, Start Menu, search box, task view, taskbar, and notification area.
**Task 3 – Introduction to Windows:** Deploys the lab machine used throughout the room.
**Task 4 – The File System:** Introduces NTFS as the modern Windows file system (versus older FAT/HPFS), its journaling recovery feature, folder/file permissions, and Alternate Data Streams (ADS).
**Task 5 – The Windows\System32 Folders:** Explains the Windows directory and the critical System32 subfolder, plus the %windir% environment variable.
**Task 6 – User Accounts, Profiles, and Permissions:** Covers Administrator vs Standard User account types, user profile folders under C:\Users, and local user/group management via lusrmgr.msc.
**Task 7 – User Account Control:** Explains UAC as a safeguard that prompts for approval before actions requiring elevated privileges are allowed to run.
**Task 8 – Settings and the Control Panel:** Compares the modern Settings app to the legacy Control Panel for making system changes.
**Task 9 – Task Manager:** Introduces Task Manager for viewing running apps/processes and system resource usage.
**Task 10 – Conclusion:** Wraps up the room and previews further Windows topics to come.

### Room 2: Windows Fundamentals 2
**Task 1 – Introduction:** Deploys the lab machine used for Part 2.
**Task 2 – System Configuration and Advanced System Settings:** Covers msconfig's boot/services/startup troubleshooting tabs and Advanced System Settings options like the page file and crash dump (Startup and Recovery) configuration.
**Task 3 – Change UAC Settings:** Covers adjusting the UAC notification slider between Always notify, Notify for apps, Notify without dimming, and Never notify.
**Task 4 – Computer Management:** Tours compmgmt.msc, including Task Scheduler, Event Viewer, Shared Folders, Local Users and Groups, Performance Monitor (perfmon), Device Manager, Disk Management, and Services.
**Task 5 – System Information:** Introduces msinfo32 for viewing hardware, software, and environment variable details.
**Task 6 – Resource Monitor:** Introduces resmon for detailed real-time CPU, memory, disk, and network usage per process.
**Task 7 – Command Prompt:** Covers basic CLI commands including hostname, whoami, ipconfig, netstat, and the net command family.
**Task 8 – Registry Editor:** Introduces regedit and the Windows Registry as the central hierarchical configuration database.
**Task 9 – Conclusion:** Recaps the tools covered, most of which are reachable via msconfig or the Start Menu.

### Room 3: Windows Fundamentals 3
**Task 1 – Introduction:** Deploys the lab machine for Part 3, which focuses on built-in Windows security tooling.
**Task 2 – Windows Updates:** Explains Patch Tuesday, the forced update/reboot behaviour introduced in Windows 10, and where to manage updates.
**Task 3 – Windows Security:** Tours the Windows Security app's protection areas — virus/threat, firewall, app/browser control, device security — and its green/yellow/red status colour coding.
**Task 4 – Virus & threat protection:** Covers Windows Defender scan types (quick/full/custom), quarantined/allowed threats, real-time protection, controlled folder access, and scan exclusions.
**Task 5 – Firewall & network protection:** Explains the three firewall profiles — Domain, Private, and Public — and managing which apps are allowed through the firewall.
**Task 6 – App & browser control:** Covers Microsoft Defender SmartScreen for blocking phishing/malware sites and unrecognised files, plus exploit protection settings.
**Task 7 – Device security:** Covers Core Isolation/Memory Integrity and the Trusted Platform Module (TPM), a hardware chip used for security functions.
**Task 8 – BitLocker:** Introduces BitLocker drive encryption, which offers the strongest protection when paired with a TPM chip.
**Task 9 – Volume Shadow Copy Service:** Explains VSS snapshots/restore points and why ransomware authors often target and delete shadow copies.
**Task 10 – Conclusion:** Wraps up the built-in Windows security tools covered and mentions the "Living Off The Land" attacker tactic of abusing built-in tools.

### Room 4: Active Directory Basics
**Task 1 – Introduction:** Sets up the room's learning objectives: Active Directory domains, components, and forests/trusts.
**Task 2 – Windows Domains:** Explains why centralised management via a Windows domain and a Domain Controller (the server running Active Directory) becomes necessary as a network grows.
**Task 3 – Active Directory:** Covers AD objects (users, machines, security groups), default security groups (Domain Admins, Server Operators, Backup Operators, Account Operators, Domain Users/Computers/Controllers), the difference between Organizational Units (OUs) and Security Groups, and the Active Directory Users and Computers tool.
**Task 4 – Managing Users in AD:** Covers deleting a protected OU (after disabling accidental-deletion protection) and delegating control, such as granting a helpdesk user rights to reset passwords using PowerShell's Set-ADAccountPassword and Set-ADUser cmdlets.
**Task 5 – Managing Computers in AD:** Covers organising machines into dedicated Workstations and Servers OUs instead of leaving them in the default Computers container.
**Task 6 – Group Policies:** Introduces Group Policy Objects (GPOs), the Group Policy Management console, GPO scope and security filtering, example policies (password length, restricting Control Panel access, auto-locking the screen), GPO distribution via the SYSVOL share, and forcing a refresh with gpupdate /force.
**Task 7 – Authentication Methods:** Compares Kerberos (ticket-based authentication using a TGT and per-service TGS issued by the KDC) with the legacy NetNTLM challenge-response protocol.
**Task 8 – Trees, Forests and Trusts:** Explains multi-domain Trees (domains sharing a namespace), Forests (multiple trees with different namespaces), the Enterprise Admins group, and one-way versus two-way trust relationships between domains.
**Task 9 – Conclusion:** Wraps up AD basics and points toward the Active Directory Hardening and Compromising Active Directory rooms for further learning.
