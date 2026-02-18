# 4) AWS Cloud basics (Ops-first)

## 4.1 IAM + least privilege

### Must understand

- User vs role

- Policies vs trust relationships

- “Deny by default” and grant only needed actions

### Lab

- Make a role for a service/task

- Prove it works with minimal permissions

- Add one missing permission and show the before/after error

**Measurable outcomes**

- ✅ You can explain the policy that fixed the error

---

## 4.2 VPC essentials + security groups

### Lab (core)

- VPC + public subnet + private subnet

- Launch EC2 in each

- Prove reachability expectations

- Break a route or SG and diagnose

**Measurable outcomes**

- ✅ You can fix “can’t connect” using a checklist (SG → route → DNS → service)

---

## 4.3 EC2/EBS/S3 basics

- EC2: AMI, instance types (concept), keypairs, user data basics

- EBS: attach volumes, snapshot concept

- S3: buckets, permissions, use for logs/artifacts

**Measurable outcomes**

- ✅ You can back up (snapshot) and restore basic data confidently

---

## 4.4 Observability: CloudWatch + CloudTrail

### CloudWatch

- Basic metrics + alarms + dashboards

- Logs ingestion (agent or app logs)

### CloudTrail

- Investigate “who changed what”

**Measurable outcomes**

- ✅ You can create an alarm that triggers during a drill

- ✅ You can locate a config change in CloudTrail

---
