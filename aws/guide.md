# AWS Learning Plan

## Goal
Build practical AWS operations skills to deploy, secure, monitor, and troubleshoot cloud infrastructure.

## Time Commitment
- 8 weeks
- 5 sessions per week
- 60 to 90 minutes per session

## Prerequisites
- AWS account with billing alerts enabled
- IAM user for learning plus MFA
- AWS CLI configured locally

## Week 1: IAM Foundations and Access Control
### Focus
- IAM users, groups, roles, and policies
- Trust policy vs permissions policy
- Least privilege and temporary credentials

### Labs
1. Create a role for EC2 and attach minimal S3 read permissions.
2. Trigger an `AccessDenied` error, then fix with smallest policy change.
3. Enable MFA and test role assumption via CLI.

### Done Criteria
- You can explain why access is denied and which policy fixed it.
- You avoid admin-wide permissions for service tasks.

## Week 2: VPC, Subnets, Routes, Security Groups
### Focus
- VPC design basics
- Public vs private subnets
- Route tables, IGW, NAT, security groups, NACL concepts

### Labs
1. Build one VPC with one public and one private subnet.
2. Launch EC2 in both and validate expected connectivity.
3. Break route or security group and diagnose with checklist.

### Done Criteria
- You can isolate connectivity failures quickly.
- You can predict reachability before testing.

## Week 3: EC2 Operations
### Focus
- AMIs, instance families, key pairs, user data
- EBS volume types and snapshot basics
- Safe patching and reboot behavior

### Labs
1. Launch EC2 with user data installing a web service.
2. Attach a second EBS volume, mount it, and persist in `/etc/fstab`.
3. Create and restore from an EBS snapshot.

### Done Criteria
- You can boot, configure, and recover an EC2 host end to end.

## Week 4: S3 and Data Handling
### Focus
- Bucket policies vs IAM policies
- Versioning, lifecycle, and encryption basics
- S3 for logs, artifacts, and backups

### Labs
1. Create a private bucket with versioning and lifecycle rules.
2. Upload deployment artifacts and verify access boundaries.
3. Simulate accidental deletion and recover with versioning.

### Done Criteria
- You can secure and recover data in S3 confidently.

## Week 5: Load Balancing and Auto Scaling
### Focus
- ALB target groups and health checks
- Auto Scaling groups and launch templates
- Multi-AZ reliability concepts

### Labs
1. Put two EC2 instances behind an ALB.
2. Configure health checks and simulate unhealthy instance behavior.
3. Scale out under load and observe traffic distribution.

### Done Criteria
- You can maintain service availability during instance failure.

## Week 6: Observability with CloudWatch and CloudTrail
### Focus
- Metrics, logs, alarms, and dashboards
- Event tracing with CloudTrail
- Alert quality and noisy-alert reduction

### Labs
1. Create alarms for CPU, status checks, and HTTP 5xx.
2. Forward app/system logs to CloudWatch Logs.
3. Identify who changed a security group using CloudTrail.

### Done Criteria
- You can investigate "what changed, when, and by whom".
- You can create alerts that trigger during drills.

## Week 7: Backup, Recovery, and Cost Basics
### Focus
- Backup planning: EBS snapshots and S3 lifecycle
- Recovery objectives (RPO/RTO) at a practical level
- Basic cost controls and tagging strategy

### Labs
1. Define backup schedule and retention for one service.
2. Perform a restore drill from backup.
3. Add cost allocation tags and review spend by tag.

### Done Criteria
- You can execute a basic restore with documented steps.

## Week 8: Final AWS Project
### Project Scope
Deploy a production-style baseline:
- VPC with public/private subnets
- ALB + Auto Scaling web tier
- IAM least-privilege roles
- CloudWatch alarms and log visibility
- Backup and restore runbook

### Deliverables
- Architecture diagram
- Deployment steps
- Troubleshooting checklist
- One incident simulation report

## Mastery Checklist
- I can deploy secure and reachable infrastructure in AWS.
- I can debug IAM, networking, and EC2 failures without guessing.
- I can monitor and recover services with documented procedures.
