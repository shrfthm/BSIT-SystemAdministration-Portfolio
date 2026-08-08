# Week 1 – Building My Professional Environment
## Student Information
- Name: Shareef P. Tohmi
- Course: Bachelor of Science in Information Technology
- Section: 4A Web and Mobile Development
- Date: August 6, 2026
# Objectives
By completing the Week 1 Laboratory Activity, I aim to achieve the following:

- **Setup & Configuration:** Successfully install and verify the core SysAdmin toolchain (Git, VS Code, VirtualBox, Linux & Windows ISOs).
- **Version Control & Portfolio:** Initialize and configure my `BSIT-SystemAdministration-Portfolio` repository on GitHub with standardized folder structures from Week 01 to Week 15.
- **Documentation:** Author structured technical documentation using Markdown, including proof of installation, troubleshooting resolution logs, and learning reflections.
- **Professional Branding:** Establish my professional IT presence across GitHub and LinkedIn by building custom profile documentation and broadcasting my learning journey.
---
# Software Installed
- GUI
- Github Desktop
- Visual Studio Code
- Virtual Box
- Ubuntu ISO
- Windows Enterprise Evaluation ISO
---
# Professional Accounts
- **GitHub:** https://github.com/shrfthm
- **LinkedIn:** ://www.linkedin.com/in/shareef-tohmi-16780a427/
---
# Installation Screenshots
![Git Installation](./screenshots/git-install.png)
![VS Code Installation](./screenshots/vscode-install.png)
![VirtualBox Installation](./screenshots/virtualbox-install.png)
![Ubuntu ISO](./screenshots/ubuntu-iso.png)
![Windows ISO](./screenshots/windows-iso.png)
---
# Challenges Encountered
During the setup and installation of the virtual machines in Oracle VirtualBox, three key technical challenges were encountered and resolved:

1. **Windows 11 Black Screen on Startup:** Launching the Windows 11 virtual machine resulted in a black screen without displaying the boot logo or installation setup. This was caused by host-level Hyper-V conflicts and automated unattended boot loops. It was resolved by executing `bcdedit /set hypervisorlaunchtype off` in an elevated Command Prompt, setting the VM display memory to **128 MB** with **3D Acceleration disabled**, and attaching the standard Windows 11 ISO file directly instead of using the unattended setup wizard.

2. **Ubuntu `vmwgfx` Unsupported Hypervisor Error:** Booting the Ubuntu VM produced a red display driver error (`*ERROR* vmwgfx seems to be running on an unsupported hypervisor`), which prevented the desktop installer from opening. This occurred because VirtualBox defaulted to an incompatible VMware display controller (`VMSVGA`). Changing the **Graphics Controller** setting to **VBoxVGA** (or **VBoxSVGA**) in the VM Display settings resolved the driver conflict and allowed the Ubuntu live desktop to load successfully.

3. **Grayed-Out "Nested VT-x/AMD-V" Setting:** The option to enable hardware virtualization passthrough was disabled and grayed out in the VirtualBox user interface, preventing proper 64-bit nested virtualization. This was fixed by opening Command Prompt as Administrator, navigating to the VirtualBox directory, and running `VBoxManage modifyvm "Windows 11" --nested-hw-virt on`, along with disabling **Memory Integrity (Core Isolation)** in Windows Security.

---
# Reflection
Setting up and configuring virtual machines using Oracle VirtualBox provided valuable hands-on experience in hardware resource allocation, operating system deployment, and environment troubleshooting. Navigating the configuration process for both Windows 11 and Ubuntu highlighted how hypervisors interact directly with host system hardware. Diagnosing issues—such as resolving graphics driver incompatibilities (vmwgfx), handling host-level Hyper-V conflicts, and enabling nested virtualization via command-line tools like VBoxManage—demonstrated that system deployment rarely works seamlessly on the first attempt without proper configuration and troubleshooting.

Mastering virtualization tools and hypervisors is essential for effective system administration. Virtualization allows administrators to provision, isolate, and manage multiple operating systems on a single physical host, significantly reducing hardware overhead and optimizing resource utilization. Learning to configure virtual disks, assign dedicated CPU cores, allocate memory parameters, and manage virtual network adapters mimics the operational workflows required in production server environments and cloud infrastructure.

Furthermore, virtualization provides a safe, sandbox environment for testing software updates, trying out security configurations, and deploying new service stacks without risking live production systems. Developing the ability to systematically diagnose boot failures, resolve driver mismatches, and tweak low-level hypervisor settings builds the critical problem-solving mindset necessary for maintaining uptime, managing server infrastructure, and delivering reliable IT services as a future System Administrator.
---
# References
https://www.microsoft.com/
https://ubuntu.com/
https://www.virtualbox.org/manual/
https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/
