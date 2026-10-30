# Cybersecurity Internship – Week 01
## Kali Linux Virtual Lab Setup and Network Configuration

### 1. Project Overview

This project documents the setup of a cybersecurity virtual lab using **Oracle VM VirtualBox** and **Kali Linux**. The lab is intended to provide a controlled environment for learning cybersecurity fundamentals, Linux administration, networking, and ethical penetration testing.

The project focuses on preparing a Kali Linux virtual machine, configuring its virtual network, and documenting the setup process with screenshots and verification steps.

### 2. Project Objectives

- Install and configure Oracle VM VirtualBox.
- Create a virtual machine for Kali Linux.
- Prepare the Kali Linux installation environment.
- Configure a virtual NAT network for the cybersecurity lab.
- Understand basic virtual machine networking.
- Verify network connectivity and document the results.
- Build a foundation for future cybersecurity and penetration-testing exercises.

### 3. Tools and Technologies

| Tool | Purpose |
|---|---|
| Oracle VM VirtualBox 7.2 | Virtualization platform |
| Kali Linux 2024.4 | Cybersecurity operating system |
| VirtualBox NAT Network | Virtual lab networking |
| GitHub | Project documentation and version control |

### 4. Virtual Machine Configuration

The following configuration reflects the VirtualBox VM setup shown in the project screenshot.

| Configuration | Value |
|---|---|
| VM Name | NetworkWalks |
| Virtualization Platform | Oracle VM VirtualBox 7.2 |
| Guest OS Type (currently selected) | Ubuntu (64-bit) |
| Kali Linux ISO | kali-linux-2024.4-installer-amd64.iso |
| RAM | 4096 MB (4 GB) |
| CPU Cores | 2 |
| Virtual Hard Disk | NetworkWalks.vdi |
| Disk Capacity | 25 GB |
| Graphics Controller | VMSVGA |
| Network Adapter | Intel PRO/1000 MT Desktop |
| Network Attachment | NAT Network |
| NAT Network Name | CyberLab |


### 5. Virtual Network Configuration

A VirtualBox NAT Network named `CyberLab` was created for the virtual lab.

| Network Setting | Value |
|---|---|
| Network Name | CyberLab |
| Network Mode | NAT Network |
| IPv4 Network | 10.0.0.0/24 |
| Gateway | 10.0.0.1 |
| DHCP | Enabled |
| IPv6 | Disabled |

The following static IPv4 configuration is the intended Kali Linux network configuration. It should be treated as planned until it has been applied and verified inside the virtual machine.

| Setting | Planned Value |
|---|---|
| IPv4 Address | 10.0.0.2 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 10.0.0.1 |
| Preferred DNS | 8.8.8.8 |
| Alternate DNS | 1.1.1.1 |

**Important:** Before assigning a static IP address, ensure that `10.0.0.2` is outside the DHCP allocation range to avoid an IP address conflict.

### 6. Setup Procedure

The lab setup process follows these stages:

1. Download and prepare the Kali Linux 2024.4 installer ISO.
2. Install Oracle VM VirtualBox 7.2.
3. Create a virtual machine named `NetworkWalks`.
4. Allocate 4096 MB RAM and 2 CPU cores.
5. Create the 25 GB virtual hard disk.
6. Attach the Kali Linux installer ISO.
7. Create the NAT Network named `CyberLab`.
8. Attach the VM network adapter to the `CyberLab` NAT Network.
9. Proceed with Kali Linux installation and initial configuration.
10. Configure the intended network settings after the operating system is ready.
11. Perform connectivity checks and document the results.

### 7. Installation and Troubleshooting Notes

During the initial Kali Linux setup, two issues were encountered:

- **Graphical desktop issue:** After login, the graphical desktop did not load as expected. The terminal was accessible using `Ctrl + Alt + F2`.
- **APT repository issue:** Running `sudo apt update` returned a message indicating that no APT data sources were configured.

These issues require further troubleshooting and verification. The installation and graphical desktop should not be considered fully completed until the Kali desktop loads successfully and package updates work.

### 8. Verification Commands

Once Kali Linux is installed and the network configuration has been applied, the following commands can be used to verify the environment.

**Check the IP address:**

```bash
ip addr
```

**Check the routing table:**

```bash
ip route
```

**Check DNS configuration:**

```bash
cat /etc/resolv.conf
```

**Test connectivity to the gateway:**

```bash
ping -c 4 10.0.0.1
```

**Test internet connectivity:**

```bash
ping -c 4 8.8.8.8
```

**Test DNS resolution:**

```bash
ping -c 4 google.com
```

### 9. Project Screenshots

Screenshots are included to provide visual evidence of the lab setup and installation stages.

| Screenshot | Filename |
|---|---|
| VirtualBox VM configuration | `01-virtualbox-vm.png` |
| Kali Linux network settings | `02-kali-network-settings.png` |
| Kali Linux boot screen | `03-kali-boot-screen.png` |
| Kali Linux login screen | `04-kali-login-screen.png` |
| Kali Linux desktop | `05-kali-desktop.png` |

VirtualBox VM Configuration



Kali Linux Network Settings



Kali Linux Boot Screen



Kali Linux Login Screen



Kali Linux Desktop


### 10. Learning Outcomes

This project provides practical experience with:

- Virtual machine creation and configuration.
- Kali Linux installation preparation.
- Virtual networking concepts.
- NAT Network configuration.
- Basic Linux terminal commands.
- IP addressing and DNS concepts.
- Troubleshooting operating system and package-management issues.
- Technical documentation using GitHub and Markdown.

### 11. Ethical Use and Safety

All cybersecurity learning and future testing activities will be conducted in a controlled lab environment or on systems for which explicit permission has been granted.

This project is intended for educational purposes and responsible cybersecurity practice.

### 12. Project Status

| Task | Status |
|---|---|
| VirtualBox installation and VM creation | Configured |
| Kali Linux ISO attached | Configured |
| CyberLab NAT Network created | Configured |
| Kali Linux installation | Requires confirmation |
| Graphical desktop | Requires confirmation |
| Static IP configuration | Planned |
| Network connectivity testing | Pending |
| Screenshot documentation | In progress |

### 13. Conclusion

Week 01 focuses on preparing a virtual cybersecurity lab using VirtualBox and Kali Linux. The project establishes the virtual machine configuration and the intended network architecture, while documenting installation issues and the remaining verification steps.

This lab will serve as a foundation for future cybersecurity learning, practical networking exercises, and ethical penetration-testing activities.

---

**Project:** NetworkWalks – Cybersecurity Internship, Week 01  
**Virtualization Platform:** Oracle VM VirtualBox 7.2  
**Operating System:** Kali Linux 2024.4  
**Repository:** `cybersecurity-pentesting-lab`
