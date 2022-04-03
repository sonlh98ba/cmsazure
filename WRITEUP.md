# Why did I choose App service instead of VM deployment

## Features of this application

1. According to what has been learned, we have 2 options for this project:
   - Virtual Machine Based deployment - VM
   - Azure App Services - AAS

=> I choose the Azure App Service instead of Virtual Machine Based deployment due to the reasons mentioned below!

## Reasons for choosing to use Azure App Services instead of Virtual Machine

1. Reason 1: Deploying on VM will cost extra for SSL. (Advantage in cost)(+1 point for AAS)

2. Reason 2: This is a basic application based on 2 components (Application & Database) in which there are no specific hardware and unique software constraints (DB is deployed outside application deployment boundaries). Therefore, the most suitable solution in this case is the App Service Deployment (which support specific set of platforms such as .NET, Python, NodeJS, .etc) (Advantage in workflow) (+1 point for AAS)

3. Reason 3: This CMS application is a web application that is not based on layered or complex architectures. It is not an application that follows architectures like N-Tiers or Big Compute. Additionally it's not currently need an Event Driven Framework or Scalable Micro-service style. Therefore, it is not necessary to use a VM. (Advantage in scalability)(VM = AAS)

4. Reason 4: DevOps Optimization - Set up continuous integration and deployment with Azure DevOps, GitHub, BitBucket, Docker Hub, or Azure Container Registry. Promote updates through test and staging environments. Manage your apps in App Service by using Azure PowerShell or the cross-platform command-line interface (CLI). See reference [here](https://docs.microsoft.com/en-us/azure/app-service/overview) (Advantage in workflow)(+1 point for AAS)

5. Reason 5: The cost is substantially lower when compared to a VM where you need manage OS, patches and application deployment manually (IaaS). Additionally a free tier with 1 GB RAM with 1GB storage with F1 instance can be used for dev with no cost overhead. This is more cost effective especially with Linux workload. On the other hand VM (especially the reserved VM or PAYG) is much more expensive as Spot instances can't be used for this CMS app. Although a general purpose VM (AV2) costs much less, which only provide zonal redundancy. On the other hand a compute optimized VM (e,g FSv2) costs no less than 0.01. But A VM has admin overhead such as backup restore. Although IaaS (VM), looks to be cheaper, it has much higher TCO and operating cost. See reference [here](https://www.bmc.com/blogs/saas-vs-paas-vs-iaas-whats-the-difference-and-how-to-choose/)(Advantage in cost)(+1 point for AAS)

6. Reason 6: If we choose VM (IaaS) where there is a cost in managing VMs along with the associated networking and storage components. But App Service provides a managed hosting environment, where we can deploy your application without needing to manage VMs or networking resources. Azure App Service is a PaaS service. (Advantage in cost and another efforts such as human resources,...)(Advantage in cost)(+1 point for AAS)

### Assess app changes that would change your decision

In the future depends on technology changes and other non-function needs could change the above decision.

1. If we have to use more complex and demanding technology stacks such as micro services architecture then we are likely to think about using VM.

2. This CMS application is quite simple, so using Azure App Service will make the deployment process easier and more developer-friendly.

3. After deploying the application and going into actual use, depending on the performance needs and required upgrades from the users, we can think about switching to using a VM.

4. Deploying the application to a VM may happen in the future, but don't worry because this CMS is quite simple so migrating it to a VM is also very easy
