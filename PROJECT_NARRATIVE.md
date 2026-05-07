# DevOps Labs Narrative

This repository documents 59 hands-on DevOps labs across Linux, AWS, Docker,
Kubernetes, GitHub Actions, Terraform, Ansible, Prometheus, Grafana, and Gatus.

The strongest value is not the number of labs. It is the progression from
manual operations to repeatable infrastructure and observable services.

## What This Repo Proves

| Area | Evidence |
|---|---|
| Linux and Git fundamentals | Module 1 labs with branching, collaboration, permissions, and shell workflow notes |
| AWS architecture | Module 2 labs and the WordPress HA capstone with VPC, public/private subnets, ALB, ASG, RDS, EFS, and user data automation |
| CI/CD and containers | Module 3 labs with Docker, Docker Compose, GitHub Actions CI, Docker image publishing, Jenkins, and Kubernetes basics |
| IaC and operations | Module 4 labs with Terraform backend/module examples, Ansible playbooks, Prometheus/Grafana/Gatus notes, and backup/restore automation |

## Capstone Summary

| Capstone | Scope | Current Evidence |
|---|---|---|
| WordPress HA on AWS | Multi-AZ WordPress lab architecture using ALB, ASG, private RDS, EFS, and bootstrapping scripts | README, user data script, and screenshots |
| E-commerce CI/CD | React + Express lab app with Docker Compose, API tests, GitHub Actions CI, and GHCR image publishing workflow | Workflow files, Dockerfiles, app source, and notes |
| Terraform + Monitoring | Terraform and observability learning path using modules, remote state examples, Prometheus, Grafana, and Gatus | Write-up plus implementation files in related Module 4 mini-projects |

## Credibility Boundaries

- Live AWS resources are not assumed to still be running.
- Deployment-time reduction claims are not used unless backed by workflow run data.
- Monitoring impact is described by mechanism, not unsupported percentages.
- Terraform source files for some concepts live in mini-project folders rather than the capstone folder.
- Screenshots and dashboard exports should be promoted into a root evidence index before interviews.

## Best Interview Path

For a 5-minute technical screen, start with:

1. [WordPress HA on AWS](Module-2/capstone-project-4/) for AWS architecture.
2. [E-commerce CI/CD](Module-3/capstone-project-5/) for Docker and GitHub Actions.
3. [Terraform backend/modules](Module-4/mini-project-03/) for infrastructure as code.
4. [Ansible backup/restore](Module-4/mini-project-09/) for operations automation.
