# Awesome-Spot-Instance-Automation

## Top Spot Instance Automation Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Spot/Preemptible Instance Management, Kubernetes Node Autoscaling, Cost Optimization & Workload Interruption Handling*  

**Last updated: September 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Spot Instance Automation**. These tools help organizations safely and automatically run workloads on discounted spot/preemptible capacity across public clouds, maximizing savings while managing interruptions, diversification, and fallback to on-demand instances.



**Examples** include Spot by NetApp (Ocean), Cast AI, StormForge, Zesty, PerfectScale, nOps, Karpenter Enterprise, ScaleOps, CloudPilot AI, and related optimization platforms (the category leaders).



**Open-source emphasis**: **Karpenter** is the leading open-source Kubernetes node provisioner and the foundation of modern spot automation on Kubernetes. **AutoSpotting**, Cluster Autoscaler, and related tools extend automation to Auto Scaling groups and broader environments. This section highlights every major active open-source project found.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting Tier) | Free Tier / Trial Limits |
| :--- | :--- | :--- | :--- |
| **[Spot by NetApp (Ocean)](https://spot.io/)** | Automated Kubernetes & Spot instance workload management, scaling, and interruption handling. | Starts at 15–20% of net savings generated (or ~\$0.001/vCPU-hr on AWS Marketplace). | 14-day free trial with full platform access. |
| **[CAST AI](https://cast.ai/)** | Kubernetes cost optimization, automated node provisioning, rightsizing, and Spot management. | Starts at \$0.0069 per managed CPU/hr (~\$5/CPU/month) or \$200/mo minimum tier. | Free forever Read-Only Cost Monitoring plan (unlimited nodes & clusters). |
| **[StormForge](https://www.stormforge.io/)** | Continuous ML-driven Kubernetes workload optimization and resource rightsizing. | Starts at \$0.0041 per CPU/hr (~\$3/pod/month). | 30-day free trial (up to 1 cluster with full optimization features). |
| **[Zesty](https://zesty.co/)** | Automated cloud compute and commitment management (storage & Spot instance optimization). | Starts at 25% of net cloud cost savings achieved (success-based billing). | Free Cloud Savings Analysis & ROI evaluation report. |
| **[PerfectScale](https://www.perfectscale.io/)** | Autonomous Kubernetes capacity optimization and pod resource rightsizing platform. | Starts at \$0.005 per vCPU-hr for paid Advanced/Expert tiers. | Free forever Community Edition (up to 300,000 vCPU-hours/month) & 30-day trial for Expert features. |
| **[ScaleOps](https://scaleops.io/)** | Autonomous Kubernetes cloud cost optimization, pod rightsizing, and dynamic node scaling. | Starts at \$5.00 per vCPU/month (or ~\$0.0069/vCPU-hr). | 7-day free trial with full automated rightsizing features. |
| **[nOps](https://www.nops.io/)** | Automated FinOps platform specializing in AWS Spot instance automation and commitment management. | Starts at \$199/month for Core platform (or 15% of net Spot savings). | Free Tier (basic visibility & reporting) + 14-day free trial for full automation. |
| **[CloudPilot AI](https://cloudpilot.ai/)** | AI-driven Kubernetes autoscaling, Spot instance selection, and node rightsizing platform. | Starts at \$0.003 per CPU core-hour for Standard plan. | Free forever Community Edition (open-source engine with auto node sizing) & 30-day trial for Standard features. |



## Open-Source GitHub Projects



- **[Karpenter](https://github.com/aws/karpenter-provider-aws)**  

  Leading open-source Kubernetes node autoscaler/provisioner. Dynamically launches right-sized nodes (including Spot) based on pending pods, supports consolidation, and offers fast provisioning with flexible capacity-type policies.



- **[AutoSpotting](https://github.com/LeanerCloud/AutoSpotting)**  

  Open-source tool that automatically replaces on-demand instances in existing AWS Auto Scaling groups with equivalent Spot instances, with minimal configuration changes and fallback handling.



- **[Kubernetes Cluster Autoscaler](https://github.com/kubernetes/autoscaler)**  

  Classic open-source autoscaler that scales node groups up and down. Still widely used and can be configured for mixed on-demand/spot node groups.



- **[Karpenter providers for other clouds](https://github.com/search?q=karpenter+provider)**  

  Community and vendor providers that bring Karpenter-style provisioning to additional cloud environments beyond AWS.



- **[Spot interruption handlers & event responders](https://github.com/search?q=spot+interruption+OR+rebalance+recommendation+kubernetes)**  

  Open-source controllers and scripts that react to spot rebalance recommendations and termination notices (drain, checkpoint, reschedule).



- **[Node termination handlers](https://github.com/aws/aws-node-termination-handler)**  

  Tools that gracefully handle EC2 Spot (and other) interruptions inside Kubernetes clusters.



- **[Cost & utilization agents](https://github.com/search?q=kubernetes+cost+OR+spot+optimization+open+source)**  

  Open-source agents and exporters that surface spot vs on-demand usage, savings, and interruption metrics.



### Additional Strong Open-Source Options



- **KEDA**: Event-driven autoscaling that pairs well with Karpenter for scale-to-zero and bursty workloads.

- **Descheduler & consolidation tools**: Projects that help rebalance and pack workloads more efficiently onto cheaper capacity.

- **Instance selector libraries**: Tools that help choose diversified instance types for better spot availability.

- **Terraform / IaC modules**: Reusable modules for deploying Karpenter, AutoSpotting, and mixed-instance policies.

- **Observability for interruptions**: Dashboards and alerts focused on spot reclaim rates and fallback behavior.

- Multi-cloud abstractions and policy engines that encode “prefer spot, fallback to on-demand” rules.



**Frameworks for building custom systems**:  

For Kubernetes environments, start with **Karpenter** and configure NodePools to prefer Spot capacity with on-demand fallback.  

For classic Auto Scaling groups on AWS, **AutoSpotting** remains a proven open-source option.  

Layer commercial platforms (Cast AI, Spot by NetApp, StormForge, PerfectScale, etc.) when you need advanced ML-based interruption prediction, automated rightsizing, multi-cloud intelligence, or turnkey savings guarantees.  

Many production setups successfully run open-source Karpenter as the core provisioner and add commercial optimization layers for deeper automation and governance.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Spot/preemptible instances can be reclaimed with little notice. Workloads must be interruption-tolerant (stateless, checkpointable, or protected by PodDisruptionBudgets and fallback capacity). Incorrect configuration can cause outages.

- Open-source tools provide excellent control and cost savings but require proper configuration, monitoring of interruption rates, and testing of fallback behavior. Commercial platforms often add guardrails, prediction, and support that reduce operational risk.



---



**Made for platform engineers, FinOps teams, Kubernetes operators, and cloud cost optimizers.**  

Let's maximize the value of spot capacity through open, reliable, and well-engineered automation.
