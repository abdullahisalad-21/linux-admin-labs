# Linux Navigation and File Operations

## Overview
This lab covers essential Linux navigation and file management commands. These are the foundation of system administration and daily IT support tasks.

---

## 1. Navigation Commands

### `pwd`
Shows your current working directory.


### `ls`
Lists files and directories. 
ls ls -l ls -a

### `cd`
Moves between directories.

---

## 2. File and Directory Management

### Create a directory
mkdir projects

### Create an empty file
touch notes.txt

### Copy files
cp file1.txt file2.txt cp -r folder1 folder2

### Move or rename files
mv oldname.txt newname.txt mv file.txt /home/user/Document

### Delete files and directories
rm file.txt rm -r foldername

---

## 3. Viewing File Content

### `cat`
Displays file content.
cat notes.txt

### `less`
Scroll through long files.
less /var/log/syslog

### `head` and `tail`
head file.txt tail file.txt

---

## 4. What I Learned
- How to navigate the Linux filesystem  
- How to create, move, copy, and delete files  
- How to view file content  
- How to manage directories  
- How Linux paths work (absolute vs relative)

---

## 5. Next Steps
Move on to:
- Permissions and ownership  
- Users and groups  
- Searching and pipelines  
