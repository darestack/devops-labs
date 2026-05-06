# devops-labs

59 hands-on projects across 4 modules, progressing from Linux fundamentals
to production-grade infrastructure automation and observability.

Completed as part of the [Darey.io DevOps curriculum](https://3mtt.academy.darey.io/).

---

## Capstone Projects

These are the highest-signal deliverables — full deployments with real infrastructure decisions.

| Capstone | What Was Built | Stack |
|---|---|---|
| [WordPress HA on AWS](Module-2/capstone-project-4/) | Multi-AZ VPC, ALB, Auto Scaling Group (scales at 70% CPU), RDS in private subnet, EFS shared storage, EC2 User Data automation | AWS VPC · EC2 · ALB · ASG · RDS · EFS · Bash |
| [E-Commerce CI/CD Pipeline](Module-3/capstone-project-5/) | React + Express.js app with GitHub Actions CI (test + lint on every PR), Docker image publishing to GHCR on merge, automated deployment to EC2 | Docker · GitHub Actions · Node.js · GHCR |
| [Modular Terraform + Observability Stack](Module-4/capstone-project-6/) | Terraform EC2/SG modules, remote S3 backend with DynamoDB state locking, Prometheus Node Exporter scraping, Grafana dashboards, Gatus endpoint uptime monitoring | Terraform · Prometheus · Grafana · Gatus · AWS |

---

## Module Summary

| Module | Topics | Projects |
|---|---|---|
| [Module 1](Module-1/) | Linux administration, Git workflows, user/group management | 8 mini + 1 capstone |
| [Module 2](Module-2/) | AWS (EC2, VPC, IAM, S3, ASG, RDS, EFS), Bash scripting | 17 mini + 3 capstones |
| [Module 3](Module-3/) | Docker, Kubernetes, Jenkins, GitHub Actions CI/CD | 16 mini + 1 capstone |
| [Module 4](Module-4/) | Terraform, Ansible, Prometheus, Grafana, Gatus | 12 mini + 1 capstone |

---

## Key Skills Demonstrated

**Infrastructure as Code**
Terraform modules with reusable EC2/security-group components, remote S3 backend,
DynamoDB state locking for team collaboration.

**Cloud Architecture**
Multi-AZ VPC design, Application Load Balancer, Auto Scaling Groups,
RDS in private subnets, EFS shared storage across instances.

**CI/CD Pipelines**
GitHub Actions: matrix builds, Docker publish to GHCR, EC2 auto-deploy.
Jenkins: Pipeline as Code via Jenkinsfile.

**Monitoring & Observability**
Prometheus Node Exporter (CPU, memory, disk, network I/O),
Grafana dashboards, Gatus uptime + SSL monitoring.

**Linux & Automation**
User management, Bash scripting, systemd, Ansible playbooks
for configuration management and server automation.

**Containers & Orchestration**
Docker, Docker Compose, Kubernetes (Pods, Deployments, Services, networking).

---

## Repository Structure

```
devops-labs/
├── Module-1/    # Linux & Git fundamentals
├── Module-2/    # AWS & Shell scripting
├── Module-3/    # Docker, Kubernetes & CI/CD
└── Module-4/    # Terraform, Ansible & Monitoring
```

Each project directory contains a `README.md` with implementation steps,
architecture notes, and screenshot evidence.

---

## Resources

- [Darey.io DevOps Training](https://3mtt.academy.darey.io/)
- [Terraform Documentation](https://www.terraform.io/docs)
- [Prometheus Documentation](https://prometheus.io/docs/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)