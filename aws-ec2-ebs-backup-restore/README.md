# AWS EC2 Backup & Restore using EBS Snapshots

## Overview
This project demonstrates a practical disaster recovery scenario using Amazon EC2 and EBS snapshots. An EC2 instance was backed up using a snapshot and later restored by attaching the recovered volume to a new instance and mounting it within a Linux environment.

---

## Step 1 — EC2 Instance Running

![EC2](ec2-running.png)  
An EC2 instance was launched and verified to be in a running state with a public IP address.

**Learning:**  
Every EC2 instance is backed by an EBS root volume, which contains the operating system and application data.

---

## Step 2 — Snapshot Created

![Snapshot](snapshot-created.png)  
A snapshot of the EC2 instance’s EBS volume was created to capture a point-in-time backup.

**Learning:**  
EBS snapshots store both the data and filesystem, enabling full restoration of a volume.

---

## Step 3 — New EC2 Instance

![New EC2](new-ec2.png)  
A new EC2 instance was launched in the same Availability Zone as the restored volume.

**Learning:**  
EBS volumes are Availability Zone–specific and must be attached to instances within the same AZ.

---

## Step 4 — Volume Attached

![Volume](volume-attached.png)  
The restored EBS volume was attached to the new EC2 instance.

**Learning:**  
Attaching a volume makes it available to the instance, but it must be mounted within the OS before the data can be accessed.

---

## Step 5 — Disk Detection

![lsblk](lsblk.png)  
The `lsblk` command was used to identify the attached volume and its partition (`nvme1n1p1`).

**Learning:**  
Understanding the difference between a disk and its partition is essential. Filesystems are typically located on partitions rather than the raw disk.

---

## Step 6 — Volume Mounted

![Mounted](mounted-volume.png)  
The volume was mounted using the correct filesystem and mount options.

```bash
sudo mkdir -p /data
sudo mount -o nouuid -t xfs /dev/nvme1n1p1 /data
