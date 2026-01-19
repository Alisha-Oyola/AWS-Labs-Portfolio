# 🔐 AWS IAM Foundations: Secure Access Lab

![AWS](https://img.shields.io/badge/AWS-Cloud-orange) ![IAM](https://img.shields.io/badge/IAM-Access%20Management-blue) ![Security](https://img.shields.io/badge/Security-Best%20Practices-green)

## Overview
This lab demonstrates how to securely manage access in AWS using IAM best practices. The focus is on **least privilege**, eliminating root usage, and creating a **scalable access model** for future cloud environments.  

---

## What I Built
- Created an **IAM user** for daily operations (no root usage)  
- Built an **IAM group** with read-only permissions  
- Assigned the user to the group for inherited access  
- Created an **IAM role** for EC2 with read-only permissions  
- Wrote a **custom policy** for fine-grained S3 read-only access  
- Explored AWS **global vs regional services**  

**Problem Solved:** Provides a secure, scalable, and auditable access model that prevents over-permissioned users and enforces least privilege.

---

## Architecture Overview
     ┌─────────────┐
     │  IAM User   │
     └─────┬───────┘
           │
           ▼
     ┌─────────────┐
     │   IAM Group │
     │ (Read-Only) │
     └─────┬───────┘
           │
           ▼
     ┌─────────────┐
     │ IAM Role for│
     │    EC2      │
     └─────────────┘
---

## AWS Services Used
- **IAM:** Users, Groups, Roles, Policies  
- **AWS Console:** Region switching to observe global vs regional services  

---

## Key Design Decisions
- **Root Account Avoidance:** Daily operations via IAM user only  
- **Group-Based Permissions:** Policies attached to groups, not individuals  
- **Read-Only by Default:** Safer onboarding and audit-friendly  
- **Roles Over Keys:** Eliminates long-lived credentials, follows best practices  
- **Custom Policy:** Demonstrates fine-grained, least-privilege access  

---

## Challenges & Improvements
**Challenges:** Understanding policy inheritance, JSON syntax, and role vs user permissions.  

**Future Improvements:** Add MFA, attach IAM role to a live EC2 instance, introduce environment-specific roles.  
