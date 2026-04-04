# 1. Overview ⭐
Today I installed and reconfigured OpenLDAP (slapd) on Ubuntu as part of learning Linux directory services.

# 2. Objectives 🎯
- Install slapd and ldap-utils
- Reconfigure LDAP server
- Initialize directory structure
- Prepare for LDAP queries and user creation

# 3. Tools & Commands Used 🛠️
- sudo apt-get install slapd ldap-utils
- sudo dpkg-reconfigure slapd

# 4. Steps Completed 🧩
- Installed OpenLDAP server and utilities
- Observed creation of openldap system user
- Reconfigured slapd
- System backed up old config and created new directory
- LDAP directory initialized successfully

# 5. Problems & Fixes 🐞
No issues — installation and reconfiguration completed cleanly.

# 6. What I Learned 📚
- slapd installation initializes LDAP automatically
- dpkg-reconfigure rebuilds configuration
- LDAP uses hierarchical DN structure
- OpenLDAP is Linux’s directory service equivalent to AD DS

# 7. Related Files 📎
- /etc/ldap/slapd.d/
- /var/lib/ldap/

# 8. Next Steps 🔜
- Verify slapd service status
- Run ldapsearch queries
- Create OUs (People, Groups)
- Add users and groups via LDIF
