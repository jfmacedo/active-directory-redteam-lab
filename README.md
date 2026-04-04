# Active Directory Red Team Lab

[wip]

## Objective

This project simulates a corporate Active Directory environment in a controlled lab setting in order to understand how enterprise networks are configured and how attackers may interact with them during a red team engagement.

## Skills Learned

- Virtual machine deployment using VirtualBox
- Windows Server installation and initial configuration
- Active Directory Domain Services setup
- Domain creation and user management
- Basic lab network preparation

## Tools Used

- Oracle VM VirtualBox
- Kali Linux
- Windows Server 2022
- Active Directory Domain Services

# Steps

## Part 1

### *Prepare the lab environment*

A dedicated lab environment was prepared using VirtualBox in order to isolate the machines used throughout the project.

### *Create the domain controller*

A Windows Server virtual machine was created and configured to act as the domain controller for the lab.

### *Install Active Directory Domain Services*

Active Directory Domain Services was installed on the Windows Server machine in order to create a functional enterprise-style domain environment.

### *Create the domain*

A new domain named `corp.local` was created and configured on the server.

### *Create domain users*

Several users were created in Active Directory to simulate a realistic corporate environment and prepare the lab for future enumeration and attack scenarios.

## Next Steps

- Configure the Windows 10 client machine
- Join the client machine to the domain
- Validate network communication between lab systems
- Begin reconnaissance and enumeration from Kali Linux