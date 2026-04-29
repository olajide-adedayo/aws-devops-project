# Project 2: EC2 + EBS Persistent Storage

## Overview
This project demonstrates how to attach and configure Amazon EBS storage on an EC2 instance and ensure data persistence.

## Steps Completed

- Created EBS volume (gp3, 2GB)
- Attached volume to EC2 instance
- Verified using lsblk
- Formatted disk using ext4 filesystem
- Mounted volume to /data
- Created test file to verify storage
- Configured auto-mount using /etc/fstab

## Key Commands

```bash
lsblk
sudo mkfs -t ext4 /dev/nvme1n1
sudo mkdir /data
sudo mount /dev/nvme1n1 /data
