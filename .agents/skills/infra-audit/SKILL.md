---
name: infra-audit
description: Audit Dockerfiles, Helm charts, and Terraform configurations for security vulnerabilities, reliability gaps, and cost issues. Use when asked to audit, review, or harden infrastructure code.
---
# Infrastructure Audit Checklist

When auditing infrastructure files in this repository, execute these steps in order:
1. Run local static checks if installed (`helm lint ./charts/web-app`, `terraform -chdir=terraform fmt -check`).
2. Inspect **Dockerfiles** for root user execution, unpinned `:latest` tags, and missing `.dockerignore` or multi-stage builds.
3. Inspect **Helm charts** for missing CPU/memory limits, missing health probes, and privileged security contexts.
4. Inspect **Terraform** for open `0.0.0.0/0` ingress rules, unencrypted storage, and missing resource tags.
5. Present all findings in a Markdown table with columns: **Severity**, **File**, **Issue**, and **Fix**.