🐧 3. LINUX‑ADMIN REPO
Filename: cups-printing-basics.md

⭐ 1. Overview
This document covers Linux printing fundamentals using CUPS, including checking installation, managing print queues, and understanding Linux printing workflows.

🎯 2. Objectives
Check CUPS installation
Understand Linux printing architecture
Manage print queues
Compare Linux printing to Windows/macOS

🛠️ 3. Tools & Commands Used
dpkg -l | grep cups
systemctl status cups
lpstat -o
cancel -a


🧩 4. Steps Completed
Verified how to check CUPS installation
Reviewed Ubuntu print queue management
Reviewed print‑to‑file workflow
Reviewed network printing protocols (IPP, SMB, LPD)

🐞 5. Problems & Fixes
Problem
Fix
Needed to check CUPS presence
Used dpkg + systemctl


📚 6. What I Learned
CUPS is the core of Linux printing
Ubuntu supports IPP, SMB, LPD
Linux print queues can be managed via GUI or CLI

📎 7. Related Files
Daily Practice: 2026-3-12.md
Networking: network-printing-overview.md

🔜 8. Next Steps
Install CUPS if missing
Configure network printing
Test printing from Windows → Linux
