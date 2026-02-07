# Linux Package Management (.deb Installation)

## Overview
This lab covers how to manually install `.deb` software packages in Ubuntu using `dpkg`, 
how to fix dependency issues using `apt`, and how to troubleshoot common installation errors. 
These skills are essential for Linux system administration and real IT support scenarios.

---

## 1. Downloading .deb Packages

### Using wget
When a URL contains `?` or `&`, it must be wrapped in quotes.

```bash
wget "https://discord.com/api/download?platform=linux&format=deb" -O discord.deb
Example for VSCodium:
wget https://github.com/VSCodium/vscodium/releases/download/1.108.20787/codium_1.108.20787_amd64.deb

2. Installing Packages with dpkg
sudo dpkg -i codium_1.108.20787_amd64.deb
Expected behavior
- Installs the package directly
- Does not resolve dependencies
- Shows errors if required libraries are missing

3. Fixing Dependency Problems
sudo apt --fix-broken install
APT will:
- Detect broken packages
- Download missing dependencies
- Complete the installation

4. Verifying Installation
codium --version
codium

5. Common Errors and Fixes
File not found
Caused by:
- Wrong filename
- Wrong extension (.dep instead of .deb)
- Wrong architecture (amd644 instead of amd64)
Fix:
ls
404 Not Found
Cause:
- Incorrect GitHub release filename
Fix:
- Use exact versioned .deb from release page
URL parsing error
Cause:
- Shell splits URL at ? and &
Fix:
wget "<URL>" -O file.deb
Dependency errors
Fix:
sudo apt --fix-broken install

What I Learned
- How to manually install .deb packages
- How dpkg and apt work together
- How to fix dependency issues
- How to correctly download packages with wget
- How to troubleshoot installation errors
- Why Linux requires exact filenames

Next Steps
- Practice removing packages
- Learn how to add APT repositories
- Explore Snap and Flatpak installation methods
