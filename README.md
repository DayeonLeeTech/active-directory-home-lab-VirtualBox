![Windows Server](https://img.shields.io/badge/Windows%20Server-0078D4?style=for-the-badge&logo=windows-server&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-%235391FE.svg?style=for-the-badge&logo=powershell&logoColor=white)
![VirtualBox](https://img.shields.io/badge/VirtualBox-214294?style=for-the-badge&logo=virtualbox&logoColor=white)
![Active Directory](https://img.shields.io/badge/Active%20Directory-0078D4?style=for-the-badge&logo=microsoft-active-directory&logoColor=white)
![DHCP](https://img.shields.io/badge/DHCP-orange?style=for-the-badge&logo=server&logoColor=white)
![Automation](https://img.shields.io/badge/Automation-blueviolet?style=for-the-badge&logo=robot&logoColor=white)
# Active Directory Home Lab (Oracle VirtualBox)
<p align="center">
  <img src="assets/active-directory.drawio (1).png" width="100%" alt="My Lab Setup" />
</p>

## Introduction
This Home Lab was built using Oracle VirtualBox to simulate a functional corporate network on Windows Server 2019. The project provided hands-on experience with Active Directory, DNS, and DHCP configuration for a Windows 10 client. A PowerShell script was also implemented to automate bulk user creation, demonstrating how automation simplifies everyday management tasks. This setup served as a practical way to gain direct experience with Windows networking and the core system administration tools used in IT support.

## Technical Skills & Tools
* Virtualization: Oracle VirutalBox
* Operating Systems: Windows Server 2019, Windows 10 Pro
* Networking: DHCP, DNS, NAT, Private Virtual Networks
* Automation: PowerShell Scripting
  
Download Links
* [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Windows Server 2019 ISO](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)
* [Windows 10 ISO](https://www.microsoft.com/en-us/software-download/windows10)

---
## Project Setup

### Part 1: Virtualization & Network Setup 
The foundation of the lab is a virtualized corporate network designed to be completely isolated from the host machine.
* Environment Deployment: Used Oracle VirtualBox to host two virtual machines: a Windows Server 2019 Domain Controller and a Windows 10 client.
* Dual-NIC Configuration: The Domain Controller was configured with two network adapters—one for internet access and one for the internal private network—allowing it to act as a gateway.
* Internal Subnet: Established a private virtual network to ensure secure communication between the server and client.

<p align="center">
  <img src="assets/VMConfig.png" width="800" alt="My Lab Setup" />
</p>

### Part 2: Active Directory & Network Services
This stage focused on transforming the standalone server into the central management hub for the network.
* Active Directory (AD DS): Installed and configured the Active Directory role, promoting the server to a Domain Controller for the internal domain.
* Network Infrastructure: Configured Static IP addressing and DNS for proper name resolution across the private subnet.
* DHCP Management: Established a DHCP scope ($172.16.0.100 - 200$) to automate IP assignment for any client workstations joining the domain.
<p align="center">
  <img src="assets/ActiveDirectory.png" width="800" alt="Active Directory Setup" />
</p>

### Part 3: Routing & Internet Connectivity
To ensure the isolated client machine could reach the web safely, the server was configured as a functional router.
* NAT Configuration: Enabled Routing and Remote Access (RAS) on the server.
* Internet Gateway: Configured Network Address Translation (NAT) so the Windows 10 client could access the internet through the Domain Controller’s external adapter.
* Connectivity Verification: Confirmed the client workstation could reach external sites while remaining on the internal subnet.
<p align="center">
  <img src="assets/InstallRAS_NAT.png" width="800" alt="NAT Configuration" />
</p>

<p align="center">
  <img src="assets/NetworkConnectivityTest.png" width="800" alt="Connectivity Test" />
</p>

### Part 4: PowerShell Automation
Instead of manual account creation, automation was used to simulate a large-scale employee onboarding process.
* Scripting: Developed a PowerShell script to read from a list of names and automatically generate unique user accounts.
* Efficiency: This process demonstrated how to provision hundreds of users instantly, ensuring consistent account settings and saving hours of manual entry.

Automation Scripts:
* [📂 Create Users Script](scripts/1_CREATE_USERS.ps1) – The primary logic for provisioning accounts in AD.
* [📂 Name Generation Script](scripts/Generate-Names-Create-Users.ps1) – Used to generate mock user data for the simulation.
  
<p align="center">
  <img src="assets/PowerShell.png" width="800" alt="PowerShell Automation" />
</p>

---

## Project Outcome & Key Takeaways
The project successfully established a functional corporate network within a virtualized environment. By the end of the lab, a Windows 10 client workstation was fully integrated into a managed domain, receiving automated network configurations and maintaining stable, routed internet connectivity through a centralized Windows Server 2019 Domain Controller.

### Core Technical Competencies
* **System Administration:** Hands-on experience managing a centralized Windows Server environment, including Active Directory Domain Services (AD DS) and organizational unit (OU) management.
* **Network Infrastructure:** Configuration of critical infrastructure services, including DHCP for dynamic IP assignment and DNS for internal name resolution.
* **Network Routing & NAT:** Implementation of Routing and Remote Access (RAS) to provide internal-to-external internet communication for isolated client nodes.
* **Workflow Automation:** Utilization of PowerShell scripting to provision 1,000+ user accounts instantly, demonstrating the ability to handle high-volume administrative tasks with precision.

### Key Takeaways
* **Automation at Scale:** Demonstrated that PowerShell is an essential force multiplier in IT, transforming a task that would take days (manual user creation) into a process that takes seconds.
* **Infrastructure Interconnectivity:** Gained a deep understanding of how AD, DNS, and DHCP must work in perfect synchronization for a client workstation to successfully join and authenticate with a domain.
* **Virtualized Networking:** Mastered the complexity of dual-homed networking, successfully using a server as a gateway to provide internet access to a private, secure subnet.
* **Standardized Configuration:** Recognized the importance of standardized user data and automated provisioning to prevent human error during large-scale employee onboarding.

---

## Conclusion & Cleanup
To maintain system hygiene and resource efficiency, the virtual environment was decommissioned upon completion. This project served as a comprehensive exercise in building, securing, and automating a standard enterprise network from the ground up.









