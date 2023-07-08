1. What is the smallest unit in Kubernetes?

Pod


2. What does CNCF stand for?

Cloud Native Computing Foundation


3. What are the 4Cs of Cloud Native Security?

Code, Container, Cluster, Cloud


4. What is the most common autoscaling method in the world of cloud-native?

Horizontal Scaling


5. What does serverless computing not need?

Cloud
Servers
The provisioning and operating infrastructure
Code

Explanation:
Serverless computing, also known as Function as a Service (FaaS), is a cloud computing model where developers can write and deploy code without worrying about the underlying infrastructure. Serverless computing does not require the following:

Server Management: With serverless computing, developers do not need to manage or provision servers. The cloud provider abstracts away the server infrastructure, and developers can focus solely on writing code and defining functions.

Infrastructure Scaling: Scaling is handled automatically by the serverless platform. The provider dynamically scales the infrastructure resources up or down based on the incoming request load. Developers do not need to manually scale servers or worry about resource provisioning.

Capacity Planning: Unlike traditional server-based architectures, serverless computing eliminates the need for capacity planning. Developers do not have to estimate or provision resources to handle peak loads or sudden traffic spikes. The serverless platform automatically scales to accommodate the demand.

Server Maintenance: Serverless computing removes the burden of server maintenance tasks. Developers do not need to perform software updates, security patches, or manage server configurations. The cloud provider takes care of maintaining the server infrastructure and ensuring its reliability.

Operating System Configuration: Serverless platforms abstract the underlying operating system, and developers do not need to configure or manage the operating system settings. They can focus solely on writing application logic without worrying about compatibility or dependencies.

Idle Resource Costs: Serverless computing allows for efficient resource utilization. When functions are not actively processing requests, no resources are consumed, and therefore, no costs are incurred. Resources are allocated dynamically as requests come in, and deallocated when the functions are idle.

Serverless computing abstracts away the infrastructure and operational aspects, enabling developers to focus on writing code and delivering value without being concerned about managing servers, scaling, or infrastructure maintenance.


6. Which of the following is not a fundamental metric used in Site Reliability Engineering?

Service Level Objective (SLO)
Service Level Indicator (SLI)
Service Level Definition (SLD)
Service Level Agreement (SLA)

Explanation:
Among the options provided, "Service Level Definition (SLD)" is not a fundamental metric used in Site Reliability Engineering (SRE).

The correct term for the metric associated with service levels is "Service Level Agreement (SLA)." An SLA is a formal agreement or contract between a service provider and its users, specifying the level of service that the provider commits to deliver. It typically includes measurable targets known as Service Level Objectives (SLOs) and the corresponding metrics known as Service Level Indicators (SLIs).

SLIs are quantitative measurements that represent different aspects of service performance, such as availability, latency, error rates, throughput, etc. These metrics help assess the health and reliability of a system.

On the other hand, "Service Level Definition (SLD)" is not a common term used in the context of SRE. It does not represent a fundamental metric but rather appears to be a hypothetical term.


7. The Kubernetes object "Stateful Set" requires which service for the network identity of Pods?

ClusterIP
NodePort
LoadBalancer
Headless Service

Explanation:
A StatefulSet is a Kubernetes controller that manages a set of stateful pods. Each pod created by a StatefulSet has a stable and unique network identity, including a hostname and a stable network identity even if the pod is rescheduled or restarted.

To provide the network identity for StatefulSet pods, a Headless Service is used. A Headless Service is a Kubernetes service without a cluster IP. It allows each pod in the StatefulSet to have its own DNS record and DNS identity. This allows other services or applications to discover and communicate with the pods directly by their unique DNS names.

Therefore, when using a StatefulSet in Kubernetes, you would typically define and associate a Headless Service to enable the network identity and discoverability of the StatefulSet pods.


8. The Open Container Initiative (OCI) provides container standards for ?

Runtime, Image, Distribution

Explanation:
OCI is an open governance structure under the Linux Foundation that aims to create open industry standards for container formats and runtime. These standards ensure interoperability and portability across different containerization platforms.

The OCI specifications cover the following areas:

Runtime: OCI defines the runtime specification, which describes the lifecycle of a container, including how containers are started and stopped, the configuration and isolation of containers, and the management of container processes.

Image: OCI provides the image specification, which defines a standardized format for container images. This specification specifies how container images are built, stored, and distributed. It defines the container image layout, metadata, and configuration.

Distribution: OCI also offers the distribution specification, which addresses the distribution of container images. It defines a standard protocol for securely pulling and pushing container images across different container registries and platforms.

By providing these container standards, OCI ensures that containers built using OCI-compliant tools and platforms can be run and distributed consistently across different container runtimes and environments. This interoperability allows for greater flexibility and choice for developers and organizations using container technologies.


9. Which of the following Computing model doesn't require provisioning of infrastructure?

EC2 Instances
Infrastructure as Service
Serverless
Bare Metal Model

Explanation:
Among the options provided, the computing model that does not require provisioning of infrastructure is the "Serverless" model.

In the Serverless computing model, also known as Function as a Service (FaaS), developers can write and deploy code without the need to provision or manage underlying infrastructure. In this model, the cloud provider abstracts away the infrastructure, and developers can focus solely on writing code and defining functions. The provider takes care of dynamically allocating resources and scaling based on demand, without any manual provisioning required.

On the other hand, the other options mentioned do involve infrastructure provisioning:

EC2 Instances: EC2 (Elastic Compute Cloud) instances are part of Amazon Web Services (AWS) and represent virtual servers in the cloud. When using EC2, you need to provision and manage the instances yourself, including selecting the instance type, specifying the capacity, and managing the operating system and software configurations.

Infrastructure as a Service (IaaS): IaaS involves provisioning and managing virtualized infrastructure resources such as virtual machines, storage, networks, etc. With IaaS, you have more control over the infrastructure compared to serverless, but you are still responsible for managing and provisioning the infrastructure components.

Bare Metal Model: The Bare Metal model refers to the use of physical servers or machines without a hypervisor or virtualization layer. In this case, you need to provision and manage the underlying hardware infrastructure yourself, including the installation and configuration of the operating system and software stack.

In summary, the Serverless model is the computing model that abstracts away infrastructure provisioning, allowing developers to focus solely on writing code and functions.


10. What are the main part of a Service Mesh?

Master plane and worker node
Kube-scheduler and controller manager
Data plane and Control plane
Discovery plane and date plane

Explanation:
The main components of a Service Mesh architecture are the Control Plane and the Data Plane.

Control Plane: The Control Plane is responsible for managing and controlling the behavior of the Service Mesh. It includes components that handle traffic management, service discovery, policy enforcement, and telemetry collection. Some popular examples of Control Plane components are Istio's Pilot, Mixer, and Citadel.

Data Plane: The Data Plane is where the actual network traffic flows and is intercepted and managed by the Service Mesh. It consists of a set of proxies (usually sidecar proxies) deployed alongside each service or workload. These proxies intercept network traffic between services, apply policies defined by the Control Plane, and collect telemetry data for monitoring and observability.

The Control Plane and Data Plane work together to provide advanced features and capabilities for managing, securing, and monitoring microservices-based applications within a Service Mesh architecture. The Control Plane configures and orchestrates the behavior of the Data Plane proxies to achieve the desired functionality and observability across the services.

The other options mentioned in your question, such as the Master plane and worker node (commonly used in container orchestration platforms like Kubernetes) and components like Kube-scheduler and controller manager, are related to container orchestration and management rather than specifically being part of a Service Mesh architecture.

While the Discovery Plane is not a standard component in Service Mesh, service discovery is indeed a functionality provided by the Control Plane of a Service Mesh to enable dynamic service-to-service communication and load balancing.


11. Kubernetes was originally developed by who?

Google

Explanation:
Kubernetes was originally developed by a team of engineers at Google. The project was initiated by Joe Beda, Brendan Burns, and Craig McLuckie, who were part of Google's Borg system—a large-scale internal container orchestration platform used by Google to manage their applications.

In 2014, Google open-sourced Kubernetes and donated it to the Cloud Native Computing Foundation (CNCF), a Linux Foundation project, to be developed and maintained as an open-source container orchestration platform. Since then, Kubernetes has gained widespread adoption and has become one of the most popular and widely used container orchestration systems in the industry.


12. What are the TWO types of Kubernetes nodes? Select TWO answers.

Worker Node
Internal Node
Control Plane Node
Data plane

Explanation:
The two types of Kubernetes nodes are:

Worker Node: Worker nodes, also known as compute nodes, are responsible for running the application workloads in the Kubernetes cluster. These nodes execute the tasks assigned to them by the control plane and host the containers or pods that make up the applications. Worker nodes handle the actual processing and resource utilization.

Control Plane Node: The control plane, also called the master node or the control node, is responsible for managing and controlling the cluster's overall state and coordinating operations. It includes components such as the API server, scheduler, controller manager, and etcd. The control plane ensures the desired state of the cluster is maintained and manages the scheduling and orchestration of workloads across worker nodes.

Therefore, the correct answers are:

Worker Node
Control Plane Node


13. Which of the following is the name of the agent that run on each Kubernetes worker node?

etcd
kube-API server
kube-proxy
kubelet

Explanation:
The agent that runs on each Kubernetes worker node is called "kubelet."

The kubelet is a Kubernetes component responsible for managing and maintaining the state of each node in the cluster. It communicates with the control plane components and performs tasks to ensure the desired state of the node and its associated workloads. The kubelet receives instructions from the control plane and takes actions to create, start, stop, and monitor containers or pods on the worker node.

The other options mentioned are:

etcd: etcd is a distributed key-value store used by Kubernetes to store the cluster's configuration data, such as the state of the cluster, service discovery information, and other metadata. It is not specific to the worker nodes.

kube-API server: The kube-API server is a control plane component that exposes the Kubernetes API and handles API requests. It is responsible for validating and processing API requests and maintaining the desired state of the cluster. It does not run directly on the worker nodes.

kube-proxy: kube-proxy is another Kubernetes component responsible for network proxying and load balancing. It helps to maintain network connectivity between services within the cluster. While kube-proxy runs on worker nodes, it is not the agent specifically associated with the worker node itself.

Therefore, the correct answer is:

kubelet


14. Which of the following is not part of the Control Plane in Kubernetes?

etcd
kube-API server
kube scheduler
kube-proxy

Explanation:
The component that is not part of the Control Plane in Kubernetes is "kube-proxy."

The Control Plane in Kubernetes consists of several key components responsible for managing and controlling the cluster's overall state and operations. These components include:

etcd: etcd is a distributed key-value store that holds the cluster's configuration data, including the state of the cluster, service discovery information, and other metadata. It is a separate component that provides a reliable data store for Kubernetes.

kube-API server: The kube-API server is the central component that exposes the Kubernetes API and serves as the entry point for all administrative and operational actions. It handles API requests, performs authentication and authorization checks, and maintains the desired state of the cluster.

kube-scheduler: The kube-scheduler is responsible for making decisions about which nodes in the cluster should run specific pods. It takes into account factors such as resource requirements, placement constraints, and workload characteristics to ensure optimal scheduling decisions.

On the other hand, "kube-proxy" is not part of the Control Plane. kube-proxy is a network proxy and load balancing component responsible for maintaining network connectivity between services within the cluster. It operates on worker nodes and is not directly involved in managing the overall cluster state or control plane operations.

Therefore, the correct answer is:

kube-proxy


15. Which access control component of Kubernetes is responsible for authorization and decides what a user is allowed to do?

Config Maps
Service Account
Admission Controller
Role-Based Access Control (RBAC)

Explanation:
Which access control component of Kubernetes is responsible for authorization and decides what a user is allowed to do?

Config Maps
Service Account
Admission Controller
Role-Based Access Control (RBAC)

The access control component of Kubernetes responsible for authorization and deciding what a user is allowed to do is "Role-Based Access Control (RBAC)."

RBAC is a built-in authorization mechanism in Kubernetes that allows you to define fine-grained access policies and permissions for users, groups, or service accounts within the cluster. It provides a flexible and granular approach to controlling access to Kubernetes resources.

RBAC uses the following key components:

Roles: Roles are a set of rules that define permissions within a namespace. They specify what actions (verbs) are allowed on which resources (API groups, resources, and specific objects) within a particular namespace.

Role Bindings: Role Bindings associate a role with one or more users, groups, or service accounts. They grant the defined permissions to the associated subjects, allowing them to perform authorized actions within the assigned namespace.

Cluster Roles and Cluster Role Bindings: Cluster Roles and Cluster Role Bindings are similar to Roles and Role Bindings, but they operate across the entire cluster rather than a single namespace. They define permissions and grant access to cluster-level resources.

By configuring RBAC, you can enforce access controls and ensure that only authorized users or service accounts have the necessary permissions to perform specific actions within the Kubernetes cluster.

The other options mentioned are:

Config Maps: Config Maps are a Kubernetes resource that allows you to store and manage configuration data for your applications. They are not directly related to access control or authorization.

Service Account: Service Accounts are a Kubernetes resource used by pods to authenticate and interact with the Kubernetes API. While they play a role in authentication, they do not directly handle authorization or access control.

Admission Controller: Admission Controllers are webhook-based components that intercept and validate API requests before they are persisted in the cluster. While they can enforce certain policies, they are not specifically responsible for authorization decisions.

Therefore, the correct answer is:

Role-Based Access Control (RBAC)


16. Which of the following container runtime is marked as deprecated by Kubernetes?

gVisor
Docker
containerd
CRI-O

Explanation:
As of my knowledge cutoff in September 2021, Docker was marked as deprecated by Kubernetes as a container runtime. Docker was the default container runtime used in earlier versions of Kubernetes. However, Kubernetes has been shifting towards using the Container Runtime Interface (CRI) to decouple the container runtime implementation from the Kubernetes control plane.

Kubernetes supports multiple container runtimes, and containerd has become the recommended and widely adopted container runtime in the Kubernetes ecosystem. containerd is an open-source runtime that provides a core set of container runtime functionalities.

CRI-O is another container runtime option designed specifically for Kubernetes. It is built to be lightweight and integrates with Kubernetes through the CRI, providing a runtime environment for containers.

gVisor, on the other hand, is not a container runtime but a sandboxed container runtime. It provides an additional layer of isolation and security for containers but is not marked as deprecated by Kubernetes.

Please note that the container runtime landscape is subject to change, and it is recommended to refer to the official Kubernetes documentation or the latest updates to determine the current status of container runtimes.


17. Which control plane component is responsible for scheduling pods?

kubelet
kube controller manager
kube scheduler
kube-proxy

Explanation:
The control plane component responsible for scheduling pods in Kubernetes is the "kube-scheduler."

The kube-scheduler is a core component of the Kubernetes control plane that assigns pods to suitable nodes in the cluster based on defined scheduling policies and constraints. It takes into consideration factors such as resource requirements, affinity/anti-affinity rules, node conditions, and pod constraints when making scheduling decisions.

The kube-scheduler continuously monitors the state of the cluster and identifies which nodes have available resources to accommodate the pending pods. It evaluates the constraints and preferences specified in the pod's configuration, along with other cluster-wide policies, to determine the most appropriate node for scheduling the pod.

Once the kube-scheduler selects a node for a pod, it updates the pod's scheduling information, and the kubelet on the chosen node is responsible for pulling the container image, creating the pod, and managing its lifecycle.

To summarize, the kube-scheduler is the control plane component specifically dedicated to making scheduling decisions for pods in Kubernetes.


18. Select TWO commands which can be used to LIST all pods in all namespaces.

kubectl get pods
kubectl get pods -n --all
kubectl get pods -A
kubectl get pods --all-namespaces

Explanation:
The two commands that can be used to list all pods in all namespaces are:
kubectl get pods -A: This command uses the -A flag, which is a shorthand for --all-namespaces. It lists all the pods in all namespaces.
kubectl get pods --all-namespaces: This command explicitly specifies the --all-namespaces flag, which also lists all the pods in all namespaces.

Therefore, the correct commands are:
kubectl get pods -A
kubectl get pods --all-namespaces


19. What is the command to list all the available objects in your Kuberenetes cluster ?

kubectl list api-resources
kubectl get apis
kubectl get api-resources
kubectl api-resources

Explanation:
The command to list all the available objects in your Kubernetes cluster is:

Copy code
kubectl api-resources
Running this command will display a list of all the available resource types (objects) in your Kubernetes cluster, along with their short names, API group, and whether they are namespaced or not.

It provides an overview of the various resources that can be managed and operated within your Kubernetes cluster, including deployments, pods, services, config maps, secrets, and more.


20. Which of these is not a service type in Kubernetes?

ClusterIP
NodePort
Ingress
LoadBalancer

Explanation:
Among the options provided, "Ingress" is not a service type in Kubernetes.

The other three options are valid service types in Kubernetes:

ClusterIP: This service type exposes the service on a cluster-internal IP address, accessible only from within the cluster.

NodePort: This service type exposes the service on a static port on each node in the cluster. It allows external access to the service by routing traffic to the specified port on any cluster node.

LoadBalancer: This service type provisions an external load balancer (e.g., a cloud provider's load balancer) that distributes traffic to the service. It automatically assigns an external IP address to the service for external access.

However, "Ingress" is not a service type but rather an object used to configure rules for routing external traffic into the cluster to specific services. Ingress resources are used in conjunction with an Ingress controller to manage the inbound traffic and perform routing based on rules defined in the Ingress configuration.

So, the correct answer is:

Ingress


21. What language is used to specify and create a Kubernetes resource?

JavaScript
Python
YAML
JSON

Explanation:
The language commonly used to specify and create a Kubernetes resource is YAML (YAML Ain't Markup Language).

Kubernetes resources, such as deployments, services, pods, config maps, and many others, are typically defined using YAML files. YAML is a human-readable data serialization language that is often used for configuration files and data exchange between systems. It provides a structured and easy-to-read format for describing the desired state of Kubernetes resources.

While it is possible to interact with the Kubernetes API using various programming languages and libraries, when creating and defining resources, YAML is the most commonly used language. JSON (JavaScript Object Notation) is also supported, but YAML is generally preferred due to its readability and conciseness.

Therefore, the correct answer is:

YAML


22. Which of the following is not a required field to create a Kubernetes resource?

kind
apiVersion
container
metadata

Explanation:
Among the options provided, "container" is not a required field to create a Kubernetes resource.

When creating a Kubernetes resource, the following fields are required:

kind: The "kind" field specifies the type of resource being created, such as Pod, Deployment, Service, ConfigMap, etc. It defines the kind of object being described in the YAML file.

apiVersion: The "apiVersion" field specifies the version of the Kubernetes API that the resource definition is based on. It ensures compatibility and proper interpretation of the resource definition.

metadata: The "metadata" field includes metadata information for the resource, such as the name, namespace, labels, and annotations. This information is used for identification, organization, and management of the resource.

On the other hand, "container" is not a required field when creating a Kubernetes resource. The "container" field typically appears within the specification of a Pod resource, where it defines the containers to be run within the Pod. However, it is not a top-level field required for all resource types.

Therefore, the correct answer is:

container
