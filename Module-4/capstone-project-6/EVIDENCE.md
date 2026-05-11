# Capstone 6 Evidence Notes

This capstone covered modular Terraform infrastructure and a monitoring stack.
The AWS environment used for the lab was temporary and has been destroyed, so
the repo should show this as historical implementation evidence rather than a
currently running system.

## Evidence Available Now

| Evidence | Path | What It Shows |
|---|---|---|
| Capstone summary | [img/image.png](img/image.png) | High-level summary of the Terraform and monitoring work |
| Terraform apply evidence | [../mini-project-03/img/main-apply.png](../mini-project-03/img/main-apply.png) | Terraform apply output from the supporting remote-state/module lab |
| S3 remote state | [../mini-project-03/img/state-file-console.png](../mini-project-03/img/state-file-console.png) | Terraform state stored in an S3 backend |
| AWS VPC evidence | [../mini-project-03/img/vpc-console.png](../mini-project-03/img/vpc-console.png) | AWS VPC created during the Terraform module lab |
| Gatus implementation notes | [../mini-project-12/README.md](../mini-project-12/README.md) | Uptime monitoring setup and configuration flow |

## What Not To Claim

- Do not describe this capstone as currently live.
- Do not claim active Grafana or Gatus dashboards unless the stack is rebuilt.
- Avoid unsupported percentage claims. Describe the mechanism instead: Prometheus scraping, Grafana dashboards, and Gatus endpoint checks.

## Fresh Evidence To Capture If Rebuilt

- `terraform init`, `terraform plan`, and `terraform apply` output with account IDs, IPs, and secrets redacted.
- `terraform state list` showing the main resources.
- Browser screenshot of the Apache or monitored endpoint.
- Grafana dashboard screenshot for CPU, memory, disk, and network metrics.
- Gatus dashboard screenshot showing endpoint availability checks.
- `terraform destroy` output or a short teardown note confirming cleanup.

## Positioning

Use this capstone as proof of infrastructure automation breadth: Terraform
modules, remote state, EC2 provisioning, and monitoring concepts. Use the
supporting mini-project screenshots as historical evidence, and be clear that
the environment was torn down after the lab.
