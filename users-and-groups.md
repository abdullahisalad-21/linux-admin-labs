# Linux Users and Groups

## Overview
This lab covers creating, modifying, and managing users and groups in Linux.

---

## 1. Creating Users

### `useradd`
sudo useradd john

### `adduser` (interactive)
sudo adduser john

---

## 2. Setting Passwords
sudo passwd john

---

## 3. Creating Groups
sudo groupadd developers

---

## 4. Adding Users to Groups
sudo usermod -aG developers john

---

## 5. Deleting Users
sudo deluser john

---

## 6. What I Learned
- How Linux stores user info in `/etc/passwd`  
- How groups work in `/etc/group`  
- How to add/remove users  
- How to assign group membership  
