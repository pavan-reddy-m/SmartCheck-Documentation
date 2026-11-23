# GitHub and Kubernetes Pricing Comparison

**Research date:** 23 November 2026

**Currency:** USD

## 1. Introduction

This document explains the pricing models of GitHub and Kubernetes-related cloud services. It covers subscription plans, CI/CD usage, compute resources, storage, and additional infrastructure costs.

Cloud service prices can vary by region, configuration, usage, and applicable taxes. The figures in this document are reference prices and should be checked against the official pricing calculators before purchasing.

## 2. GitHub Pricing

GitHub provides free and paid plans for individuals, development teams, and enterprises.

### 2.1 GitHub Subscription Plans

| Plan | Price | Intended Users |
|---|---:|---|
| Free | $0/month | Individual developers and small projects |
| Team | $4/user/month | Development teams and organizations |
| Enterprise | $21/user/month | Large organizations requiring enterprise governance and security |

Source: https://github.com/pricing

### 2.2 GitHub Free Plan

The Free plan provides basic source code management and collaboration features.

Key features:

- Unlimited public and private repositories.
- GitHub Issues and Projects.
- Dependabot security and version updates.
- GitHub Actions included usage.
- GitHub Packages storage allowance.
- Community support.

Suitable for individual developers, students, and small projects.

### 2.3 GitHub Team Plan

The Team plan provides additional collaboration and repository management features.

Key features:

- All Free plan features.
- Repository rules.
- Multiple pull request reviewers.
- Draft pull requests.
- Code owners and required reviewers.
- Environment deployment branches and secrets.
- GitHub Codespaces access.
- Increased GitHub Actions and Packages allowances.
- Web-based support.

Suitable for organizations that need structured code reviews and team collaboration.

### 2.4 GitHub Enterprise Plan

The Enterprise plan provides advanced security, administration, and governance capabilities.

Key features:

- All Team plan features.
- Enterprise Managed Users.
- SAML single sign-on.
- SCIM user provisioning.
- Advanced auditing.
- Audit Log API.
- Data residency capabilities.
- Enterprise account management.
- Enterprise security and compliance features.
- Increased GitHub Actions and Packages allowances.

Suitable for large organizations with strict security, compliance, and access-management requirements.

### 2.5 GitHub Plan Comparison

| Feature | Free | Team | Enterprise |
|---|---|---|---|
| Unlimited repositories | Yes | Yes | Yes |
| Private repositories | Yes | Yes | Yes |
| Pull requests | Yes | Yes | Yes |
| Advanced repository rules | Limited | Yes | Yes |
| Multiple reviewers | Limited | Yes | Yes |
| Code owners | Limited | Yes | Yes |
| SAML SSO | No | No | Yes |
| Enterprise account management | No | No | Yes |
| Advanced auditing | No | No | Yes |
| Community support | Yes | No | No |

Feature availability can differ between public and private repositories. Consult the official comparison page for the complete feature matrix.

## 3. GitHub Actions Pricing

GitHub Actions is used to automate continuous integration and continuous delivery workflows.

Its cost depends on factors such as:

- GitHub subscription plan.
- Runner operating system.
- Runner processing capacity.
- Workflow execution time.
- Artifact and cache storage.
- Usage beyond included allowances.

### 3.1 Included GitHub Actions Compute Usage

The current GitHub billing documentation lists these monthly compute allowances:

| Plan | Included Compute Usage |
|---|---:|
| GitHub Free | $12/month |
| GitHub Pro | $18/month |
| GitHub Free for organizations | $12/month |
| GitHub Team | $18/month |
| GitHub Enterprise Cloud | $300/month |

These are monetary compute allowances, not fixed numbers of minutes. Actual execution time depends on the runner type and its billing rate.

### 3.2 GitHub-Hosted Runner Pricing

Standard GitHub-hosted runners have different rates depending on their operating system and processing capacity.

| Runner | Price per minute |
|---|---:|
| Linux 1-core x64 | $0.002 |
| Linux 2-core x64 | $0.006 |
| Linux 2-core ARM64 | $0.005 |
| Windows 2-core x64 | $0.010 |
| macOS 3-core or 4-core | $0.062 |

GitHub rounds job execution time up to the nearest whole minute for billing purposes.

Standard GitHub-hosted runners are free for public repositories. Self-hosted runner usage is also not charged as standard GitHub-hosted runner compute, although the infrastructure used to operate self-hosted runners can have its own cost.

### 3.3 GitHub Actions Storage Pricing

| Storage Type | Price |
|---|---:|
| Shared storage for artifacts and Packages | $0.25/GB/month |
| Actions cache storage | $0.07/GB/month |
| Custom runner image storage | $0.07/GB/month |

Artifact storage and GitHub Packages share a storage allowance. Actions cache storage has a separate allowance.

### 3.4 GitHub Actions Cost Example

Consider a development team using a standard Linux 2-core GitHub-hosted runner.

Assume:

- Runner rate: $0.006/minute.
- Total execution time: 1,000 billable minutes.
- Public or private repository status and included allowances are considered separately.

Estimated compute cost before applicable included allowances:

1,000 × $0.006 = $6.00

The actual amount payable depends on the account's available compute allowance and billing configuration.

### 3.5 GitHub Billing Management

Organizations can monitor and control their spending through GitHub's billing settings.

Recommended practices:

- Monitor Actions compute usage.
- Configure budgets and spending limits.
- Set usage notifications.
- Review artifact and cache storage.
- Remove unnecessary workflow artifacts.
- Use appropriate runner sizes.
- Prefer standard Linux runners when suitable.
- Review billing reports regularly.

## 4. GitHub Pricing References

- GitHub Plans and Pricing: https://github.com/pricing
- GitHub Plans Documentation: https://docs.github.com/en/get-started/learning-about-github/githubs-plans
- Product Usage Included with Each Plan: https://docs.github.com/en/billing/reference/product-usage-included
- GitHub Actions Billing: https://docs.github.com/en/billing/concepts/product-billing/github-actions
- GitHub Actions Runner Pricing: https://docs.github.com/en/billing/reference/actions-runner-pricing
- How GitHub Billing Works: https://docs.github.com/en/billing/get-started/how-billing-works

## 5. Pricing Notes

- Prices are listed in USD.
- Team and Enterprise subscription prices are per user per month.
- Usage-based services can generate additional charges.
- Taxes and currency conversion may affect the final amount paid in India.
- Pricing and included allowances can change. Verify the official documentation before making purchasing decisions.

## 6. Kubernetes Pricing

Kubernetes is an open-source container orchestration platform. The Kubernetes software itself does not have a standard per-user subscription price.

However, running Kubernetes in production requires infrastructure such as:

- Control plane or cluster management.
- Worker nodes or compute instances.
- Persistent storage.
- Networking and load balancers.
- Container image registries.
- Monitoring and logging.
- Data transfer.

Managed Kubernetes providers such as Google Kubernetes Engine (GKE), Amazon Elastic Kubernetes Service (EKS), and Azure Kubernetes Service (AKS) charge according to their respective service and infrastructure pricing models.

### 6.1 Kubernetes Pricing Overview

Kubernetes is an open-source container orchestration platform. The upstream Kubernetes software does not require a subscription or license fee.

However, running Kubernetes clusters requires infrastructure and managed services that may generate costs.

Typical cost components include:

- Cluster management and control plane.
- Worker nodes and virtual machines.
- CPU and memory resources.
- Persistent storage.
- Networking and load balancers.
- Public IP addresses.
- Container image registries.
- Monitoring and logging.
- Data transfer and network egress.

### 6.2 Google Kubernetes Engine (GKE) Pricing

Google Kubernetes Engine is Google's managed Kubernetes service.

GKE provides two primary cluster operation modes:

**Standard mode**

- Provides control over node pools and infrastructure.
- Uses Compute Engine virtual machines for worker nodes.
- Charges for the underlying worker node resources.
- Supports customized cluster configurations.

**Autopilot mode**

- Google manages the underlying infrastructure and node provisioning.
- Billing for general-purpose workloads is based on requested Pod resources.
- Suitable for teams that want to reduce infrastructure management.

**GKE cluster management pricing:**

| Component | Pricing |
|---|---|
| Cluster management | $0.10 per cluster per hour |
| Extended support | Additional $0.50 per cluster per hour; total $0.60 per hour |
| Free-tier credit | $74.40 per month per billing account |
| Standard worker nodes | Based on Compute Engine pricing |
| Autopilot workloads | Based on requested CPU, memory, and applicable storage |
| Persistent storage | Based on disk type and capacity |
| Networking | Additional charges may apply |

The $74.40 monthly free-tier credit is equivalent to one eligible zonal Standard or Autopilot cluster's management fee for a 744-hour month. It does not cover worker nodes or other infrastructure costs. Regional cluster management fees are not eligible for this credit.

**Official pricing:**

https://cloud.google.com/kubernetes-engine/pricing

### 6.3 Amazon Elastic Kubernetes Service (EKS) Pricing

Amazon Elastic Kubernetes Service is AWS's managed Kubernetes service.

AWS manages the Kubernetes control plane, while customers pay for the infrastructure used by their applications.

**EKS pricing components:**

| Component | Pricing |
|---|---|
| Standard Kubernetes version support | $0.10 per cluster per hour |
| Extended Kubernetes version support | $0.60 per cluster per hour |
| EC2 worker nodes | Based on EC2 instance pricing |
| Persistent storage | Based on Amazon EBS pricing |
| Public IPv4 addresses | Additional charges may apply |
| Networking | Data transfer and cross-Availability Zone charges may apply |
| Load balancers | Based on Elastic Load Balancing pricing |

**Standard support:**

A Kubernetes version receives standard support for the first 14 months after its release in EKS.

**Extended support:**

After standard support ends, an eligible Kubernetes version can enter an additional 12-month extended support period at a higher cluster management price.

**Official pricing:**

https://aws.amazon.com/eks/pricing/

### 6.4 Azure Kubernetes Service (AKS) Pricing

Azure Kubernetes Service is Microsoft's managed Kubernetes service.

AKS provides Free, Standard, and Premium cluster management tiers.

**AKS pricing tiers:**

| Tier | Cluster Management | Main Purpose |
|---|---|---|
| Free | No cluster management fee | Learning, development, and testing |
| Standard | Pay-as-you-go; check applicable SLA pricing | Production workloads requiring uptime SLA |
| Premium | Pay-as-you-go; additional LTS charges may apply | Production workloads requiring 24-month Kubernetes LTS |

**AKS Free tier:**

- Free cluster management.
- Pay only for underlying infrastructure resources.
- Supports up to 1,000 nodes; recommended for clusters with fewer than 10 nodes.
- No financially backed control-plane uptime SLA.
- Suitable for development and testing.

**AKS Standard tier:**

- Financially backed control-plane uptime SLA.
- Supports production workloads.
- Supports up to 5,000 nodes.
- Cluster management charges depend on the selected Azure region and configuration.

**AKS Premium tier:**

- Includes Standard tier capabilities.
- Provides 24-month Long-Term Support (LTS) for eligible Kubernetes versions.
- Supports up to 5,000 nodes.
- Supports workloads requiring extended maintenance and security updates.
- Additional LTS charges apply.

AKS Standard tier control-plane SLA charges and Premium LTS charges should be verified using the Azure Pricing Calculator. Worker-node compute and other infrastructure resources are billed separately.

**Official pricing:**

https://azure.microsoft.com/en-us/pricing/details/kubernetes-service/

### 6.5 GKE vs EKS vs AKS Pricing Comparison

| Pricing Component | GKE | EKS | AKS |
|---|---|---|---|
| Cluster management | $0.10/hour | $0.10/hour standard | Free or paid tier; check Azure pricing |
| Extended support | $0.60/hour during extended support | $0.60/hour | Premium LTS; additional charges may apply |
| Worker nodes | Compute Engine | EC2 | Azure Virtual Machines |
| Persistent storage | Persistent Disk | EBS | Azure Managed Disks |
| Load balancing | Cloud Load Balancing | Elastic Load Balancing | Azure Load Balancer |
| Container registry | Artifact Registry | Amazon ECR | Azure Container Registry |
| Monitoring | Cloud Monitoring | CloudWatch | Azure Monitor |

Actual infrastructure prices depend on the selected region, machine type, storage capacity, and network usage.

### 6.6 Monthly Cluster Management Cost Example

For comparison, assume a cluster runs continuously for 730 hours in a month.

**GKE Standard cluster management:**

730 × $0.10 = $73.00

An eligible monthly free-tier credit of $74.40 can cover this cluster management fee.

**EKS standard support:**

730 × $0.10 = $73.00

**GKE extended support:**

730 × $0.60 = $438.00

**EKS extended support:**

730 × $0.60 = $438.00

**AKS Free tier:**

730 × $0.00 = $0.00

**AKS Standard tier:**

AKS Standard and Premium charges depend on the selected tier and applicable Azure pricing. Check the Azure Pricing Calculator for an estimate based on your region and subscription.

https://azure.microsoft.com/en-us/pricing/calculator/

These examples cover cluster management only. They do not include worker nodes, storage, networking, monitoring, or other infrastructure charges.

### 6.7 Total Kubernetes Infrastructure Cost

A complete Kubernetes cost estimate should consider the following formula:

Total Monthly Cost =

- Cluster management charges
- Worker node compute charges
- Persistent storage charges
- Load balancer charges
- Public IP charges
- Network data transfer charges
- Container registry charges
- Monitoring and logging charges

For production environments, additional costs may arise from high availability, multiple clusters, backup systems, security services, and disaster recovery.

### 6.8 Kubernetes Cost Optimization Best Practices

Recommended practices for reducing Kubernetes infrastructure costs:

1. Select appropriate virtual machine sizes.
2. Configure CPU and memory requests and limits.
3. Use Horizontal Pod Autoscaling where appropriate.
4. Enable cluster autoscaling.
5. Remove unused clusters and worker nodes.
6. Use Spot or preemptible instances for suitable fault-tolerant workloads.
7. Monitor persistent storage usage.
8. Review network egress and load balancer charges.
9. Use committed-use discounts or reservations for predictable workloads.
10. Monitor costs through cloud billing dashboards.

### 6.9 Kubernetes Pricing References

**Google Cloud:**

- GKE Pricing: https://cloud.google.com/kubernetes-engine/pricing
- Compute Engine Pricing: https://cloud.google.com/compute/pricing

**Amazon Web Services:**

- EKS Pricing: https://aws.amazon.com/eks/pricing/
- EC2 Pricing: https://aws.amazon.com/ec2/pricing/
- EBS Pricing: https://aws.amazon.com/ebs/pricing/

**Microsoft Azure:**

- AKS Pricing: https://azure.microsoft.com/en-us/pricing/details/kubernetes-service/
- AKS Pricing Tiers: https://learn.microsoft.com/en-us/azure/aks/free-standard-pricing-tiers
- Azure Virtual Machines Pricing: https://azure.microsoft.com/en-us/pricing/details/virtual-machines/
- Azure Pricing Calculator: https://azure.microsoft.com/en-us/pricing/calculator/

### 6.10 Conclusion

GKE, EKS, and AKS provide managed Kubernetes services with different cluster management, infrastructure, and support pricing models.

GKE provides a monthly free-tier cluster management credit for eligible clusters. EKS charges according to Kubernetes version support. AKS provides Free, Standard, and Premium management tiers.

The best provider depends on infrastructure requirements, existing cloud investments, operational needs, availability requirements, and total estimated cost.