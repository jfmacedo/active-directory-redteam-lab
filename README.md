# Active Directory Red Team Lab

[wip]

# Do it Yourself

## Steps - Part 1

### *Setting up the virtual environment*

The lab environment was built using Oracle VM VirtualBox. The software was downloaded from the official website and installed using the default configuration, providing the base required to run multiple virtual machines simultaneously.

### *Preparing the Windows 10 machine*

The Windows 10 installation media was obtained through Microsoft’s official website using the Media Creation Tool. After generating the ISO file, a new virtual machine was created in VirtualBox. The machine was configured with appropriate resources, including memory, CPU allocation, and disk space. The ISO was mounted, and the operating system was installed by following the standard installation process.

### *Setting up the attacker machine (Kali Linux)*

A Kali Linux virtual machine was downloaded in its pre-configured VirtualBox format. The file was extracted and imported into VirtualBox, allowing the machine to be quickly deployed. This system will serve as the attacker machine for all future testing and simulation within the lab.

### *Preparing the Windows Server machine*

The Windows Server 2022 ISO was downloaded from Microsoft’s evaluation center. A dedicated virtual machine was created and configured similarly to the other systems. During installation, the desktop experience version was selected to simplify interaction. Basic configuration was completed, including setting the administrator credentials.

### *Part 1 - Summary*

At this point, the lab environment has been successfully initialized. The setup includes a Windows Server machine, a Windows 10 client machine, and a Kali Linux attacker machine. All systems are installed and operational, forming the foundation for the next stages of configuration and security testing.

## Steps - Part 2

### *Configuring network settings*

After installing all virtual machines, network settings were adjusted to allow communication between systems. Each machine was configured within VirtualBox to use a Host-Only Adapter, creating an isolated internal network for the lab.

Manual IP configuration was applied to ensure consistent communication between machines. The same IPv4 network range was used across the systems to allow proper connectivity.

Connectivity tests were performed to verify that the machines could successfully reach each other within the network.

### *Promoting the server to domain controller*

The Windows Server machine was configured as the domain controller by installing Active Directory Domain Services. During this process, a new domain named `corp.local` was created.

This step established the central authentication system for the lab environment.

### *Creating domain users*

User accounts were created within Active Directory to simulate a real-world corporate environment. These accounts will be used in later stages for authentication, enumeration, and attack scenarios.

### *Preparing domain authentication*

A test user account was created and prepared for domain authentication. This account will be used when connecting client machines to the domain and validating login functionality.

### *Part 2 - Summary*

At this stage, the virtual network has been successfully configured and the domain controller is fully operational. Active Directory is running, users have been created, and the lab environment is now ready for client integration and further security testing.