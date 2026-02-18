# Git Learning Plan

## Goal
Use Git like a DevOps engineer: safe collaboration, clean history, and infrastructure changes managed through reviewable pull requests.

## Time Commitment
- 4 weeks
- 4 to 5 sessions per week
- 45 to 75 minutes per session

## Prerequisites
- GitHub account and one practice repo
- Basic CLI usage (`git` in terminal)

## Week 1: Core Git Mechanics
### Focus
- Working tree, staging area, commit history
- Branch creation and switching
- Useful inspection commands (`status`, `log`, `diff`, `show`)

### Labs
1. Make at least 10 small commits with meaningful messages.
2. Practice amending the last commit in a scratch branch.
3. Compare file-level diff vs commit-level diff.

### Done Criteria
- You can explain exactly what is staged vs unstaged.
- Your commit messages state intent, not just "update file".

## Week 2: Team Workflow with Branches and PRs
### Focus
- Feature branch workflow
- Pull request hygiene (description, testing notes, rollback notes)
- Merge strategies (merge commit, squash, rebase)

### Labs
1. Open one PR per task, even for solo work.
2. Use a PR template: problem, change, validation, risk.
3. Request and respond to at least 3 review comments.

### Done Criteria
- Every code change is traceable through a PR.
- PRs are small enough to review in 10 to 15 minutes.

## Week 3: Conflict Resolution, Rebase, Recovery
### Focus
- Handling merge conflicts
- Interactive rebase for cleanup
- Recovery tools: `reflog`, reverting bad changes

### Labs
1. Intentionally create and resolve 3 merge conflicts.
2. Use rebase to squash noisy commits before merge.
3. Recover a "lost" commit using `reflog`.

### Done Criteria
- You can resolve conflicts without deleting others' work.
- You can recover mistakes without panic or forceful resets.

## Week 4: Releases, Tags, and DevOps Change Discipline
### Focus
- Semantic version tags (`v1.0.0` style)
- `CHANGELOG.md` maintenance
- Infrastructure-as-code and GitOps mindset

### Labs
1. Create 3 tagged releases with clear notes.
2. Maintain a changelog entry for each merged PR.
3. For infra changes, include expected impact and rollback in PR text.

### Final Project
Set up a full repo workflow that includes:
- Protected default branch
- PR template and issue template
- Release tagging process
- `CHANGELOG.md` updated per release

## Mastery Checklist
- I create clean, reviewable commits and PRs consistently.
- I can resolve merge conflicts and recover from mistakes safely.
- I track infra changes through PRs, not undocumented manual clicks.
