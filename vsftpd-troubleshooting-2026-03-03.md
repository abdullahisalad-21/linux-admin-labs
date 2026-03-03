🐧 Linux‑Admin — March 3, 2026
📘 Overview
This session focused on diagnosing and repairing a broken vsftpd service. The daemon was crashing immediately with exit code 2, preventing both control and data channel operations. I used systemctl, journalctl, and configuration inspection to isolate the root cause: a missing write_enable=YES directive required for local user access. After correcting the configuration, I restarted the service, verified that port 21 was listening, and confirmed successful directory listing using lftp. This workflow strengthened my ability to troubleshoot Linux services using logs, ports, and configuration validation.
🎯 Objectives
• Identify why vsftpd was crashing
 • Use logs to trace daemon failures
 • Validate FTP behavior using lftp
 • Restore service functionality
 • Strengthen Linux troubleshooting workflow
🛠️ Tools & Commands Used
systemctl status vsftpd
journalctl -u vsftpd
nl -ba /etc/vsftpd.conf
sudo ss -tulpn | grep :21
lftp localhost
📝 Steps Completed
1. Service Failure Detection
vsftpd was failing with exit code 2. This indicated a configuration error.
2. Log Analysis
Using journalctl, I identified the exact failure: INVALIDARGUMENT, confirming a missing or invalid directive.
3. Config Inspection
I reviewed the entire vsftpd configuration and found that write_enable=YES was commented out.
4. Fixing the Configuration
I enabled the directive and restarted the service successfully.
5. Verifying Port 21
Using ss, I confirmed that vsftpd was now listening on port 21.
6. Testing with lftp
Directory listing succeeded, confirming full FTP functionality.
🧩 Problems & Fixes
Problem: vsftpd crashed on startup
 Fix: Enabled write_enable=YES
Problem: lftp hung on directory listing
 Fix: Restored port 21 listener
📚 What I Learned
How to interpret exit codes
How to use logs to diagnose service failures
How FTP behaves when the data channel is broken
How configuration directives impact daemon startup
🔗 Resources Used
/etc/vsftpd.conf
Linux documentation
