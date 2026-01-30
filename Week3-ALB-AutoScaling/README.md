High Availability & Auto Scaling Lab








Overview

This lab focuses on designing highly available and fault-tolerant compute architectures using AWS managed services. The goal was to understand how traffic is distributed across instances, how capacity scales automatically based on demand, and how AWS replaces unhealthy resources without manual intervention.

What I Built

Created an Application Load Balancer (ALB) to distribute HTTP traffic

Defined a Launch Template for standardized EC2 provisioning

Configured an Auto Scaling Group (ASG) across multiple Availability Zones

Attached the ASG to a Target Group with health checks

Implemented a dynamic scaling policy based on load

Manually terminated an instance to validate self-healing behavior

Problem Solved:
Demonstrates how to design a resilient compute layer that automatically scales with demand and recovers from instance failures without downtime.

Architecture Overview
        Internet
            │
            ▼
 ┌─────────────────────┐
 │ Application Load    │
 │ Balancer (ALB)      │
 └─────────┬───────────┘
           │
           ▼
 ┌─────────────────────┐
 │ Target Group        │
 │ (Health Checks)     │
 └─────────┬───────────┘
           │
           ▼
 ┌─────────────────────┐
 │ Auto Scaling Group  │
 │  (Multi-AZ)         │
 └───────┬───────┬─────┘
         │       │
         ▼       ▼
     EC2 Instance  EC2 Instance

AWS Services Used

EC2: Compute instances launched automatically by the ASG

Application Load Balancer (ALB): Distributes incoming HTTP traffic

Auto Scaling Group (ASG): Maintains desired capacity and replaces unhealthy instances

Launch Templates: Defines instance configuration and bootstrap behavior

Target Groups: Routes traffic based on health checks

Key Design Decisions

Application Load Balancer over Classic/Network LB
Enables Layer 7 routing and advanced health checks.

Launch Template Usage
Preferred over deprecated Launch Configurations.

Multi-AZ Auto Scaling Group
Improves availability and fault tolerance.

Dynamic Scaling Policy
Automatically adjusts capacity based on demand instead of manual scaling.

Health Check Integration
Ensures only healthy instances receive traffic.

Key Concepts Learned

How ALB, Target Groups, and ASGs work together

Difference between scaling and self-healing

Why AWS favors horizontal scaling

How health checks control traffic flow

How dynamic scaling policies respond to load changes

Validation & Testing

Verified traffic flow using the ALB DNS name

Confirmed instances were marked Healthy in the target group

Manually terminated an EC2 instance and observed:

Automatic termination detection

New instance launch

Traffic continuity

Adjusted desired capacity to validate scale-out and scale-in behavior

Challenges & Improvements

Challenges:
Understanding how health checks, scaling policies, and instance replacement interact in real time.

Future Improvements:

Add HTTPS with ACM certificates

Implement path-based routing

Integrate CloudWatch alarms for scaling visibility

Extend architecture with a database backend
