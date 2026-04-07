
# AWS EC2 Backup & Restore using EBS Snapshots

## Overview
This project shows how I backed up an EC2 instance using an EBS snapshot and restored the data by attaching the restored volume to a new EC2 instance.

## Steps
1. Created an EC2 instance
2. Created a snapshot of its EBS volume
3. Created a new volume from the snapshot
4. Launched a new EC2 instance in the same Availability Zone
5. Attached the restored volume
6. Connected with EC2 Instance Connect
7. Mounted the restored partition in Linux
8. Verified the recovered data

## Commands Used

```bash
lsblk
sudo mkdir -p /data
sudo mount -o nouuid -t xfs /dev/nvme1n1p1 /data
ls /data
