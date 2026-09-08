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



- **[Spot by NetApp (Ocean)](https://spot.io/)**  

  Specialized platform for automating and optimizing workloads on spot instances across clouds, with intelligent scaling, interruption handling, and SLA-oriented features.



- **[Cast AI](https://cast.ai/)**  

  Kubernetes cost-optimization platform that automates node provisioning, bin-packing, rightsizing, and advanced Spot management (often layered on Karpenter).



- **[StormForge](https://www.stormforge.io/)**  

  Continuous workload optimization platform that tunes resource requests and works alongside autoscalers and spot strategies to improve efficiency.



- **[Zesty](https://zesty.co/)**  

  Cloud cost optimization focused on automated commitment and capacity management, including storage and compute efficiency.



- **[PerfectScale, ScaleOps](https://www.perfectscale.io/)**  

  Autonomous Kubernetes optimization platforms that continuously adjust pod resources and improve cluster efficiency, complementing spot automation.



- **[nOps](https://www.nops.io/)**  

  Cloud cost management and automation platform with strong support for spot strategies and Kubernetes optimization.



- **[Karpenter Enterprise / commercial Karpenter offerings](https://karpenter.sh/)**  

  Enterprise-supported distributions and managed services built on or extending the open-source Karpenter project.



- **[CloudPilot AI and related optimizers](https://cast.ai/)**  

  Additional AI-driven platforms that automate instance selection, spot usage, and cluster cost reduction.



- **[Other cloud cost & spot platforms](https://spot.io/)**  

  Solutions from cloud providers and FinOps vendors that include spot automation, interruption handling, and commitment optimization.



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
