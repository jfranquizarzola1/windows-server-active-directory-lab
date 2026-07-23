# Active Directory Configuration

This folder documents the Active Directory structure and configuration used in the Windows Server 2022 home lab.

## Domain Information

- Domain: `franquiz.lab`
- Domain Controller: `DC01`
- Client Computer: `WIN11-01`

## Organizational Units

The domain includes the following departmental Organizational Units:

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

Examples of security groups created in the lab include:

- IT Users
- IT Admins
- HR Users
- Finance Users
- Sales Users
- Management Users

Permissions were assigned to security groups instead of individual users to support role-based access control and easier administration.

## Group Policy

Group Policy was used to:

- Map departmental network drives
- Add the IT Admins group to the local Administrators group on the Windows 11 client
- Centrally manage user and computer settings

## File Access

Department folders were shared using SMB and secured with NTFS permissions.

Example:

- Share path: `\\DC01\IT`
- Drive letter: `I:`
- Share permissions: Change and Read
- NTFS permissions: Modify
- Assigned group: IT Users

## Security Notice

This repository does not include passwords, password hashes, the Active Directory database, private keys, virtual machine files, or other sensitive authentication data.
