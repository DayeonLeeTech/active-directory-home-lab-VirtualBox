
# Active Directory Home Lab (Oracle VirtualBox)

### TL;DR
*   **Technologies Used:** Oracle VirtualBox, PowerShell, Windows Server 2019, Windows 10
*   **Download Links:**
    *   [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
    *   [Windows Server 2019 ISO](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)
    *   [Windows 10 ISO](https://www.microsoft.com/en-us/software-download/windows10)

---
## Introduction
I set up a home lab to run Active Directory using Oracle VirtualBox. First, I created a Windows Server virtual machine (VM) to serve as my domain controller. After setting up the VM, I installed and configured Active Directory Domain Services (AD DS) and set up the domain. Once the domain was ready

## Project Setup

### Stage 1: Virtualization & VM Creation
I wanted a reliable sandbox to run my Windows Server, so I went with Oracle VirtualBox. It’s a great, flexible way to run a lab right on my MacBook Air (M3).

* **Installation:** I grabbed the ARM64 version of VirtualBox directly from the official site. It’s built to run natively on the Apple Silicon architecture, so it feels smooth and responsive.
* **Creating the VM:** Once everything was installed, I set up a new virtual machine. I pointed it toward the Windows Server ISO and allocated the right amount of RAM and CPU power. I wanted to make sure it had enough "breathing room" to run well without eating up all my laptop’s resources.

---
