# Active Directory Red Team Lab

[wip]

# Do it Yourself

## Steps - Part 1

### *Setting up the virtual environment*

The lab environment was built using Oracle VM VirtualBox, which was installed using the default configuration. This setup provides the foundation required to run multiple virtual machines simultaneously within an isolated environment.

### *Preparing the Windows Server machine*

The Windows Server 2022 ISO was downloaded from Microsoft’s evaluation center and used to create a dedicated virtual machine that acts as the domain controller (DC01). The system was configured with 4GB of RAM, 2 CPUs, and a 50GB virtual disk. During installation, the Desktop Experience version was selected to simplify interaction with the system. Initial configuration was completed, including setting the administrator credentials.

### *Preparing the Windows 10 machine*

The Windows 10 installation media was obtained through Microsoft’s official website using the Media Creation Tool. After generating the ISO file, a new virtual machine was created in VirtualBox to act as the client machine within the lab. The system was configured with 4GB of RAM, 2 CPUs, and a 50GB virtual disk. The ISO was mounted, and the operating system was installed following the standard installation process.

### *Setting up the attacker machine (Kali Linux)*

A pre-configured Kali Linux VirtualBox image was downloaded and extracted. The virtual machine was then imported directly into VirtualBox, allowing for a faster deployment. This machine is used as the attacker system throughout the project and is responsible for performing enumeration and exploitation tasks in later stages.

### *Part 1 - Summary*

At this stage, the lab environment consists of three fully operational virtual machines: a Windows Server 2022 system configured to become the domain controller, a Windows 10 client machine, and a Kali Linux attacker machine. All systems have been successfully installed and are ready for network configuration and domain setup.


## Steps - Part 2

### *Configuring network settings*

After installing all virtual machines, network settings were adjusted to allow communication between systems. Each machine was configured within VirtualBox to use a Host-Only Adapter, creating an isolated internal network for the lab.

Manual IP configuration was applied to ensure consistent communication between machines. The same IPv4 network range was used across the systems to allow proper connectivity.

Connectivity tests were performed to verify that the machines could successfully reach each other within the network.

### *Promoting the server to domain controller*

The Windows Server machine (DC01) was configured as the domain controller by installing Active Directory Domain Services.

During the setup process, a new domain named `corp.local` was created, establishing the central identity and authentication system for the lab.

The server was promoted successfully, and domain services were verified to ensure proper functionality.

### *Creating domain users*

User accounts were created within Active Directory to simulate a real-world corporate environment. These accounts will be used in later stages for authentication, enumeration, and attack scenarios.

### *Preparing domain authentication*

A test user account was created and prepared for domain authentication. This account will be used when connecting client machines to the domain and validating login functionality.

### *Part 2 - Summary*

At this stage, the virtual network has been successfully configured and the domain controller is fully operational. Active Directory is running, users have been created, and the lab environment is now ready for client integration and further security testing.