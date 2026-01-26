The Nautilus DevOps team needs to expand the storage capacity of an existing virtual machine and add an additional data disk to support increased workloads. This task requires resizing the existing VM disk and mounting a new data disk to the VM.

As a member of the team, perform the following steps:

1) Expand the existing VM devops-vm disk from 32Gi to 64Gi.

2) Also create a new standard HDD data disk named devops-disk of 64Gi and mount the disk to VM devops-vm at location /mnt/devops-disk.

Approach:
1. Stop the VM, resize the OS disk to 32 GiB to 64 GiB.
2. Create the data disk with 64 GiB (Standard_HDD) and attach this disk to VM.
3. SSH into VM from Azure client Host.
4. See the data disk
   ```
   lsblk

   o/p:
   NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
   loop0     7:0    0 63.8M  1 loop /snap/core20/2686
   loop1     7:1    0 91.4M  1 loop /snap/lxd/36918
   loop2     7:2    0 50.9M  1 loop /snap/snapd/25577
   sda       8:0    0   64G  0 disk 
   ├─sda1    8:1    0 63.9G  0 part /
   ├─sda14   8:14   0    4M  0 part 
   └─sda15   8:15   0  106M  0 part /boot/efi
   sdb       8:16   0    4G  0 disk 
   └─sdb1    8:17   0    4G  0 part /mnt
   sdc       8:32   0   64G  0 disk
   ```
5. Create filesystem for new disk
   ```
   mkfs.ext4 /dev/sdc
   ```
6. Create folder called devops-disk inside the /mnt folder
   ```
   mkdir -p /mnt/devops-disk
   ```
7. Mount the sdc disk
   ```
   mount /dev/sdc /mnt/devops-disk

   # sdc will looks to devops-disk folder to store the data
   ```
