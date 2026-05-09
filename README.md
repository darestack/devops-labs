# devops-labs

Curated DevOps training portfolio covering Linux, AWS, Docker, Kubernetes,
GitHub Actions, Terraform, Ansible, Prometheus, Grafana, and Gatus.

This repository is a lab index, not a single production platform. The value is
in the implementation notes, scripts, Terraform files, playbooks, workflow
files, screenshots, and troubleshooting records inside each project folder.

For a quick proof map, start with [docs/evidence-index.md](docs/evidence-index.md).

Completed as part of the [Darey.io DevOps curriculum](https://3mtt.academy.darey.io/).

## How To Read This Repo

| Capability | Best Evidence | Current Scope |
|---|---|---|
| AWS architecture | [WordPress HA on AWS](Module-2/capstone-project-4/) with Multi-AZ VPC, ALB, Auto Scaling Group, private RDS, EFS, and EC2 User Data | Manual AWS build documented with architecture notes and screenshots |
| Containerized CI/CD | [E-commerce CI/CD capstone](Module-3/capstone-project-5/) and nested [ecommerce-platform](Module-3/capstone-project-5/ecommerce-platform/) app with Dockerfiles, Compose, tests, and GitHub Actions workflows | Lab application with CI and image-publish workflow evidence |
| Terraform / IaC | [Terraform backend and VPC/S3 modules](Module-4/mini-project-03/) plus [EC2/security-group modules](Module-4/mini-project-05/) | Actual Terraform files live in mini-project folders; capstone write-up should be consolidated later |
| Ansible operations | [User management playbook](Module-4/mini-project-07/ansible-user-management/), [Nginx deployment playbooks](Module-4/mini-project-08/ansible-nginx-deployment/), and [backup/restore playbooks](Module-4/mini-project-09/ansible-backup-restore/) | Practical server automation examples |
| Monitoring | [Terraform + observability capstone write-up](Module-4/capstone-project-6/) and Gatus/Prometheus/Grafana labs in Module 4 | Monitoring workflow documented; add exported dashboards and config files next |

## Capstones And Companion Repos

Some capstones have their own application repositories. This repo is still the
main index because it keeps the build notes, screenshots, and troubleshooting
records together. The companion repos are useful when you want to inspect the
app or workflow code directly.

| Capstone | Main Evidence In This Repo | Companion Repo | Positioning |
|---|---|---|---|
| Git collaboration capstone | [Module-1/capstone-project-1](Module-1/capstone-project-1/) | [greenwood-library-website](https://github.com/darestack/greenwood-library-website) | Foundational Git workflow evidence; not a headline portfolio repo |
| MarketPeak EC2 deployment | [Module-2/capstone-project-3](Module-2/capstone-project-3/) | [MarketPeak_Ecommerce](https://github.com/darestack/MarketPeak_Ecommerce) | Early manual EC2/Apache deployment evidence; keep as historical context |
| E-commerce CI/CD | [Module-3/capstone-project-5](Module-3/capstone-project-5/) | [ecommerce-platform](https://github.com/darestack/ecommerce-platform) | Companion app repo with passing CI; promote only after current screenshots and deployment logs are added |
| EC2 release automation | [Module-3 mini-project notes](Module-3/) | [github-actions-ec2-pipeline](https://github.com/darestack/github-actions-ec2-pipeline) | Polished standalone repo; better reviewed directly |
| Container CI/CD quality gates | [Module-3 mini-project notes](Module-3/) | [github-actions-cicd-demo](https://github.com/darestack/github-actions-cicd-demo) | Polished standalone repo; better reviewed directly |

## Highest-Signal Projects

| Project | What It Demonstrates | Evidence To Review |
|---|---|---|
| [WordPress HA on AWS](Module-2/capstone-project-4/) | VPC/subnet design, ALB, ASG scaling policy, private RDS access, shared EFS storage, bootstrap automation | README architecture notes, `UserData_ALB_ASG.txt`, screenshots |
| [E-commerce CI/CD Pipeline](Module-3/capstone-project-5/) | React + Express app, Docker Compose runtime, API tests, GitHub Actions CI, GHCR image publishing workflow | Nested app source, `.github/workflows/`, Dockerfiles, screenshots |
| [Terraform Backend + Modules](Module-4/mini-project-03/) | S3 remote state, Terraform backend setup, reusable VPC/S3 modules | Terraform files under `terraform-backend-setup/` and `terraform-modules-vpc-s3/` |
| [Terraform EC2 Module](Module-4/mini-project-05/) | Reusable EC2 and security-group module structure | Terraform module files under `modules/` |
| [Ansible Backup / Restore](Module-4/mini-project-09/) | Operational automation for backup and restore workflows | `backup.yml`, `restore.yml`, and inventory notes |

## Module Map

| Module | Focus | Contents |
|---|---|---|
| [Module 1](Module-1/) | Linux, Git, shell basics | 8 mini projects + 1 capstone |
| [Module 2](Module-2/) | AWS, EC2, VPC, IAM, S3, ASG, RDS, EFS, Bash | 17 mini projects + 3 capstones |
| [Module 3](Module-3/) | Docker, Kubernetes, Jenkins, GitHub Actions CI/CD | 16 mini projects + 1 capstone |
| [Module 4](Module-4/) | Terraform, Ansible, Prometheus, Grafana, Gatus | 12 mini projects + 1 capstone |

## Skills Demonstrated

| Skill Area | Evidence Paths |
|---|---|
| Linux and Git workflow | `Module-1/` |
| AWS infrastructure | `Module-2/capstone-project-4/`, `Module-2/mini-project-*` |
| Docker and Compose | `Module-3/capstone-project-5/ecommerce-platform/` |
| GitHub Actions | `Module-3/capstone-project-5/ecommerce-platform/.github/workflows/` |
| Kubernetes basics | `Module-3/mini-project-12/` through `Module-3/mini-project-16/` |
| Terraform | `Module-4/mini-project-01/`, `Module-4/mini-project-03/`, `Module-4/mini-project-05/` |
| Ansible | `Module-4/mini-project-07/`, `Module-4/mini-project-08/`, `Module-4/mini-project-09/` |
| Observability | `Module-4/capstone-project-6/`, `Module-4/mini-project-10/`, `Module-4/mini-project-11/`, `Module-4/mini-project-12/` |

## Credibility Notes

- Training projects are labeled as labs.
- Live AWS resources are not assumed to still be running.
- Claims are limited to what is visible in the repo: scripts, workflow files,
  Terraform files, playbooks, screenshots, and notes.
- The Terraform/observability capstone currently needs source files and
  dashboard exports promoted into the capstone folder. Until then, inspect the
  linked Terraform mini-projects for implementation code.
- Cost and teardown notes should be added before using AWS labs in interviews.

## Next Evidence To Add

- Fresh screenshots for currently running services where the old screenshots are historical.
- Redacted `terraform plan` / `terraform apply` outputs for the Terraform labs.
- Current app screenshots and deployment logs for the e-commerce CI/CD capstone.
- Grafana dashboard export JSON and Gatus config for the observability labs.
- AWS cost estimate and teardown checklist for the HA WordPress capstone.
