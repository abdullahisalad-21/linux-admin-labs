🗂️ 1. Overview
Today’s session focused on Linux disk management, covering:
• 	Virtual disk creation in VirtualBox
• 	Disk attachment and verification
• 	Partition table creation (GPT)
• 	Partition creation
• 	Filesystem creation (ext4)
• 	Mounting and unmounting
• 	UUID identification
• 	Understanding lost+found
• 	Troubleshooting mount errors
This lab strengthens my Linux administration foundation and directly supports your CompTIA A+, Google IT Support, and real-world helpdesk skills.
🎯 2. Objectives
- Understand how Linux detects and manages block devices
- Create and attach a new virtual disk
- Use parted to create GPT partition tables
- Create partitions with precise size control
- Format partitions using mkfs.ext4
- Mount and unmount filesystems safely
- Identify filesystems using blkid
- Interpret system directories like lost+found
- Troubleshoot mount point errors
🛠️ 3. Tools & Commands Used
VirtualBox
• 	Disk creation
• 	Disk attachment
• 	Storage controller configuration
Linux Commands:
lsblk
sudo parted -l
sudo parted /dev/sdb
mklabel gpt
mkpart primary ext4 1MiB 5GiB
mkpart primary ext4 1MiB 100%
sudo mkfs -t ext4 /dev/sdb1
mkdir ~/USB
sudo mount /dev/sdb1 ~/USB
sudo umount ~/USB
sudo blkid
df -h
🧱 4. Steps Completed
4.1 Creating a New Virtual Disk (8GB)
- Opened VirtualBox → Storage → Add Disk
- Selected Create (not Add)
- Chose VDI, dynamically allocated
- Set size to 8GB
- Attached the disk under SATA controller
- Verified both disks were attached
Result:
/dev/sda = OS disk
/dev/sdb = new empty disk

4.2 Verifying Disk Detection in Linux
lsblk
sudo parted -l
Output showed:
- /dev/sda → existing Ubuntu disk
- /dev/sdb → 8GB disk with unknown partition table
4.3 Creating a GPT Partition Table
Inside parted:
sudo parted /dev/sdb
(parted) mklabel gpt
Verified with:
(parted) print
Partition table changed from unknown → gpt.
4.4 Creating a Partition
You created a 5GB partition:
(parted) mkpart primary ext4 1MiB 5GiB
This produced:
Number  Start   End     Size     File system  Name
1       1049kB  5369MB  5368MB   ext4         primary
  4.5 Formatting the Partition (ext4)
  sudo mkfs -t ext4 /dev/sdb1
  Linux created:
• 	Blocks
• 	Inodes
• 	Journal
• 	Superblock backups
• 	UUID
4.6 Mounting the Filesystem
Created mount point:
mkdir ~/USB
Mounted:
sudo mount /dev/sdb1 ~/USB
Verified:
ls ~/USB
Output:
lost+found
4.7 Understanding lost+found
• 	Automatically created by ext4
• 	Used for filesystem recovery
• 	Normal and expected
• 	Should not be deleted
4.8 Unmounting the Filesystem
  sudo umount ~/USB
  Silent success (Linux prints nothing when unmount works).
  4.9 Identifying Filesystem UUID
  sudo blkid
  Output included:
  /dev/sdb1: UUID="4e946f26-09fd-469f-9e45-039d9f8f01ad" TYPE="ext4"
  UUID is used for /etc/fstab automatic mounting.
🧩 5. Problems & Fixes
  Problem:
   mount: /my-usb/: mount point does not exist.

  Cause:
  Mount point directory was not created.
  Fix:
  mkdir ~/USB
  sudo mount /dev/sdb1 ~/USB
Problem:
  umount: /dev/sdb1: not mounted.
 Cause:
 I already unmounted it successfully.
 Fix:
 No action needed.
📘 6. What I Learned
- How Linux identifies disks (lsblk, parted -l)
- Difference between disk, partition, and filesystem
- How GPT works
- How to create partitions with precise size
- How ext4 filesystems are structured
- Why lost+found exists
- How to mount/unmount safely
- How UUIDs ensure reliable mounting
- How to troubleshoot mount errors
This is foundational sysadmin knowledge.
📎 7. Related Files
- ~/USB/ (mount point)
- /dev/sdb1 (new partition)
- VirtualBox disk: Ubuntu-22.04_1.vdi

🚀 8. Next Steps
- Practice creating multiple partitions
- Add /dev/sdb1 to /etc/fstab using UUID
- Explore filesystem repair tools (fsck)
- Practice LVM (Logical Volume Manager)
