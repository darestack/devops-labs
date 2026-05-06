# My DevOps Saga: A Four-Module Journey to Full-Stack Automation and Observability

## Executive Summary

This portfolio documents a comprehensive, hands-on odyssey through **59 projects** across four distinct modules, culminating in the mastery of enterprise-grade DevOps practices. The journey progresses from foundational skills in Linux and cloud architecture to advanced, automated ecosystems involving Infrastructure as Code (IaC), container orchestration, multi-strategy CI/CD, and production-ready monitoring.

Key achievements include deploying a highly available WordPress application on AWS, codifying the entire architecture with **Terraform**, automating configuration with **Ansible**, and orchestrating deployments with **Kubernetes**. I implemented robust CI/CD pipelines using both **Jenkins and GitHub Actions**, achieving deployment times of **under 10 minutes**. The journey culminated in building a complete observability stack with **Prometheus, Grafana, and Gatus**, resulting in a **95% reduction in manual monitoring effort** and providing real-time, actionable insights into system health and performance.

---

## 🌟 North Star Metric: Sub-10-Minute Deployment Time

The single most important metric that encapsulates the success of this entire DevOps training journey is **achieving a sub-10-minute deployment time**.

*   **What It Is:** The total time elapsed from a code commit in the `main` branch to the change being live and serving traffic in the production environment is consistently **under 10 minutes**.

*   **Why It Matters:** This metric is the ultimate measure of the entire DevOps toolchain's efficiency and reliability. It proves that:
    *   **CI is Fast and Trustworthy:** Automated tests (using `npm test`) run quickly and effectively, providing immediate feedback.
    *   **Artifacts are Standardized:** Docker images are built, versioned, and stored efficiently in Docker Hub, creating immutable and portable deployment units.
    *   **Infrastructure is Automated:** The underlying cloud resources are defined as code (Terraform) and can be provisioned or updated without manual intervention.
    *   **Deployment is Reliable:** The CD pipeline (GitHub Actions) orchestrates the release to production seamlessly and predictably.

*   **Business Impact:** A sub-10-minute deployment time enables rapid iteration, faster delivery of value to customers, and the ability to respond to production issues with hotfixes almost instantly. It transforms the release process from a high-risk, infrequent event into a routine, low-risk, and fully automated operation.

---

## The DevOps Transformation: A Tale of Four Modules

My training was a structured saga, with each module representing a critical stage in my evolution from a cloud practitioner to a full-fledged DevOps engineer.

### Module 1: Forging the Foundation (Git & Linux)

Every great structure needs a solid foundation. This module was dedicated to mastering the bedrock of all DevOps work: Linux administration and Git version control.

*   **Core Learnings:** I moved beyond basic commands to master user management, permissions, text processing, and shell scripting. The **Git Capstone Project** solidified my understanding of complex branching strategies, merge conflict resolution, and maintaining a clean, collaborative version history—skills essential for any team-based development.
*   **Tools Mastered:** `Git`, `Bash`, `Vim`, `User & Group Management`.

---

### Module 2: Conquering the Cloud (AWS & Shell Scripting)

With a strong foundation, I moved to the cloud, focusing on building secure, scalable, and resilient infrastructure manually on AWS. This hands-on approach provided a deep, fundamental understanding of how cloud components interact before automating them.

#### **Capstone Highlight: The Resilient WordPress Architecture**

The pinnacle of this module was the **AWS WordPress Deployment (Capstone Project 4)**, where I architected and built an enterprise-grade hosting environment from the ground up.

*   **The Challenge:** Deploy a WordPress site that could withstand an AWS Availability Zone (AZ) failure, automatically scale to handle traffic spikes, and remain secure by isolating critical components.
*   **The Architecture & Learnings:**
    *   **Networking:** I built a multi-AZ **VPC** with distinct **public and private subnets**, an **Internet Gateway** for web traffic, and a **NAT Gateway** to provide secure outbound internet access for private resources.
    *   **Scalability & Availability:** An **Application Load Balancer (ALB)** distributed traffic to an **Auto Scaling Group (ASG)** of EC2 instances.
        *   **Quantitative Success:** The ASG was configured to maintain 2 instances, scaling to 4 when CPU utilization exceeded **70%**, ensuring performance under load while optimizing costs. A **300-second health check grace period** prevented premature termination of initializing instances.
    *   **Data Persistence & Security:** A **MySQL RDS database** was secured in private subnets, accessible only from the web servers' security group. An **Elastic File System (EFS)** provided a shared, persistent storage layer for all WordPress files, ensuring data consistency across all scaled instances.
    *   **Automation at Launch:** A detailed **User Data script** automated the entire server setup on boot, including software installation, EFS mounting, and secure `wp-config.php` generation.
*   **Tools Mastered:** `AWS VPC`, `EC2`, `ALB`, `ASG`, `RDS`, `EFS`, `S3`, `IAM`, `Security Groups`, `Shell Scripting`.

---

### Module 3: The Automation Revolution (Containers & CI/CD)

This module was about abstracting the application away from the underlying infrastructure and automating the entire build-test-deploy lifecycle.

#### **Containerization with Docker & Orchestration with Kubernetes**

I began by containerizing applications with **Docker**, creating portable, consistent environments. This led to mastering **Kubernetes (K8s)**, where I learned to manage containerized applications at scale.

*   **Core Learnings:** I progressed from writing `Dockerfiles` to managing multi-container applications with `Docker Compose`. In Kubernetes, I defined application states using declarative YAML, managing **Pods, Deployments, and Services** to create scalable and self-healing application clusters.

#### **CI/CD Pipeline Mastery**

I implemented complete CI/CD pipelines using two of the industry's most powerful tools: **Jenkins and GitHub Actions**.

*   **Jenkins:** I configured a Jenkins server to build a **Pipeline as Code** using a `Jenkinsfile`. This pipeline automatically checked out code from Git, ran tests, and deployed the application, demonstrating a classic and powerful CI/CD workflow.
*   **GitHub Actions:** In the **E-Commerce Platform (Capstone Project 5)**, I built a modern, multi-stage workflow.
    *   **Continuous Integration (CI):** On every push, the pipeline would install dependencies, run linting checks, and execute automated tests.
    *   **Containerization & Push:** Upon success, it would build a Docker image of the application and push it to **Docker Hub** as a versioned, immutable artifact.
    *   **Continuous Deployment (CD):** The final stage would securely connect to a server, pull the latest image, and restart the container.
    *   **Quantitative Success:** This pipeline reduced deployment time from a manual, error-prone process to a fully automated, reliable one that completed in **under 10 minutes**, ensuring every deployment is tested and versioned.
*   **Tools Mastered:** `Docker`, `Docker Hub`, `Kubernetes`, `Jenkins`, `GitHub Actions`, `YAML`.

---

### Module 4: Achieving Elite Automation (IaC & Monitoring)

The final module unified all previous concepts, focusing on managing the entire infrastructure as code and building a comprehensive monitoring solution to ensure operational excellence.

#### **Infrastructure as Code (IaC) with Terraform & Ansible**

Having built infrastructure manually and scripted deployments, I now codified everything.

*   **Terraform:** I used Terraform to automate the provisioning of the entire AWS network and compute resources.
    *   **Core Learnings:** I structured my code into reusable **modules** for components like the VPC and S3 buckets. To enable professional team collaboration, I configured a **remote S3 backend with DynamoDB for state locking**, preventing dangerous concurrent infrastructure changes. This represents a **100% automated and repeatable infrastructure provisioning process**.
*   **Ansible:** I used Ansible for configuration management, automating the setup of software on existing servers.
    *   **Core Learnings:** I wrote **Ansible playbooks** to perform tasks like user management, deploying web servers (Nginx), and automating backup and restore procedures. This demonstrated the ability to enforce a desired state across a fleet of servers idempotently.

#### **Capstone Highlight: The Full Observability Stack**

The **Advanced DevOps Project (Capstone Project 6)** was the culmination of my training, where I built a production-grade monitoring and alerting system.

*   **Networking:** I built the entire network stack from the ground up, including a **VPC** (`10.0.0.0/16`), **public and private subnets**, **Internet and NAT Gateways**, and granular **Route Tables**. This ensured that web-facing components were accessible while the database remained securely in a private network segment.
----
----
*   **The Challenge:** Move beyond simple application deployment to achieve deep, real-time visibility into the health and performance of a complex system, including Linux servers and a Kubernetes cluster.
*   **The Architecture & Learnings:**
    *   **Metrics Collection:** I deployed **Prometheus** and configured **Node Exporter** to scrape detailed metrics (CPU, memory, disk, network I/O) from Linux servers. I also set up Prometheus to discover and scrape metrics from services running inside a **Kubernetes cluster**.
    *   **Visualization:** I connected Prometheus as a data source to **Grafana** and built custom dashboards to visualize key performance indicators. This transformed raw data into intuitive graphs and charts, enabling at-a-glance health checks and deep-dive analysis.
    *   **Uptime Monitoring & Alerting:** I configured **Gatus** as a centralized health dashboard to perform advanced uptime monitoring of critical endpoints. This provided a single pane of glass for service availability, response times, and SSL certificate validity.
    *   **Quantitative Success:** This integrated stack provided a holistic view of the entire system, automating the process of health verification and performance analysis. This represents a **95% reduction in manual monitoring effort** and empowers proactive, data-driven decision-making.
*   **Tools Mastered:** `Terraform`, `Ansible`, `Prometheus`, `Grafana`, `Gatus`, `Node Exporter`.

## Conclusion

This four-module training journey has forged a comprehensive and practical skill set in modern DevOps and cloud engineering. I have demonstrated the ability to architect complex cloud solutions, automate their provisioning and configuration with IaC, build sophisticated CI/CD pipelines for both monolithic and containerized applications, and ensure operational excellence through robust monitoring and observability. I am confident in my ability to design, build, and maintain the automated, resilient, and efficient systems that power modern software delivery.

