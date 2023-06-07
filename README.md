
Azure Devops:

What is difference b/w Deployment group and Environments?

They both have the same theory in actual deployment. But, since Deployment group jobs are not yet supported in YAML. In this case, the Environments comes up.

What is difference b/w build pipeline and release pipeline?

A Build Pipeline is used to generate Artifacts out of Source Code. 
A Release Pipeline consumes the Artifacts and conducts follow-up actions within a multi-staging system

How to configuring approval in azure devops?

In your Azure DevOps project, go to the resource (for example, environment) that needs to be protected.

Navigate to Approvals and Checks for the resource.

Control option give to time out 1 day, 2 days any time give it and apply.

what is b/w Microsoft-hosted agents and Self-hosted agents?

Ans: Microsoft-hosted agents If your pipelines are in Azure Pipelines, then you've got a convenient option to run your jobs using a Microsoft-hosted agent. With Microsoft-hosted agents, maintenance and upgrades are taken care of for you. Each time you run a pipeline, you get a fresh virtual machine for each job in the pipeline. The virtual machine is discarded after one job (which means any change that a job makes to the virtual machine file system, such as checking out code,will be unavailable to the next job). Microsoft-hosted agents can run jobs directly on the VM or in a container. Azure Pipelines provides a predefined agent pool named Azure Pipelines with Microsoft-hosted agents.

Self-hosted agents An agent that you set up and manage on your own to run jobs is a self-hosted agent. You can use self-hosted agents in Azure Pipelines or Azure DevOps Server, formerly named Team Foundation Server (TFS). Self-hosted agents give you more control to install dependent software needed for your builds and deployments. Also, machine-level caches and configuration persist from run to run, which can boost speed.

3-06-2023:

How to enable ci/CD?

Build pipeline --trigger --enable the Contiune intergration 
Release pipeline-- release --contiune deployment trigger.

What is Azure Artifacts?


What Is Deployment groups?

A deployment group is a logical set of deployment target machines that have agents installed on each one. Deployment groups represent the physical environments; for example, "Dev", "Test", or "Production" environment

In effect, a deployment group is just another grouping of agents, much like an agent pool.

Deployment groups are only available with Classic release pipelines and are different from deployment jobs


Deployment groups:

A deployment group is a logical set of deployment target machines that have agents installed on each one. Deployment groups represent the physical environments; for example, “Dev”, “Test”, “UAT”, and “Production”. In effect, a deployment group is just another grouping of agents, much like an agent pool.

Environments:

Environment represents a collection of resources such as namespaces within Kubernetes clusters, Azure Web Apps, virtual machines, databases, which can be targeted by deployments from a pipeline.


What is azure Artifacts?

Azure Artifacts enables developers to share their code efficiently and manage all their packages from one place. With Azure Artifacts, developers can publish packages to their feeds and share it within the same team, across organizations, and even publicly.

Developers can also consume packages from different feeds and public registries such as NuGet.org or npmjs.com. Azure Artifacts supports multiple package types such as NuGet, npm, Python, Maven, and Universal Packages.

Need to create new feed in artifacts 
and create new pipeline for using need feed like Nuget--pack and push.
then run pipeline along with feed once it get success add to feed to our pipeline.

Just open build pipeline add task like nuget and added feed then run pipeline artifacts will store that place.

2nd Way:

Through visula studio create new project-- dependecy package source-browse some xyz feed 
3rd way:

and through run power shell will particaller command will configure we use it.


Git:
1.What is difference b/w Rebase and Merge?

Merging is a safe option that preserves the entire history of your repository, 
while rebasing creates a linear history by moving your feature branch onto the tip of main

2.What is difference b/w merge and squash?
squash merge gives you just the file changes, and a regular merge gives you the file changes and the commit history

As a refresher, the difference between a “squash commit” and a “merge commit” is that a regular “merge” includes all the Git commits in the history of the target branch, while “squash” flattens them to one commit.

AKS:
1) Why is load balancer needed?

A load balancer is needed because it gives a standard way to distribute network traffic among different services, which runs in the backend.
2) Define Ingress Network

Ingress network is defined as a collection of rules which allow permission for connections into the Kubernetes cluster.

3) Explain Replica set

A Replica set is used to keep replica pods stable. 
It enables us to specify the available number of identical pods.
This can be considered a replacement for the replication. Controller

4) What do you mean by persistent volume?

A persistent volume is a storage unit that is controlled by the administrator. It is used to manage an individual pod in a cluster.

5) Explain PVC?

The full form of PVC stands for Persistent Volume Claim. It is storage requested by Kubernetes for pods. The user does not require to know the underlying provisioning. This claim should be created in the same namespace where the pod is created.

1.What is differebce b/w configmap and Secrets?

The big difference between Secrets and ConfigMaps are that Secrets are obfuscated with a Base64 encoding. but it is good practice to use Secrets for confidential data (like API keys) and ConfigMaps for non-confidential data (like port numbers).
kubectl create secret generic apikey --from-literal=API_KEY=123–456
kubectl create configmap language --from-literal=LANGUAGE=English

2.What is difference b/w a replication controller and replica set?

The major difference between a replication controller and replica set is that the rolling-update command works with Replication Controllers, but won't work with a Replica Set. This is because Replica Sets are meant to be used as the backend for Deployments.

3.What difference b/w Deployments, statefulset and daemonsetes?

Deployments are great for stateless applications that can be easily scaled horizontally. StatefulSets are great for applications that require persistent storage and have state that needs to be maintained DaemonSets are great for running an application on every node in the cluster.

4.What is auto scalling ? 

Kubernetes enables autoscaling at the cluster/node level as well as at the pod level, two different but fundamentally connected layers of Kubernetes architecture.

Horizontal Pod Autoscaling
In Kubernetes, a HorizontalPodAutoscaler automatically updates a workload resource (such as a Deployment or StatefulSet), with the aim of automatically scaling the workload to match demand.

Horizontal scaling means that the response to increased load is to deploy more Pods. This is different from vertical scaling, which for Kubernetes would mean assigning more resources (for example: memory or CPU) to the Pods that are already running for the workload.

If the load decreases, and the number of Pods is above the configured minimum, the HorizontalPodAutoscaler instructs the workload resource (the Deployment, StatefulSet, or other similar resource) to scale back down

kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10

5.How do you scale Kubernetes pods automatically?

Kubernetes Automatic Scaling with the Horizontal Pod Autoscaler (HPA) Object. The Kubernetes HorizontalPodAutoscaler object updates pods, deployments and statefulsets to match demands by automatically scaling workloads. The HPA's response to increased load is to dynamically provision additional pods


What is Ingress Controller?

Ingress Controller is an intelligent Load Balancer. Ingress is a high-level abstraction responsible for allowing simple host or URL based HTTP routing. It is always implemented using a third-party proxy. These implementations are nothing but Ingress Controller. It is a Layer-7 load balancer.

1.NGINX-Based Ingress Controllers

This is the most popular and only open-source Ingress Controller maintained by the K8s team, built on top of NGINX reverse proxy. It is a popular option for simple HTTP/S routing and SSL termination use case. Hence of the popularity, there is comprehensive documentation and tutorials available for common ingress tasks and related tools

2.Kubernetes Ingress Controller with a LoadBalancer

Whatever is your ingress strategy, you presumably will need to start with an external load balancer. This will route traffic to a K8s service on the cluster that will perform service-specific routing. In this setup, your load balancer provides a stable endpoint which is nothing but an IP address for external traffic to access.

Both ingress controllers and K8s services require an external load balancer. So, this concludes that NodePort is not designed to be directly used for production

![image](https://github.com/krishnamsdpl/krishnamsdpl.github.io/assets/30367367/049efc8b-8e76-4b7a-a67d-1a659d9c0cf2)

3. Cloud-Based Ingress Controller

4. Opensource Ingress Controller

5. HAProxy-Based Ingress Controllers

6. F5 Container Ingress



Terraform:

All defined variables must have values in order to run Terraform code.

Once you set a default value for a variable, it becomes optional.

What is terraform plan and terraform validate? 

What is the difference between Terraform null resource and provisioner?
The null_resource implements the standard resource lifecycle but takes no further action.
The local-exec provisioner invokes a local executable after a resource is created

04-06-2023:

Terraform with Azure Devops lab need to practice

https://github.com/nextopsvideos/terraform_ado/blob/main/Azure%20Powershell%20Task%20File

https://www.youtube.com/watch?v=3WgI7EJAULo&list=PLFoX_td1iTj8U74ZxVRNkEebG3pb2Gdpb&index=13


05-06-2023:

![image](https://github.com/krishnamsdpl/krishnamsdpl.github.io/assets/30367367/c1531ac7-276c-4372-bc17-a69efd24c616)


What is Terraform Workspace?

If we use the local backend for storing Terraform state, Terraform creates a file called terraform.tfstate to store the state of the applied configuration. 
However, in scenarios where you want to use the same configuration for different contexts, separate states might be necessary with same configuration.

Workspaces allows you to separate your state and infrastructure without changing anything in your code when you wanted the same exact code base to deploy to multiple environments without overlap. i.e. Workspaces help to create multiple state files for set of same terraform configuration files.

Each of environments required separate state files to avoid collision. With the use of workspaces, you can prepend the workspace name to the path of the state file, ensuring each workspace (environment) had its own state

Key Points:

1.With Workspaces, we can set deploy different environment with same terraform configuration files.

2.To manage multiple distinct sets of infrastructure resources (e.g. multiple environments), we can use Workspaces.

3.Workspaces isolate Terraform state. It is a best practice to have separate state per environment. Workspaces are technically equivalent to renaming your state file.

4.Workspaces ensure that the environments are isolated and mirrored.

5.Workspaces are the successor to old Terraform Environments.


Use Cases
Workspaces are convenient in a number of situations:

Multiple Environments:

One common need in infrastructure management is to build multiple environments, with mostly the same setup but keeping a few variables different, like networking and sizing.
1. Production
2. Staging
3. Development


Multiple Regions/Locations: Replicate infrastructure in multiple places for High Availability (HA) and Disaster Recovery (DR).

1. us-east-1
2. eu-west-2


Multiple Accounts/Subscriptions: Create infrastructure in multiple accounts.
1. Cloud Account 1
2. Cloud Account 2


Testing and Research: Quickly create a new infrastructure for temporary pilot testing, freely experiment or R&D purpose, and destroy it with single command.


