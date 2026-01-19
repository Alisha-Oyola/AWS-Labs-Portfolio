# 🖥️ AWS EC2 Foundations: Compute & Storage Lab

![AWS](https://img.shields.io/badge/AWS-Cloud-orange) ![EC2](https://img.shields.io/badge/EC2-Compute-blue) ![EBS](https://img.shields.io/badge/EBS-Block%20Storage-green)

## Overview
This lab focuses on core EC2 operations and AWS compute fundamentals. The goal was to understand how virtual servers are provisioned, how storage is attached and managed, and how instance lifecycle actions impact availability and cost.

---

## What I Built
- Launched an **EC2 instance** using a selected instance type  
- Attached an **EBS volume** to the running instance  
- Created an **EBS snapshot** for backup and recovery  
- Stopped and restarted the instance to observe state behavior  

**Problem Solved:** Demonstrates how to provision compute resources, persist data independently of instances, and manage instance lifecycle safely.

---

## Architecture Overview
     ┌─────────────┐
     │   EC2       │
     │  Instance   │
     └─────┬───────┘
           │
           ▼
     ┌─────────────┐
     │   EBS       │
     │  Volume     │
     └─────┬───────┘
           │
           ▼
     ┌─────────────┐
     │ EBS Snapshot│
     └─────────────┘

---

## AWS Services Used
- **EC2:** Virtual compute instances  
- **EBS:** Persistent block storage  
- **EC2 Snapshots:** Point-in-time backups  

---

## Key Design Decisions
- **Instance Type Selection:** Balanced cost and performance based on workload needs  
- **EBS for Storage:** Ensures data persistence beyond instance lifecycle  
- **Snapshots for Backup:** Enables recovery and future volume creation  
- **Stop/Start Operations:** Validates instance state behavior and cost control  

---

## Key Concepts Learned
- How to choose appropriate **EC2 instance types**  
- Differences between **EBS, EFS, and Instance Store**  
- When to use **On-Demand, Spot, and Reserved Instances**  

---

## Challenges & Improvements
**Challenges:** Understanding storage persistence and instance state changes.  

**Future Improvements:** Automate provisioning with Terraform, test snapshot restores, compare performance across instance types.  

