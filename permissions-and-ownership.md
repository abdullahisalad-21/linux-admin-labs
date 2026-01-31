# Linux Permissions and Ownership

## Overview
This lab covers Linux file permissions, ownership, and how to modify them using `chmod`, `chown`, and `chgrp`.

---

## 1. Viewing Permissions

### `ls -l`
Shows permissions, owner, group, size, and date.


---

## 2. Permission Types

- **r** = read  
- **w** = write  
- **x** = execute  

Three permission groups:
- **u** = user  
- **g** = group  
- **o** = others  
chmod u+x script.sh chmod g-w file.txt chmod o+r notes.txt

---

### Numeric mode
chmod 755 script.sh chmod 644 file.txt
------------

---

## 4. Changing Ownership

### Change file owner
sudo chown abdullahi file.txt

### Change owner and group
sudo chown abdullahi:admins file.txt

---

## 5. Changing Group Ownership
sudo chgrp admins file.txt

---

## 6. What I Learned
- How Linux permissions work  
- Difference between symbolic and numeric modes  
- How to change file ownership  
- How to manage group ownership  
## 3. Changing Permissions

### Symbolic mode


## Scenario: User cannot run a script

A user reported that they could not run a script called `backup.sh`.  
I checked the permissions using:

ls -l backup.sh

The file had no execute permission.  
I fixed it using:

chmod u+x backup.sh

The user was then able to run the script successfully.
