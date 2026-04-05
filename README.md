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

After preparing all virtual machines, network settings were configured to allow communication between systems. Each machine was connected using a Host-Only Adapter in VirtualBox, creating an isolated internal network for the lab environment.

To ensure stable and predictable communication, static IP addressing was applied across all machines. The domain controller (DC01) was assigned the IP address 192.168.56.10, the Windows 10 (Win10-Client) client machine was configured with 192.168.56.20, and the Kali Linux attacker machine was assigned 192.168.56.30. All systems operated within the same subnet (255.255.255.0).

The DNS configuration on the client machines was set to point to the domain controller, allowing proper name resolution within the domain environment.

Connectivity between machines was tested to confirm that the network configuration was functioning correctly.

### *Installing Active Directory Domain Services*

The Windows Server machine (DC01) was prepared to act as the domain controller by installing the Active Directory Domain Services role through the Server Manager using the "Add Roles and Features" option.

This step enabled the necessary services required to manage domain-based authentication and directory structures.

### *Promoting the server to domain controller*

Following the installation of the Active Directory role, the server was promoted to a domain controller. During this process, a new domain named `corp.local` was created, establishing the central identity and authentication system for the lab.

The promotion process was completed successfully, and the domain services were verified to ensure proper operation.

### *Configuring Active Directory and users*

With Active Directory in place, user accounts were created to simulate a basic enterprise environment. These accounts will be used in later stages for authentication testing, enumeration, and privilege-related activities.

A test user account was also prepared to validate domain authentication from client machines.

### *Part 2 - Summary*

At this stage, the internal network has been fully configured, and all machines are successfully connected. Active Directory Domain Services have been installed, the server has been promoted to a domain controller, and the `corp.local` domain is operational. User accounts have been created, and the environment is now ready for client integration and further security testing.

## Steps - Part 3

### *Configuring the client machine*

The Windows 10 client machine was configured to operate within the same internal network as the domain controller. A static IP address (192.168.56.20) was assigned, using the same subnet (255.255.255.0) as the rest of the environment to ensure proper communication.

The DNS server was configured to point to the domain controller (192.168.56.10), allowing the client machine to resolve domain services correctly and communicate with Active Directory.

These configurations ensured that the client machine was correctly integrated into the lab network and capable of interacting with the domain environment.

### *Joining the domain*

After confirming network configuration, the client machine was joined to the `corp.local` domain. This step integrated the workstation into the domain infrastructure, allowing centralized authentication through the domain controller.

The domain join process completed successfully, confirming proper communication between the client machine and the domain controller.

### *Validating domain authentication*

Authentication was tested using a domain user account created in Active Directory (`testuser`). The login was performed using the domain format (e.g., `corp\testuser`), confirming that domain authentication was working as expected.

This validation demonstrated that the client machine was fully integrated into the domain and that authentication requests were being handled correctly by the domain controller.

### *Part 3 - Summary*

At this stage, the Windows 10 client machine has been successfully integrated into the domain environment. Network configuration, domain join, and user authentication have all been validated, resulting in a functional enterprise-style setup ready for further security testing.