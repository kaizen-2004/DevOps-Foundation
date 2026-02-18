# Linux Learning Plan

## Goal
Build Linux operations skills to support and troubleshoot real services in production-like environments.

## Time Commitment
- 6 weeks
- 5 sessions per week
- 60 to 90 minutes per session

## Prerequisites
- One Linux VM (Ubuntu or Amazon Linux)
- A non-root user with `sudo`
- Notes folder in this repo for commands, mistakes, and fixes

## Week 1: Shell, Filesystem, and Package Basics
### Focus
- Filesystem layout: `/etc`, `/var`, `/home`, `/opt`, `/tmp`
- Navigation and text tools: `ls`, `cd`, `find`, `grep`, `awk`, `sed`
- Package management: `apt` or `dnf` basics

### Labs
1. Install and remove one package safely.
2. Locate config files for SSH and your shell.
3. Extract only `ERROR` lines from a sample log file.

### Done Criteria
- You can explain where config, logs, and app data usually live.
- You can search files quickly with one command pipeline.

## Week 2: Processes, Services, and Boot
### Focus
- Process lifecycle and signals
- `systemd` units and restart policies
- Startup behavior (`enable` vs `start`)

### Labs
1. Create a simple script and run it as a `systemd` service.
2. Break the service with a bad path, then debug and fix it.
3. Compare `ps`, `top`/`htop`, and `systemctl status` outputs.

### Done Criteria
- You can recover a failed service using `journalctl` evidence.
- You can describe why a service does or does not start at boot.

## Week 3: Logs and Troubleshooting Workflow
### Focus
- `journalctl` and `/var/log/*`
- Log levels and noisy vs actionable logs
- Repeatable troubleshooting method

### Labs
1. Trigger three failures (bad permissions, bad env var, wrong port).
2. Capture proof from logs for each failure.
3. Write a short runbook: symptom, checks, fix, prevention.

### Done Criteria
- You can produce a timeline of events from logs.
- You can avoid guessing by validating hypotheses quickly.

## Week 4: Users, Groups, Permissions, SSH
### Focus
- Ownership and mode bits (`rwx`)
- `sudo` least-privilege mindset
- SSH key-based access and hardening basics

### Labs
1. Create a user and group model for a service account.
2. Reproduce a `Permission denied` issue and fix it with minimal changes.
3. Configure SSH keys and disable password login in a lab VM.

### Done Criteria
- You can explain exactly why a user can or cannot access a file.
- You can set up key-based SSH login end to end.

## Week 5: Linux Networking Tools for Ops
### Focus
- Host/network diagnostics with `curl`, `dig`, `ss`, `traceroute`, `tcpdump`
- Difference between DNS, routing, firewall, and app errors

### Labs
1. Run a local web service on a custom port.
2. Break DNS resolution and prove root cause.
3. Block traffic locally and compare timeout vs refused behavior.

### Done Criteria
- You can classify outages into DNS, network, or service issues.
- You can prove where packets stop with a command and output.

## Week 6: Automation and Final Linux Project
### Focus
- Bash scripting fundamentals for operations
- Cron or systemd timers
- Idempotent scripts and safe rollback habits

### Labs
1. Script health checks for CPU, disk, memory, and service status.
2. Schedule the script and save output to rotating logs.
3. Add non-zero exit codes for failures.

### Final Project
Build a "Linux service operations kit" that includes:
- One managed `systemd` service
- One troubleshooting runbook
- One Bash diagnostic script
- One incident report from a simulated outage

## Mastery Checklist
- I can diagnose a failed service in under 15 minutes.
- I can trace errors from symptom to log evidence.
- I can fix permission and SSH issues without unsafe `chmod 777`.
- I can script repeatable checks instead of manual steps.
