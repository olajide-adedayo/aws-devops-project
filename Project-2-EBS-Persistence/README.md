# 🚀 AWS DevOps Project 2: EBS Persistent Storage

## 📌 Project Overview
This project demonstrates how to configure persistent block storage using Amazon Elastic Block Store (EBS) with an EC2 instance.

It simulates a real-world scenario where application data must persist even after instance reboot.

---

## 🎯 Objectives
- Create and attach an EBS volume to EC2  
- Format the volume using ext4 filesystem  
- Mount the volume to a directory  
- Configure automatic mounting using /etc/fstab  
- Validate persistence after configuration  

---

## ⚙️ Implementation Steps

### 1. Check Attached Disk
```bash
lsblk

Format Disk:
sudo mkfs -t ext4 /dev/nvme1n1

Create Mount Point:
sudo mkdir /data

Mount Volume:
sudo mount /dev/nvme1n1 /data

Verify Mount:
df -h

Test Storage:
cd /data
sudo touch testfile.txt
ls

## Persistent Storage Configuration

Get UUID:
sudo blkid

Edit fstab file:
sudo nano /etc/fstab

Add this line to /etc/fstab:
UUID=3e3ee1e4-2585-424e-a820-b569ef9dbb58  /data  ext4  defaults,nofail  0  2

Validate Configuration:
sudo mount -a
(No output = success)

## 🧠 Key Concepts
- Amazon EBS (Elastic Block Store)
- Persistent vs ephemeral storage
- Linux filesystem (ext4)
- Mounting and disk management
- UUID-based configuration

## 🌍 Real-World Use Case
EBS is used in production systems for:
- Database storage
- Application data persistence
- Log storage
- File systems requiring durability

## 🏁 Outcome
Successfully configured persistent storage on AWS EC2 using EBS with proper Linux setup and validation.

