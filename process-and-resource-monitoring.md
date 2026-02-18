# 🐧 Process and Resource Monitoring in Linux

## ⭐ 1. Overview
This documentation covers Linux process inspection, resource monitoring tools, and the `/proc` filesystem. It explains how Linux exposes system information and how to identify CPU, memory, and disk bottlenecks.

## 🎯 2. Objectives
- Monitor processes using `ps`, `top`, `htop`, and `pstree`  
- Explore `/proc` for process metadata  
- Identify high‑CPU and high‑memory processes  
- Practice killing processes safely  
- Understand Linux resource monitoring tools  

## 🛠️ 3. Tools & Commands Used
- `ps -ef`, `ps aux`
- `grep`
- `pstree -p`
- `kill`, `kill -KILL`, `pkill`
- `/proc/<PID>/status`
- `/proc` exploration
- `free -h`
- `df -h`
- `iostat`
- `iotop`

## 🧪 4. Steps Completed
- Listed all processes using `ps -ef`  
- Sorted processes by CPU/memory using `ps aux --sort`  
- Viewed parent/child relationships with `pstree -p`  
- Inspected `/proc/<PID>/status`  
- Killed Firefox using:
  ```
  pkill -9 firefox
  ```
- Completed supplemental reading on Linux resource monitoring  

## 🐞 5. Problems & Fixes
- ❗ Many Firefox processes →
- Fix: used `pkill -9 firefox`  
- ❗ Unclear parent process →
- Fix: used `pstree -p`  

## 📚 6. What I Learned
- Linux exposes process info through `/proc`  
- `ps`, `top`, and `htop` read from `/proc`  
- `pstree` visualizes parent/child relationships  
- `free`, `df`, `iostat`, and `iotop` are essential for diagnostics  
- Killing processes requires understanding process groups  

## 📎 7. Related Files
- Linux terminal screenshots  
- Supplemental reading summaries  

## 🔜 8. Next Steps
- Document Linux memory management  
- Practice `htop` and `iotop`  
- Explore systemd service monitoring (`systemctl status`)  
