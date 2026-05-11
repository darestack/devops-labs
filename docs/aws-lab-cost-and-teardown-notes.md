# AWS Lab Cost and Teardown Notes

Most AWS projects in this repo were built as temporary labs. After the work was
validated, the environments were destroyed to avoid ongoing cloud spend. That is
why some projects have historical screenshots and workflow logs instead of live
URLs.

## Cost Risks To Watch

These are the resources most likely to keep billing after a lab feels done:

- EC2 instances and attached EBS volumes
- Elastic IPs that are allocated but not attached
- NAT gateways
- Application Load Balancers and target groups
- Auto Scaling Groups with desired capacity above zero
- RDS instances, retained snapshots, and automated backups
- EFS file systems and mount targets
- S3 buckets used for app assets, logs, or Terraform state
- DynamoDB tables used for Terraform state locking
- CloudWatch logs, alarms, and dashboards

## Teardown Checklist

Before destroying anything, capture the evidence needed for the README: workflow
run links, architecture screenshots, terminal output, and dashboard screenshots.

Then clean up in this order:

1. Run `terraform destroy` for Terraform-managed environments.
2. Confirm EC2 instances are terminated.
3. Confirm Auto Scaling Groups, Launch Templates, Load Balancers, listeners, and target groups are gone.
4. Confirm RDS instances, final snapshots, and retained automated backups are handled intentionally.
5. Confirm EFS file systems and mount targets are removed.
6. Confirm unattached EBS volumes and old snapshots are removed if no longer needed.
7. Confirm Elastic IPs and NAT gateways are released.
8. Confirm S3 buckets and DynamoDB lock tables are kept only when they are still needed for state history.
9. Check AWS Billing or Cost Explorer the next day for unexpected spend.

## Evidence To Keep Next Time

- A screenshot of the deployed app or dashboard.
- A screenshot of the successful CI/CD or Terraform run.
- Redacted `terraform plan`, `terraform apply`, and `terraform destroy` output.
- A short note with the deployment date, teardown date, AWS region, and services used.
- Any final GitHub Release or Actions run link if the deployment was automated.
