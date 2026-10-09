---
title: "Costing estimates for Hybrid deployment"
slug: "costing-estimates-for-hybrid-deployment-with-aws-outpost"
updated: 2026-10-05T19:53:56Z
published: 2026-10-05T19:53:56Z
canonical: "helpcenter.securiti.ai/costing-estimates-for-hybrid-deployment-with-aws-outpost"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Costing estimates for Hybrid deployment

This article explains how costs are calculated for Hybrid deployment with AWS Outpost. It shows estimated daily costs for different operational scenarios based on default configuration settings.

Outpost deployment costs fall into two categories:

- Fixed costs
- Variable costs

## Fixed costs

Fixed costs are services that are installed and deployed as part of your Outpost setup. These costs remain the same whether your system is idle or actively scanning.

Fixed costs include:

- ElastiCache cluster for data caching
- Baseline system nodes (four on-demand nodes)
- Elastic Kubernetes Service (EKS) control plane for orchestration
- Virtual Private Cloud (VPC) endpoints and networking infrastructure
- Key Management Service (KMS) and Secrets Manager for security

## Variable costs

Variable costs scale up when you run scans and scale down when your system is idle. These services automatically adjust based on your workload.

Variable costs include:

- Elastic Compute (EC2) Spot compute for scanning workers
- S3 requests and object operations
- Data transfer and NAT gateway costs
- Monitoring, metrics, and logs
- Attached storage (Elastic Block Store (EBS) volumes)

## Estimated daily costs

The table below shows estimated daily costs for different scenarios based on default Outpost settings:

> [!NOTE]
> **Note**
> 
> - The costs shown are estimated daily rates during active scans. Actual spending varies throughout a scan based on when scanning workers scale up and down, network rate limits taking effect, and how long the scan runs each day.
> - These costs represent the standard setup most customers use when they start. If you increase the maximum node pool size to improve scan performance, your costs become higher than shown here.
> - For exact costs, check AWS Cost Explorer filtered by your OutpostId to see your actual costs specific to your deployment and usage patterns.

| **Service Component** | **Fixed cost per day ($)** | **Variable cost per day ($)** |
| --- | --- | --- |
|  | **Idle cost** | **Discovery Scan** | **Data Inventory Sync** |
| Amazon EC2 Compute | $12.25 | $290.57 | $396.56 |
| Amazon S3 (Storage & Requests) | $0.03 | $137.47 | $135.13 |
| CloudWatch Logs & Metrics | $1.36 | $43.22 | $51.49 |
| EC2-Other (Data Transfer & EBS) | $6.77 | $49.78 | $48.32 |
| Amazon Managed Service for Prometheus | $5.75 | $12.11 | $18.15 |
| Amazon EKS Control Plane | $3.26 | $2.90 | $4.80 |
| Amazon ElastiCache | $1.03 | $0.93 | $1.54 |
| Amazon Virtual Private Cloud (VPC) | $0.96 | $0.89 | $1.53 |
| KMS, ECR & Secrets Manager | $0.06 | $0.13 | $0.31 |
| Total daily cost estimate | $31.47 | $538.00 | $657.83 |

Use the following list to understand the costing scenarios provided in the table:

- **Idle baseline** - Your Outpost is deployed and running but not actively scanning. This represents your minimum daily cost.
- **Discovery scan** - Your system is performing a discovery scan, which identifies resources in your environment.
- **Data Inventory Sync** - Your system is performing a data inventory sync to build inventory, which provides detailed analysis of resources. Data Inventory Synn typically costs more than discovery scans.

> [!WARNING]
> Important
> 
> Amazon EC2 compute cost is significantly higher for Data Inventory Sync because it processes substantially more files than Discovery Scans.
