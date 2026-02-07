
---

# ✅ **2. linux-admin-lab-2026-02-07.md**

```markdown
# Linux Admin Lab — Package Management & Dependencies

## Overview
This lab focused on installing `.deb` packages, resolving dependencies, and understanding how Linux package managers work. I practiced using `wget`, `apt`, `dpkg`, `7z`, and TAR.

---

## Commands / Work Done
```bash
wget "https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb"
sudo apt install ./google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo apt --fix-broken install

7z e file.zip
7z x file.zip

tar -cvf archive.tar folder/
tar -xvf archive.tar
tar -tvf archive.tar

What I Learned
• 	APT performs dependency resolution; DPKG does not.
• 	Missing dependencies cause installation failures.
• 	Older  files may require deprecated libraries.
• 	TAR is used for packaging and backups.
• 	Archive extraction behavior changes depending on flags.

Scenarios
• 	Installing proprietary software not in Ubuntu repositories.
• 	Fixing broken installations caused by missing dependencies.
• 	Extracting archives for system recovery.
• 	Packaging directories using TAR.
