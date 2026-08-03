# TryHackMe: Active Directory Basics — Notes

## Task 1: Introduction
Overview of AD fundamentals: what AD is, what a domain is, and forest/trust concepts.

## Task 2: Windows Domains
A Windows domain centralizes user/computer administration via Active Directory,
hosted on a Domain Controller (DC). Key benefits: centralized identity management
and centralized security policy enforcement.

## Task 3: Active Directory
Core AD object types: Users, Machines, Security Groups (all "security principals").
Machine accounts follow the pattern COMPUTERNAME$.
Default groups: Domain Admins, Server Operators, Backup Operators, Account Operators,
Domain Users, Domain Computers, Domain Controllers.
OUs organize objects for policy application; a user belongs to only one OU at a time.
Managed via Active Directory Users and Computers (ADUC).

## Task 4: Managing Users in AD
Covers OU cleanup, enabling "Advanced Features" to delete protected OUs, and
Delegation (granting limited admin rights, e.g. password resets, without full
Domain Admin access) via ADUC's "Delegate Control" wizard.

Key commands:
- Set-ADAccountPassword <user> -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
- Set-ADUser -ChangePasswordAtLogon $true -Identity <user> -Verbose

## Task 5: Managing Computers in AD
Organizing computer objects into OUs by role: Workstations, Servers, Domain Controllers.

## Task 6: Group Policies
GPOs apply settings to OUs (user or computer scope), managed via Group Policy
Management. Distributed via the SYSVOL share (C:\Windows\SYSVOL\sysvol\).
Force sync: gpupdate /force.

## Task 7: Authentication Methods
Kerberos (modern default): KDC, TGT, Session Key, TGS, SPN, Service Session Key, krbtgt.
NetNTLM (legacy): challenge-response mechanism; password/hash never sent over the wire.

## Task 8: Trees, Forests and Trusts
Tree = domains sharing a namespace. Forest = multiple trees, different namespaces.
Enterprise Admins = rights across all domains in a forest (vs. Domain Admins, single domain).
Trust relationships (one-way / two-way) enable cross-domain resource access.

## Task 9: Conclusion
Follow-on rooms: Active Directory Hardening (defense), Compromising Active Directory (offense).
