# Welcome to the Durable Task Scheduler repository

## How to Use This Repository 
This GitHub repository serves as a centralized hub for users of the Durable Task Scheduler to open issues, submit feature requests, and track overall progress and upcoming roadmap items. 

#### For feature requests, ongoing issues, or general questions, please use the "Issues" forum and apply the appropriate labels to your submissions.

#### To track ongoing and upcoming investments, visit the "Roadmap" project board under "Projects" (WIP).

Below, you'll find some helpful references to learn more about and try out the Durable Task Scheduler:
- Documentation: https://aka.ms/dts-documentation
- Samples: https://aka.ms/dts-samples
- Blog announcement: https://aka.ms/dts-public-preview

# About the Durable Task Scheduler
![Durable Task Scheduler in all Azure Computes](./media/images/dts-in-all-computes.png)
The Durable Task Scheduler is a solution for durable execution in Azure. It ensures fault-tolerant code execution by handling failures and interruptions through automatic retries and state persistence. This makes it ideal for scenarios such as distributed transactions, multi-agent orchestration, data processing, infrastructure management, and more.

When paired with a developer orchestration framework like Durable Functions or the Durable Task SDKs, the Durable Task Scheduler empowers developers to create stateful applications that run on any compute environment without needing to architect for fault tolerance.

Developers can use the durable task scheduler with the following orchestration frameworks: 
- [Durable Functions](https://learn.microsoft.com/azure/azure-functions/durable/durable-functions-overview) 
- Durable Task SDKs, also referred to as "portable SDKs"
- [Durable Task Framework](https://github.com/Azure/durabletask) 

## Azure Functions durable task scheduler

The durable task scheduler is a solution for durable execution in Azure. Durable execution is a fault-tolerant approach to running code that handles failures and interruptions through automatic retries and state persistence. Scenarios where durable execution is required include distributed transactions, multi-agent orchestration, data processing, infrastructure management, and others. Coupled with a developer orchestration framework like Durable Functions or the Durable Task SDKs, the durable task scheduler enables developers to author stateful apps that run on any compute environment without the need to architect for fault tolerance. 

### Use with Durable Functions and Durable Task Framework
When used with Durable Functions, a feature of Azure Functions, the durable task scheduler plays the role the ["backend provider"](https://learn.microsoft.com/azure/azure-functions/durable/durable-functions-storage-providers), where state data is persisted as the app runs. While other backend providers are supported, only the durable task scheduler offers a fully managed experience, which removes operational overhead from users. Additionally, the scheduler offers exceptional performance, reliability, and the ease of monitoring orchestrations. 

The durable task scheduler plays a similar role in the Durable Task Framework as in Durable Functions. 

### Use with Durable Task SDKs or "portable SDKs"
The Durable Task SDKs provide a lightweight client library for the durable task scheduler. When running orchestrations, apps using these SDKs would make a connection to the scheduler's orchestration engine in Azure. These SDKs are called "portable" because apps that leverage them can be hosted in various compute environments, such as Azure Container Apps, Azure Kubernetes Service, Azure App Service, or VMs. 

![Durable Task Scheduler in all Azure Computes](./media/images/dts-in-all-computes.png)

For more information on how to use the Azure Functions durable task scheduler and to explore its features, please refer to the [official documentation](https://aka.ms/dts-documentation)

## Choosing your orchestration framework
This repo contains samples in different directories for all orchestration frameworks supported by the durable task scheduler. The following table provides some considerations when choosing a framework. 

|Consideration | Portable SDKs | Durable Functions | Durable Task Framework|
|--------------| --------------| ------------------| --------------------- | 
|Hosting option| Azure Container Apps, Azure Kubernetes Service, Azure App Service, VMs | Azure Functions | Azure Container Apps, Azure Kubernetes Service, Azure App Service, VMs |
|Language support | [.NET](https://github.com/microsoft/durabletask-dotnet/), [Python](https://github.com/microsoft/durabletask-python), [Java (coming soon)](https://github.com/microsoft/durabletask-java), [JavaScript (coming soon)](https://github.com/microsoft/durabletask-js) | [.NET](https://github.com/Azure/azure-functions-durable-extension), [Python](https://github.com/Azure/azure-functions-durable-python), [Java](https://github.com/microsoft/durabletask-java), [JavaScript](https://github.com/Azure/azure-functions-durable-js), [PowerShell](https://github.com/Azure/azure-functions-powershell-worker/tree/dev/examples/durable) | [.NET](https://github.com/Azure/durabletask) |
|Official support| No | Yes | No |
|Durable task scheduler emulator| Available | Available |Available |
|Monitoring dashboard| Available | Available <sup>1</sup> | Available <sup>1</sup>|
|[Durable Entities](https://learn.microsoft.com/azure/azure-functions/durable/durable-functions-entities)| Not supported | Supported | Not supported|
|Other supported feature(s)| Scheduler| Azure Functions triggers and bindings ||

*<sup>1</sup> The out-of-the-box monitoring dashboard is available only when using the durable task scheduler as the backend provider.*

> **Note:** For all **new apps**, we recommend the portable SDKs over the Durable Task Framework as the former follows more modern .NET conventions and will be the focus of our future investments.

## Tell us what you think

Your feedback is essential in shaping the future direction of this product. We encourage you to share your experiences, both the good and the bad. If there are any missing features or capabilities that you would like to see supported in the Durable Task Scheduler, we want to hear about them.

> **Note:** This is an early-stage version of the product. You can share your feedback either by dropping us an issue in this repo (other private preview users will see your issue) or send an email to our product managers Nick and Lily ([nicholas.greenfield@microsoft.com](mailto:nicholas.greenfield@microsoft.com); [jiayma@microsoft.com](mailto:jiayma@microsoft.com)).
