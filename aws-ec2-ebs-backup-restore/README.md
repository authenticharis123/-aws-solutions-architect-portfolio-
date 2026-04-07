# AWS EC2 Backup & Restore using EBS Snapshots

## Overview
This project demonstrates how to back up and restore an EC2 instance using EBS snapshots.

---

## Step 1 — EC2 Instance Running

![EC2](ec2-running.png)
The EC2 instance was launched and running successfully.

---

## Step 2 — Snapshot Created

![Snapshot](snapshot-created.png)
A snapshot of the EBS volume was created.

---

## Step 3 — New EC2 Instance

![New EC2](new-ec2.png)
A new EC2 instance was launched in the same Availability Zone.

---

## Step 4 — Volume Attached

![Volume](volume-attached.png)
The restored volume was attached to the new EC2 instance.

---

## Step 5 — Disk Check

![lsblk](lsblk.png)
The volume was detected using the lsblk command.

---

## Step 6 — Volume Mounted

![Mounted](mounted-volume.png)
The volume was mounted using the correct filesystem.

---

## Step 7 — Data Recovered

![Recovered](recovered-data.png)
The original data was successfully recovered.
