---
title: 'Standard enterprise governance: Improve the Cost Management discipline'
description: Use the Cloud Adoption Framework for Azure to learn about adding cost controls to a simple governance minimum viable product (MVP).
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/05/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: internal
---

# Standard enterprise governance guide: Improve the Cost Management discipline

This article advances the narrative by adding cost controls to the governance MVP.

## Advancing the narrative

Adoption has grown beyond the cost tolerance indicator defined in the governance MVP. This is a good thing, as it corresponds with migrations from the DR datacenter. The increase in spending now justifies an investment of time from the cloud governance team.

### Changes in the current state

In the previous phase of this narrative, IT had retired 100% of the DR datacenter. The application development and BI teams were ready for production traffic.

Since then, some things have changed that will affect governance:

- The migration team has begun migrating VMs out of the production datacenter.
- The application development teams are actively pushing production applications to the cloud through CI/CD pipelines. Those applications can reactively scale with user demands.
- The business intelligence team within IT has delivered several predictive analytics tools in the cloud. The volumes of data aggregated in the cloud continues to grow.
- All of this growth supports committed business outcomes. Costs have begun to balloon. Projected budgets are growing faster than expected. The CFO needs improved approaches to managing costs.

### Incrementally improve the future state

Cost monitoring and reporting is to be added to the cloud solution. IT is still serving as a cost clearing house. This means that payment for cloud services continues to come from IT procurement. Reporting should tie direct operating expenses to the functions that are consuming the cloud costs. This model is referred to as a *showback* cloud accounting model.

The changes to current and future state expose new risks that will require new policy statements.

## Changes in tangible risks

**Budget control:** There is an inherent risk that self-service capabilities will result in excessive and unexpected costs on the new platform. Governance processes for monitoring costs and mitigating ongoing cost risks must be in place to ensure continued alignment with the planned budget.

This business risk can be expanded into a few technical risks:

- Actual costs might exceed the plan.
- Business conditions change. When they do, there will be cases when a business function needs to consume more cloud services than expected, leading to spending anomalies. There is a risk that this extra spending will be considered overages, as opposed to a necessary adjustment to the plan.
- Systems could be overprovisioned, resulting in excess spending.

## Incremental improvement of the policy statements

The following changes to policy will help remediate the new risks and guide implementation.

- All cloud costs should be monitored against plan on a weekly basis by the governance team. Reporting on deviations between cloud costs and plan is to be shared with IT leadership and finance monthly. All cloud costs and plan updates should be reviewed with IT leadership and finance monthly.
- All costs must be allocated to a business function for accountability purposes.
- Cloud assets should be continually monitored for optimization opportunities.
- Cloud governance tooling must limit asset sizing options to an approved list of configurations. The tooling must ensure that all assets are discoverable and tracked by the cost monitoring solution.
- During deployment planning, any required cloud resources associated with the hosting of production workloads should be documented. This documentation will help refine budgets and prepare additional automation to prevent the use of more expensive options. During this process consideration should be given to different discounting tools offered by the cloud provider, such as reserved instances or license cost reductions.
- All application owners are required to attend trained on practices for optimizing workloads to better control cloud costs.

## Incremental improvement of best practices

This section of the article will change the governance MVP design to include new Azure policies and an implementation of Azure Cost Management + Billing. Together, these two design changes will fulfill the new corporate policy statements.

1. Implement Azure Cost Management + Billing.
    1. Establish the right scope of access to align with the subscription pattern and the Resource Consistency discipline. Assuming alignment with the governance MVP defined in prior articles, this requires **enrollment account scope** access for the cloud governance team executing on high-level reporting. Additional teams outside of governance may require **resource group scope** access.
    1. Establish a budget in Azure Cost Management + Billing.
    1. Review and act on initial recommendations. Have a recurring process to support reporting.
    1. Configure and execute Azure Cost Management + Billing reporting, both initial and recurring.
2. Update Azure Policy
    1. Audit the tagging, management group, subscription, and resource group values to identify any deviation.
    1. Establish SKU size options to limit deployments to SKUs listed in deployment planning documentation.

## Conclusion

Adding these processes and changes to the governance MVP helps remediate many of the risks associated with cost governance. Together, they create the visibility, accountability, and optimization needed to control costs.

## Next steps

As cloud adoption continues and delivers additional business value, risks and cloud governance needs will also change. For the fictional company in this guide, the next step is using this governance investment to manage multiple clouds.

> [!div class="nextstepaction"]
> [Multicloud evolution](./multicloud-improvement.md)
