# Linux Filesystem Repair & Disk Usage

## Overview
This documentation covers Linux disk‑usage analysis and filesystem repair using df, du, fsck, and ncdu. 
The session focused on ext4 journaling, safe repair procedures, and identifying large directories.

## Objectives
- Understand ext4 journaling  
- Practice df and du for disk analysis  
- Learn safe fsck usage  
- Install and use ncdu  
- Identify large directories  

## Tools & Commands Used
- df -h, df  
- du -h, du  
- du -h ~ | sort -h | tail  
- sudo du -xh / | sort -h | tail  
- sudo fsck  
- ncdu  

## Steps Completed
1. Analyzed filesystem usage with df  
2. Inspected directory sizes with du  
3. Identified largest directories using pipelines  
4. Installed ncdu  
5. Attempted fsck on mounted root and learned why it aborts  
6. Reviewed safe fsck usage and partition‑level repair  

## Problems & Fixes
- **fsck aborted on mounted filesystem** → Learned correct safe workflow  
- **fsck /dev/sda danger** → Understood why it destroys disks  

## What I Learned
- df vs du (filesystem vs directory)  
- ext4 journaling behavior  
- Why fsck cannot run on mounted filesystems  
- Why fsck must target partitions  
- How to identify large directories  
- ncdu for interactive analysis  

## Related Files
- ncdu installation  
- du and df outputs  

## Next Steps
- Use ncdu to clean unnecessary files  
- Practice fsck in recovery mode  
- Explore ext4 metadata repair  
