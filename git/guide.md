# 3) Git (DevOps workflow)

## 3.1 Branching, PRs, merge conflicts

### Good looks like

You can work in a team flow:

- feature branch → PR → review → merge

### Must-do habits

- Small commits with clear messages

- PR descriptions that explain “why”

- Resolve conflicts calmly

### Practice routine (weekly)

- Create a branch for every change

- Open PR even if it’s just you

- Write a short review comment on your own PR

**Measurable outcomes**

- ✅ At least 10 PRs in your repo by graduation

- ✅ You’ve resolved at least 2 intentional conflicts

---

## 3.2 Tags/releases + change notes

- Use tags for milestones: `v0.1`, `v0.2`

- Keep a `CHANGELOG.md` with 3–5 lines per milestone

**Measurable outcomes**

- ✅ 3 releases tagged, each with change notes

---

## 3.3 “Infrastructure changes via PR” mindset

Rule:

- No manual “click-only” changes without documenting

- Every infra change gets:
  - a PR

  - a plan/expected impact

  - rollback note
