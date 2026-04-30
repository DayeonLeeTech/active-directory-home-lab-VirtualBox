
# Active Directory Home Lab (Oracle VirtualBox)

### TL;DR
Technologies Used
* Virtualization: Oracle VirutalBox
* Operating Systems: Windows Server 2019, Windows 10 Pro
* Networking: DHCP, DNS, NAT, Private Virtual Networks
* Automation: PowerShell Scripting
  
Download Links
* [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Windows Server 2019 ISO](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)
* [Windows 10 ISO](https://www.microsoft.com/en-us/software-download/windows10)

---
## Overview
This Home Lab was built using Oracle VirtualBox to simulate a functional corporate network on Windows Server 2019. The project provided hands-on experience with Active Directory, DNS, and DHCP configuration for a Windows 10 client. A PowerShell script was also implemented to automate bulk user creation, demonstrating how automation simplifies everyday management tasks. This setup served as a practical way to gain direct experience with Windows networking and the core system administration tools used in IT support.

## Project Setup

### Stage 1: Virtualization & Network Setup 
The foundation of the lab is a virtualized corporate network designed to be completely isolated from the host machine.
* Environment Deployment: Used Oracle VirtualBox to host two virtual machines: a Windows Server 2019 Domain Controller and a Windows 10 client.
* Dual-NIC Configuration: The Domain Controller was configured with two network adapters—one for internet access and one for the internal private network—allowing it to act as a gateway.
* Internal Subnet: Established a private virtual network to ensure secure communication between the server and client.

![My Lab Setup](assets/VMConfig.png)

### Stage 2: Active Directory & Network Services
This stage focused on transforming the standalone server into the central management hub for the network.
* Active Directory (AD DS): Installed and configured the Active Directory role, promoting the server to a Domain Controller for the internal domain.
* Network Infrastructure: Configured Static IP addressing and DNS for proper name resolution across the private subnet.
* DHCP Management: Established a DHCP scope ($172.16.0.100 - 200$) to automate IP assignment for any client workstations joining the domain.
![My Lab Setup](assets/ActiveDirectory.png)
---
