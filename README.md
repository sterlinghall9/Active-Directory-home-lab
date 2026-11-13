# Active-Directory-home-lab
Hands-on Windows Server 2022 Active Directory home lab demonstrating domain administration, DNS configuration, user management, Group Policy, and Windows workstation integration

## Project Overview

Built a Windows Server 2022 Active Directory home lab using Oracle VirtualBox to simulate a small business IT environment. Configured a domain controller, DNS, organizational units, user accounts, security groups, Group Policy, and a Windows 11 domain-joined workstation.

Performed hands-on IT administration and Help Desk troubleshooting exercises involving password resets, account lockouts, employee offboarding, and security group management.

## Lab Architecture

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Domain Controller | Windows Server 2022 |
| Client Workstation | Windows 11 |
| Domain | ad.sterlingtech.test |
| NetBIOS Domain | STERLINGTECH |
| DC01 IP Address | 192.168.10.10 |
| CLIENT01 IP Address | 192.168.10.20 |
| Virtual Network | Internal Network: AD-LAB |

## Technologies Used

- Windows Server 2022
- Windows 11
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy Management
- Active Directory Users and Computers
- Windows PowerShell
- Event Viewer
- Oracle VirtualBox

## Tasks Completed

### 1. Active Directory Configuration
- Installed and configured Active Directory Domain Services.
- Promoted Windows Server 2022 to a domain controller.
- Created the domain `ad.sterlingtech.test`.
- Configured DNS and verified domain records.
- Created organizational units for IT, Human Resources, Finance, and Operations.

### 2. User and Security Group Management
- Created domain user accounts.
- Created the IT-Support security group.
- Added and removed users from security groups.
- Reset domain user passwords.
- Disabled employee accounts.

### 3. Group Policy Management
- Created the `IT - Control Panel Restriction` Group Policy Object.
- Linked the policy to the IT organizational unit.
- Configured restrictions on Control Panel and PC Settings.
- Verified policy application using `gpresult /r`.
- Confirmed the restriction on the Windows 11 client.

### 4. Account Lockout Troubleshooting
- Configured a domain account lockout threshold of five failed attempts.
- Set the lockout duration to 15 minutes.
- Investigated authentication failures using Event Viewer.
- Used PowerShell to inspect account lockout status.
- Successfully unlocked a test domain account.

### 5. Employee Offboarding
- Disabled an employee's Active Directory account.
- Verified the account status using PowerShell.
- Confirmed that the disabled account could no longer authenticate on the domain-joined workstation.
- Practiced removing an employee from a security group.

### 6. Domain Workstation Configuration
- Installed Windows 11 in VirtualBox.
- Configured static IP addressing and DNS.
- Joined CLIENT01 to the Active Directory domain.
- Tested domain authentication using a standard domain user.
- Verified domain controller discovery and connectivity.

## Troubleshooting Commands

```powershell
# Identify the current user
whoami

# Display Group Policy results
gpresult /r

# Locate the domain controller
nltest /dsgetdc:ad.sterlingtech.test

# Display domain group members
Get-ADGroupMember "IT Support"

# Check whether an account is enabled
Get-ADUser camille.hall -Properties Enabled

# Check account lockout status
Get-ADUser camille.hall -Properties LockedOut
```

## Skills Demonstrated

- Active Directory administration
- Windows Server administration
- DNS configuration and troubleshooting
- Group Policy administration
- User account provisioning and deprovisioning
- Password resets and account recovery
- Security group management
- PowerShell
- Event Viewer
- Windows 11 workstation deployment
- Domain authentication troubleshooting

## Project Outcome

Successfully built and administered a simulated business domain environment with a Windows Server 2022 domain controller and a Windows 11 domain-joined workstation. Practiced common IT Support and Help Desk responsibilities through hands-on user administration, access control, Group Policy, and troubleshooting exercises.

**Author:** Sterling Hall

