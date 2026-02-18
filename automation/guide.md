# 5) Automation bridge (DevOps transition)

## 5.1 Terraform fundamentals

### Must understand

- Declarative resources

- State (local vs remote concept)

- Variables/outputs

- Modules (reusability)

### Labs

- Write Terraform for: VPC + EC2 + SG

- Refactor into modules

- Add `dev` vs `prod` variables

**Measurable outcomes**

- ✅ 1 command creates infra; 1 command destroys it

- ✅ README includes architecture + how to run

---

## 5.2 CI basics (pipelines, secrets, environments)

### Must understand

- Pipeline stages: validate → test → build → deploy

- Secrets: never in repo; use CI secret store

- Environments: dev/staging/prod pattern

### Lab

- CI runs `terraform fmt/validate/plan` on PR

**Measurable outcomes**

- ✅ CI status badge in README

- ✅ A failed PR when formatting is wrong

---

## 5.3 Docker basics (enough for support)

### Must do

- `Dockerfile`, build/run

- push to a registry

- environment variables

- basic image tagging

### Lab

- Containerize a simple app

- Run it behind a reverse proxy or with port mapping

**Measurable outcomes**

- ✅ Repo includes Dockerfile + run instructions

- ✅ You can explain how configs are injected (env vars)
