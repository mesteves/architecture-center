---
title: Secure DevOps for AKS
titleSuffix: Azure Solution Ideas
author: adamboeglin
ms.date: 12/16/2019
description: Implementing secure DevOps with Kubernetes on Azure, you can achieve the balance between speed and security and deliver code faster at scale.
ms.custom: acom-architecture, devops, signalr service, interactive-diagram, 'https://azure.microsoft.com/solutions/architecture/secure-devops-for-kubernetes/'
ms.service: architecture-center
ms.category:
  - containers
  - devops
ms.subservice: solution-idea
social_image_url: /azure/architecture/solution-ideas/articles/media/secure-devops-for-kubernetes.png
---

# Secure DevOps for AKS

[!INCLUDE [header_file](../header.md)]

DevOps and Kubernetes are better together. Implementing secure DevOps together with Kubernetes on Azure, you can achieve the balance between speed and security and deliver code faster at scale. Put guardrails around the development processes using CI/CD with dynamic policy controls and accelerate feedback loop with constant monitoring. Use Azure Pipelines to deliver fast while ensuring enforcement of critical policies with Azure Policy. Azure provides you real-time observability for your build and release pipelines, and the ability to apply compliance audit and reconfigurations easily.

## Architecture

![Architecture diagram](../media/secure-devops-for-kubernetes.png)
*Download an [SVG](../media/secure-devops-for-kubernetes.svg) of this architecture.*

<!-- markdownlint-disable MD033 -->

<div class="architecture-tooltip-content" id="architecture-tooltip-1">
<p>Developers rapidly iterate, test, and debug different parts of an application together in the same Kubernetes cluster</p>
</div>

<div class="architecture-tooltip-content" id="architecture-tooltip-2">
<p>Code is merged into a GitHub repository, after which automated builds and tests are run by Azure Pipelines</p>
</div>

<div class="architecture-tooltip-content" id="architecture-tooltip-4">
<p>Kubernetes clusters are provisioned using tools like Terraform; Helm charts, installed by Terraform, define the desired state of app resources and configurations</p>
</div>

<div class="architecture-tooltip-content" id="architecture-tooltip-6">
<p>Release pipeline automatically executes pre-defined deployment strategy with each code change</p>
</div>

<div class="architecture-tooltip-content" id="architecture-tooltip-8">
<p>App telemetry, container health monitoring, and real-time log analytics are obtained using Azure Monitor</p>
</div>

## Data Flow

1. Developers rapidly iterate, test, and debug different parts of an application together in the same Kubernetes cluster
1. Code is merged into a GitHub repository, after which automated builds and tests are run by Azure Pipelines
1. Container image is registered in Azure Container Registry
1. Kubernetes clusters are provisioned using tools like Terraform; Helm charts, installed by Terraform, define the desired state of app resources and configurations
1. Operators enforce policies to govern deployments to the AKS cluster
1. Release pipeline automatically executes pre-defined deployment strategy with each code change
1. Policy enforcement and auditing is added to CI/CD pipeline using Azure Policy
1. App telemetry, container health monitoring, and real-time log analytics are obtained using Azure Monitor
1. Insights used to address issues and fed into next sprint plans
