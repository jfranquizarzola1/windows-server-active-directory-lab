# Windows Server 2022 Active Directory Home Lab

This project documents a Windows Server 2022 home lab built in Oracle VirtualBox. The lab simulates a small business environment using Active Directory, DNS, Group Policy, SMB file shares, NTFS permissions, and a Windows 11 domain client.

## Lab Environment

- Domain: `franquiz.lab`
- Domain Controller: `DC01`
- Client Computer: `WIN11-01`
- Server Operating System: Windows Server 2022 Standard
- Client Operating System: Windows 11 Pro
- Virtualization Platform: Oracle VirtualBox

## Project Objectives

- Configure Windows Server 2022 as a domain controller
- Install Active Directory Domain Services and DNS
- Create departmental Organizational Units
- Create domain users and security groups
- Configure SMB file shares and NTFS permissions
- Map department drives using Group Policy
- Add the IT Admins group to the local Administrators group
- Join a Windows 11 client to the domain
- Test and troubleshoot Group Policy and domain access

## Organizational Units

The following departmental OUs were created:

- Finance
- HR
- IT
- Management
- Sales
- Servers
- Workstations

Each department contains separate OUs for:

- Users
- Groups
- Computers

## Security Groups

Examples of security groups used in the lab:

- IT Users
- IT Admins
- HR Users
- Finance Users
- Sales Users
- Management Users

Permissions were assigned to security groups instead of individual users.

## File Shares and Drive Mapping

Department folders were shared from:

```text
C:\Shares
```

Example IT configuration:

```text
Share path: \\DC01\IT
Drive letter: I:
Share permissions: Change and Read
NTFS permissions: Modify
Security group: IT Users
```

Group Policy was used to automatically map department network drives for users.

## Group Policy

Group Policy was used to:

- Map departmental network drives
- Add `FRANQUIZ\IT Admins` to the Windows 11 local Administrators group
- Centrally manage user and computer settings

## Troubleshooting

During testing, Computer Group Policy failed because the Windows 11 client clock was not synchronized with DC01.

The issue was resolved by correcting the system time, resynchronizing the client with the domain, and running:

```cmd
gpupdate /force
```

## Tools Used

- Oracle VirtualBox
- Windows Server 2022
- Windows 11 Pro
- Server Manager
- Active Directory Users and Computers
- DNS Manager
- Group Policy Management
- File Explorer
- Command Prompt
- SMB File Sharing
- NTFS Permissions

## Documentation

- [View the PDF presentation](docs/Active%20Directory%20Homelab.pdf)
- [View the Active Directory documentation](active-directory/README.md)
- [View configuration screenshots](active-directory/screenshots)
- [View commands used in the lab](active-directory/commands/README.md)

## Interactive Presentation

The full interactive PowerPoint presentation contains embedded demonstration videos.

[Download the interactive presentation from the latest GitHub release](../../releases/latest)

## Installation Media

This lab was created using official Microsoft installation media:

- Windows Server 2022 Evaluation
- Windows 11

The ISO files are not stored in this repository.

## Security Notice

This repository does not include passwords, password hashes, the Active Directory database, private keys, virtual machine files, or sensitive authentication information.

## Project Status

Completed.
