Devops Course:

Git

Github

Docker

Kubernetes

Terraform

Jenkins

Azure cloud

Azure Devops



What is difference b/w Load balancer and API gateways?

What is namespace?

In Kubernetes, namespaces provides a mechanism for isolating groups of resources within a single cluster. 
Names of resources need to be unique within a namespace, but not across namespaces

Namespace List:

default:

Kubernetes includes this namespace so that you can start using your new cluster without first creating a namespace.

kube-node-lease:

This namespace holds Lease objects associated with each node. Node leases allow the kubelet to send heartbeats so that the control plane can detect node failure.

kube-public

This namespace is readable by all clients (including those not authenticated). This namespace is mostly reserved for cluster usage, in case that some resources should be visible and readable publicly throughout the whole cluster. The public aspect of this namespace is only a convention, not a requirement.

kube-system:
The namespace for objects created by the Kubernetes system.

What is Kubernetes Troubleshooting?

Kubernetes troubleshooting is the process of identifying, diagnosing, and resolving issues in Kubernetes clusters, nodes, pods, or containers.

Providing solutions to common errors including CreateContainerConfigError, ImagePullBackOff, CrashLoopBackOff and Kubernetes Node Not Ready.
Explaining initial diagnosis of problems in Kubernetes pods and clusters.
Showing where to find logs and other information required for deeper analysis.

https://komodor.com/learn/kubernetes-troubleshooting-the-complete-guide/#:~:text=Kubernetes%20troubleshooting%20is%20the%20process,prevent%20issues%20in%20Kubernetes%20components.







