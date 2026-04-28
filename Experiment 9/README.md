Experiment 9: Manual Management of Storage Devices in Linux

Aim:
  To understand and demonstrate how to identify storage devices in Linux, manually mount and unmount file systems, and comprehend the importance of mount points and device management in system administration and cybersecurity contexts.

Objective:
  1) Identify storage devices (hard disks, USB drives, external storage) in Linux.
  2) Manually mount and unmount file systems.
  3) Learn how Linux integrates storage devices into a unified directory structure.
  4) Understand implications for system administration and cybersecurity.
 
Theory:
  Linux represents hardware devices as files in the /dev directory:
   . /dev/sda, /dev/sdb – Hard disks
   . /dev/sda1, /dev/sdb1 – Disk partitions

Mount Points: Empty directories where devices are attached, e.g., /mnt or /media.

Unmounting Devices: Safely disconnects the device from the file system to prevent data corruption.

Key Commands:
| Command    | Description                     |
| ---------- | ------------------------------- |
| `lsblk`    | List block devices              |
| `fdisk -l` | Display disk partition info     |
| `mount`    | Mount a file system             |
| `umount`   | Unmount a file system           |
| `df -h`    | Display mounted file systems    |
| `mkdir`    | Create mount point              |
| `blkid`    | Display block device attributes |

Procedure:
Step 1: Identify Devices
  lsblk          # List all block devices
  sudo fdisk -l  # Display detailed disk info

Step 2: Create Mount Point
   sudo mkdir /mnt/usb

Step 3: Mount Device
   sudo mount /dev/sdb1 /mnt/usb
   df -h          # Verify mount
   mount

Step 4: Access Mounted Device
  cd /mnt/usb
  ls

Step 5: Unmount Device
   cd ~
  sudo umount /mnt/usb
  df -h          # Verify unmount

Observations / Results:

   1) Successfully identified all connected storage devices using lsblk and fdisk -l.
   2) Mounted and unmounted USB storage safely.
   3) Verified device accessibility and data integrity.

Conclusion:

   1) Learned to manually manage storage devices in Linux.
   2) Understood the concept of mount points and safe device removal.
   3) Gained practical understanding of Linux file system integration and its relevance to system administration and cybersecurity.
