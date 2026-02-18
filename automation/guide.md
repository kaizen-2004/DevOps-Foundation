# Automation Learning Plan

## Goal
Move from manual operations to repeatable automation using infrastructure as code, CI/CD, and container workflows.

## Time Commitment
- 6 weeks
- 5 sessions per week
- 60 to 90 minutes per session

## Prerequisites
- Linux and Git fundamentals from other guides
- Cloud account and CLI access
- Docker installed locally

## Week 1: Automation Mindset and Scripting
### Focus
- Idempotent operations
- Bash scripting for repeatable tasks
- Exit codes and defensive scripting (`set -euo pipefail`)

### Labs
1. Convert a manual server setup checklist into a Bash script.
2. Add validation checks and clear error messages.
3. Run script twice and confirm safe repeated behavior.

### Done Criteria
- You can replace repeated manual steps with reliable scripts.

## Week 2: Terraform Fundamentals
### Focus
- Declarative resources and dependency graph
- Providers, variables, outputs
- State files and remote state concepts

### Labs
1. Create Terraform for a small environment (network + compute).
2. Use `terraform fmt`, `validate`, and `plan` every change.
3. Destroy and recreate safely from code.

### Done Criteria
- One command path can provision and destroy your lab environment.

## Week 3: Terraform Structure and Reuse
### Focus
- Module design
- Environment separation (`dev`, `staging`, `prod`)
- Drift detection and state hygiene

### Labs
1. Refactor flat Terraform into reusable modules.
2. Add separate variables for `dev` and `prod`.
3. Simulate drift and reconcile with plan/apply.

### Done Criteria
- Your Terraform is modular and environment-aware.

## Week 4: CI/CD Basics for Infrastructure and Apps
### Focus
- Pipeline stages: lint, test, build, plan, deploy
- Secret handling in CI
- Branch protection and required checks

### Labs
1. Create CI pipeline that runs Terraform checks on every PR.
2. Add an intentional formatting failure to verify gate behavior.
3. Publish pipeline status badge in repo README.

### Done Criteria
- Pull requests cannot merge when critical checks fail.

## Week 5: Docker and Container Operations
### Focus
- Dockerfile design and layer caching
- Image tags, registries, and versioning
- Runtime configuration via environment variables

### Labs
1. Containerize a small app with a minimal Dockerfile.
2. Build, tag, and push image to a registry.
3. Run container with environment-specific config.

### Done Criteria
- You can build and run versioned container images reliably.

## Week 6: End-to-End Automation Project
### Project Scope
Automate delivery of one small service:
- Infrastructure provisioned by Terraform
- App containerized with Docker
- CI pipeline validates and deploys to a lab environment
- Rollback steps documented

### Deliverables
- `README.md` with architecture and run instructions
- `Makefile` or script entry points for common actions
- CI pipeline file
- Terraform modules and environment configs
- Post-incident note from one failed deployment drill

## Mastery Checklist
- I can automate infrastructure changes with reviewable code.
- I can enforce quality gates with CI before deployment.
- I can package and run apps consistently using containers.
- I can document rollback and recovery for failed automation.
