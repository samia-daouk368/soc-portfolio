# AD Basics — Cheat Sheet

## Core Terms
AD, Domain, Domain Controller (DC), OU, Security Principal, GPO, SYSVOL,
Kerberos, NetNTLM, Tree, Forest, Trust Relationship

## Commands
gpupdate /force
Set-ADAccountPassword <user> -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
Set-ADUser -ChangePasswordAtLogon $true -Identity <user> -Verbose

## Default Security Groups
Domain Admins, Enterprise Admins, Server Operators, Backup Operators,
Account Operators, Domain Users, Domain Computers, Domain Controllers

## Default Containers
Builtin, Computers, Domain Controllers, Users, Managed Service Accounts

## Kerberos Flow
KDC -> TGT (+ Session Key) -> TGS request (with SPN) -> TGS (+ Service Session Key) -> Service

## NetNTLM Flow
Client -> Server challenge -> Client response (hash-derived) -> DC verifies -> Result

## Tools
Active Directory Users and Computers (ADUC), Group Policy Management Console
