# AGENTS.md

## Tech Stack
- Containerization: Docker (multi-stage builds)
- Orchestration: Kubernetes + Helm v3
- IaC: Terraform (AWS provider)

## Validation Commands
- Terraform format: `terraform -chdir=terraform fmt -check`
- Terraform validate: `terraform -chdir=terraform validate`
- Helm lint: `helm lint ./charts/web-app`

## Strict Safety Boundaries
- NEVER run `terraform apply`, `terraform destroy`, `kubectl apply`, or `helm install`.
- NEVER output secrets, tokens, or `.tfvars` contents.
- When asked to review files, propose diffs first; do not overwrite files unless explicitly told to fix them.