# Write-up

### Analyze, choose, and justify the appropriate resource option for deploying the app.

**Costs** 

Using a VM for the deployment of the CMS application involves the management of the software infrastructure on which the application resides, therefore VM running costs and configuration and maintenance of the OS and the software deployed on the VM are added on top of the costs consumed by the application itself.

In contrast using a PaaS solution like azure web apps allows the deployment of the application code only, and the maintainence of the platform and the operating system is delegated to the cloud provider. This results in less running costs than using an IaaS solution. It is also possible to pre allocate hardware resources through different App service plan tiers

**Scalability**
Scalability in VMs are achieved by virtual machine scale sets and load balancers. This achieves high availability and scalability if the application requires so. 

Azure app service also also supports vertical and horizontal scaling by opting into higher pricing tiers.

**Availability** 
Both VM scale sets and App service provides high availability.  

**Workflow**
To be able to use a VM based solution for the CMS app one would need to be able to first create the VMs in case they are not running already and then build and deploy the application by a custom pipeline. 

In contrast by using github and github actions integration if the app service, the appication deployment is taken care of in an automated fashion and each time there is a commit on the github repository  deployment is automatically performed.  

My choice for the deployment of the Project web application has been to use the PaaS solution and use *azure app service*. Since azure supports python web applications and its integration with github and github actions makes the development and the deployment of the application very easy, I opted for the azure app service. Scaling and increased control over the platform that is provided by the VMs is not necessarily needed for the CMS application case.  

### Assess app changes that would change your decision.

As the application gets more complicated in terms of the resources it uses and the flexibility it requires from the underlying platform a VM based deployment could be preferred over a PaaS solution. By using an IaaS solution, it is possible to choose the underlying hardware that runs tha application. Also in case the application is an existing app that runs on on premise harware, it would be easier to migrate to azure using VMs. Using technologies like docker and kubernetes deployment and orchestration of the application could be made more managable 

