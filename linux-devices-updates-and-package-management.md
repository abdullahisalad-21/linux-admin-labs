# Linux Devices, Updates, and Package Management – 2026-02-08

## Overview
Today’s Linux admin session focused on system introspection, device management, package installation and removal, and full system updates inside the Ubuntu VirtualBox environment. I inspected the `/dev` filesystem, analyzed character vs block devices, reviewed major/minor numbers, checked the running kernel, installed and removed software packages, and performed a complete system upgrade using APT. This session strengthened my understanding of Linux hardware abstraction, package management, and update workflows.

---

## Commands / Work Done

### Kernel and System Information
```bash
uname -r

Device Files and Hardware Abstraction
ls -l /dev

Package Management: Install, Inspect, Remove
sudo apt install gimp
apt show gimp
sudo apt remove gimp
sudo apt autoremove

System Update Operations
sudo apt update
sudo apt full-upgrade

Additional Tools and Help Commands
htop
apt --help
Additional Storage/Device Tools (reviewed conceptually)
lsblk
sudo fdisk -l

What I Learned
Linux Device Model
• 	Linux exposes hardware as files under .
• 	Character devices (c) handle byte-stream I/O (keyboards, terminals, random, hidraw).
• 	Block devices (b) handle block-based storage (HDDs, SSDs, USB drives).
• 	Device names like , ,  represent kernel-detected storage devices.
• 	Partitions follow numeric suffixes: , , etc.
• 	Major/minor numbers map device files to kernel drivers.
• 	Symbolic links in  (e.g., ) provide compatibility and convenience.
Package Management
• 	 installs software from trusted repositories.
• 	 displays package metadata, dependencies, and version info.
• 	 removes software while keeping configuration files.
• 	 cleans unused dependencies.
• 	 provides command usage and options.
• 	 is a real-time process and resource monitor.
System Updates
• 	 refreshes repository metadata.
• 	 installs new versions and resolves dependencies.
• 	Kernel updates require a reboot to activate.
• 	Linux updates are secure because repositories are signed and centrally maintained.

Scenario
Troubleshooting a Missing Storage Device
If a disk such as  does not appear:
1. 	Confirm kernel detection:
dmesg | grep sd
2. 	List block devices:
lsblk
3. 	Verify device file presence:
ls -l /dev
4. 	If still missing, check VirtualBox storage settings or physical connection.
