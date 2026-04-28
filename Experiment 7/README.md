# Experiment 7: 

Title:
User and Group Management in Linux with File Ownership and Permission Control

## Aim
To create, modify, and manage users and groups in Linux, understand file ownership and permissions, and implement secure file sharing.

## Theory
Linux uses users (UID), groups, chown, chgrp, chmod and sticky bit for access control.

## Commands Used
| Command     | Description |
|-------------|-------------|
| useradd     | Create user |
| passwd      | Set password |
| groupadd    | Create group |
| usermod     | Add to group |
| chown       | Change owner |
| chgrp       | Change group |
| chmod       | Permissions |
| groups      | Show groups |

## Step-by-Step Procedure
1. `sudo useradd testuser && sudo passwd testuser`
2. `id testuser`
3. `sudo groupadd testgroup`
4. `sudo usermod -aG testgroup testuser`
5. `groups testuser`
6. `mkdir shared_dir && sudo chgrp testgroup shared_dir && sudo chmod 770 shared_dir`
7. `sudo chmod +t shared_dir`
8. `sudo chown testuser:testgroup shared_file.txt` (if created)

## Configuration Commands
sudo useradd testuser
sudo passwd testuser
id testuser
sudo groupadd testgroup
sudo usermod -aG testgroup testuser
groups testuser
mkdir shared_dir
sudo chgrp testgroup shared_dir
sudo chmod 770 shared_dir
sudo chmod +t shared_dir

Outcomes: 
 ✓ Understand the concept of multi-user systems in Linux. 
 ✓ Create, modify, and delete users using commands like useradd, usermod, and userdel. 
 ✓ Create and manage groups using groupadd, groupmod, and groupdel. 
 ✓ Assign users to primary and supplementary groups. 
 ✓ Understand Linux file ownership (user, group, others). 
 ✓ Modify file permissions using chmod, chown, and chgrp. 
 ✓ Implement secure file sharing using group permissions. 
 ✓ Apply security best practices to prevent unauthorized access. 
 ✓ Interpret permission notations (symbolic and numeric modes). 
 ✓ Enforce access control policies in a multi-user environment. 
 
Result: 
 ❖ Successfully created and managed multiple users and groups in a Linux system. Assigned 
    appropriate file ownership and group permissions to control access to system resources. 
    Demonstrated secure file sharing between users using group-based permission management 
    and verified access restrictions to prevent unauthorized usage. 
