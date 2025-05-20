# Create and Configure Storage Services and Upload Files Using Amazon EBS, EFS, and S3

---

## Overview

This experiment focuses on practical usage of AWS storage services — Elastic Block Store (EBS), Elastic File System (EFS), and Simple Storage Service (S3). You will learn how to attach extra EBS volumes, create snapshots, mount EFS shared file systems between multiple EC2 instances, and manage files across regions.

---

## Part 1: Attach and Mount Extra EBS Volume to Linux EC2 Instance

In this section, you extend an existing EC2 instance with an additional 10GB EBS volume, format, and mount it for use.

### Key Activities:

- Access the AWS Academy Learner Lab and launch your EC2 instance.
- Create a new 10GB EBS volume in the same Availability Zone as your EC2 instance.
- Attach the new volume to the EC2 instance.
- Connect via EC2 Instance Connect or SSH, and identify the new volume.
- Partition and format the volume with the XFS filesystem.
- Create a mount point directory (named after your Roll No).
- Mount the EBS volume to the created directory.
- Verify mounting and storage availability using `df -h`.

---

## Part 2: File Operations on EBS, Snapshot Creation, and Cross-Region Volume Attachment

This part involves working with files on the attached EBS volume, snapshotting the volume, and attaching the snapshot-based volume to an EC2 instance in a different AWS region.

### Key Activities:

- Create files (e.g., Python script, Java file) inside your mounted EBS directory.
- Launch a new EC2 instance in a different region (e.g., Oregon) with default storage.
- Create a snapshot of your original 10GB EBS volume.
- From the snapshot, create a new volume.
- Attach this volume to your new EC2 instance.
- Mount and access the volume on the new instance to verify files have been preserved across regions.

---

## Part 3: Amazon Elastic File System (EFS) – Shared Storage Between Multiple EC2 Instances

Learn to create a scalable, serverless, elastic shared file system with Amazon EFS, accessible from multiple EC2 instances simultaneously.

### Key Concepts:

- EFS uses NFS protocol and supports multiple clients concurrently.
- No provisioning needed; elastic capacity grows/shrinks automatically.
- Ideal for sharing data between distributed EC2 instances.
- Works with Linux-based instances only (no Windows support).

### Key Activities:

- Create two EC2 instances (e.g., Rollno-KMIT and Rollno-NGIT).
- Create a security group allowing NFS (port 2049) traffic.
- Create an EFS file system with default or customized settings.
- Attach security group and configure network access for EFS.
- Install `amazon-efs-utils` on both EC2 instances.
- Create mount directories (e.g., RollNo-EBS1, RollNo-EBS2).
- Mount the EFS filesystem on both instances using the NFS mount command.
- Verify mount with `df -h` and create files to test shared access.
- Demonstrate file sharing by accessing data from either instance.

---

## Summary

- **Amazon EBS**: Block-level storage attached to a single EC2 instance; requires formatting and mounting.
- **Snapshots**: Point-in-time backups of EBS volumes that can be restored or attached in other regions.
- **Amazon EFS**: Managed, scalable file storage accessible concurrently by multiple EC2 instances via NFS.
- **File Operations**: Creating, editing, and verifying files across volumes and shared file systems ensure data integrity and accessibility.

---

## Helpful Commands Overview

```bash
# Switch to root user
sudo su -

# List all block devices
lsblk

# Partition disk (e.g., /dev/xvdf)
fdisk /dev/xvdf

# Create filesystem (XFS)
mkfs -t xfs /dev/xvdf

# Create mount directory (replace Rollno)
mkdir -p /Rollno

# Mount volume
mount /dev/xvdf /Rollno

# Verify mounted file systems
df -h

# List files in mount directory
ls -lart /Rollno/

# Check file system on device
file -s /dev/xvdf
```
