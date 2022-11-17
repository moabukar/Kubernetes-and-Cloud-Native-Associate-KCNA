[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

# Kubernetes-and-Cloud-Native-Associate KCNA

<p align="center">
  <img width="180" src="./pics/KCNA-logo.jpeg">
</p>

Note: A documentation of notes & curated useful resources to help you prepare for the Kubernetes and Cloud Native Associate Exam [(KCNA)](https://training.linuxfoundation.org/certification/kubernetes-cloud-native-associate/) Feel free to share them :)

For any fixes, updates or new additions to the syllabus, please raise an issue or make a pull-request (PR). Thank you! 

- Regardless of you sitting the KCNA exam or not, once you have studied these topics, you will have a good overall understanding of the Cloud-Native, Containers and Kubernetes eco-system. What matters is that you enjoy the learning process. Goodluck on your learning journey!

The KCNA is a certification aimed for individuals who want to advance to the professional level by demonstrating an understanding of the core knowledge and abilities of Kubernetes. This certification is ideal for students learning about or candidates interested in working with cloud native technologies. 

## Exam Brief

- Duration : 1.5 hours
<!-- Number of questions : ??? Multiple choice questions -->
- Passing score: 75%
- Certification validity: 3 years
- Prerequisite: None
- Cost: $250 USD, 1 year exam eligibility, with a free retake within the year.
- Result: Emailed 24 hours after exam completion
- [Official KCNA curriculum](https://github.com/cncf/curriculum/blob/master/KCNA_Curriculum.pdf)
- The exam consists of around 60 MCQ questions.

  *Linux Foundation offer several discounts around the year such as CyberMonday, Kubecon and various other events - ensure to utilise these*

## KCNA topics overview

- [X] [Kubernetes Fundamentals - 46%](#small_blue_diamond-1-kubernetes-fundamentals---46)
- [X] [Container Orchestration - 22%](#small_blue_diamond-2-container-orchestration---22)
- [X] [Cloud Native Architecture - 16%](#small_blue_diamond-3-cloud-native-architecture---16)
- [X] [Cloud Native Observability - 8%](#small_blue_diamond-4-cloud-native-observability---8)
- [X] [Cloud Native Application Delivery - 8%](#small_blue_diamond-5-cloud-native-application-delivery---8)

## Practice questions for KCNA
- [X] [Practice questions](./mock-exam-questions/questions.md)

#### Extra helpful materials

- [x] [Slack](#slack)
- [x] [Books](#books)
- [x] [Youtube Videos](#useful-youtube-videos)

### Useful keys & Common accronyms in Kubernetes

- K8s = Kubernetes
- CNCF = Cloud Native Computing Foundation
- NetPol = Network Policies
- PV = Persistent Volumes
- PVC = Persistent Volume Claims
- CSI = Container Storage Interface
- CNI = Container Network Interface
- CI/CD = Continuous Integration & Continuous Deployment
- RBAC = Role Based Access Control
- OCI = Open Container Initiative
- CRI = Container Runtime Interface
- SMI = Service Mesh Interface
- SLO = Service Level Objectives
- SLI = Service Level Indicators
- SLA = Service Level Agreements

## :small_blue_diamond: 1. Kubernetes Fundamentals - 46%

### 1.1 Fundamental Kuberenetes resources

</details>

- [Pods in Kubernetes](https://kubernetes.io/docs/concepts/workloads/pods/)
<details>
<summary>Pods in K8s - Click arrow to read more</summary>
<br>

Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.

</details>

- [Deployments in Kubernetes](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
<details>
<summary>Deployments in K8s - Click arrow to read more</summary>
<br>

A Deployment provides declarative updates for Pods and ReplicaSets.

You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate. You can define Deployments to create new ReplicaSets, or to remove existing Deployments and adopt all their resources with new Deployments.
</details>

- [Services in Kubernetes](https://kubernetes.io/docs/concepts/services-networking/service/)
<details>
<summary>Services in K8s - Click arrow to read more</summary>
<br>

An abstract way to expose an application running on a set of Pods as a network service.

Types of Services:
ClusterIP: Exposes the Service on a cluster-internal IP. Choosing this value makes the Service only reachable from within the cluster. This is the default ServiceType.

NodePort: Exposes the Service on each Node's IP at a static port (the NodePort). A ClusterIP Service, to which the NodePort Service routes, is automatically created. You'll be able to contact the NodePort Service, from outside the cluster, by requesting <NodeIP>:<NodePort>.

LoadBalancer: Exposes the Service externally using a cloud provider's load balancer. NodePort and ClusterIP Services, to which the external load balancer routes, are automatically created.

ExternalName: Maps the Service to the contents of the externalName field (e.g. foo.bar.example.com), by returning a CNAME record with its value. No proxying of any kind is set up.

Reference: https://kubernetes.io/docs/concepts/services-networking/service/

</details>

- [ReplicaSets in Kubernetes](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/)
<details>
<summary>ReplicaSets in K8s - Click arrow to read more</summary>
<br>

A ReplicaSet's purpose is to maintain a stable set of replica Pods running at any given time. As such, it is often used to guarantee the availability of a specified number of identical Pods.

</details>

<details>

<summary>Headless Services - Click arrow to read more</summary>
<br>

Sometimes you don't need load-balancing and a single Service IP. In this case, you can create what are termed "headless" Services, by explicitly specifying "None" for the cluster IP (.spec.clusterIP).

You can use a headless Service to interface with other service discovery mechanisms, without being tied to Kubernetes' implementation.

</details>

#### Useful Kubernetes commands using kubectl

```sh

kubectl get pods (obtain/list pods in current namespace)

kubectl get pods -A OR kubectl get pods --all-namespaces (obtain pods in all namespaces)

kubectl api-resources (obtain API resources that are retrievable using the kubect commands)

kubectl run nginx --image=nginx (run a pod named nginx using the nginx image)

kubectl create deploy kcna --image=nginx (create a deployment named "kcna" with the nginx image)

kubectl create deploy kcna --image=nginx --replicas=5 (create a deployment named "kcna" with the nginx image that deploys 5 pods (replicas))

```


### 1.2 Kubernetes Architecture

<p align="center">
  <img width="360" src="./pics/k8s-architecture.jpeg.png">
</p>

- [Kubernetes Components Reference](https://kubernetes.io/docs/concepts/overview/components/)

<details>

<summary>K8s components - Click arrow to read more</summary>
<br>

***Control Plane Components***

**kube-apiserver:**

The API server is a component of the Kubernetes control plane that exposes the Kubernetes API. The API server is the front end for the Kubernetes control plane.

The main implementation of a Kubernetes API server is kube-apiserver. kube-apiserver is designed to scale horizontally—that is, it scales by deploying more instances. You can run several instances of kube-apiserver and balance traffic between those instances.

**etcd**
Consistent and highly-available key value store used as Kubernetes' backing store for all cluster data.

**kube-scheduler:**
Control plane component that watches for newly created Pods with no assigned node, and selects a node for them to run on.

**kube-controller-manager:**
Control plane component that runs controller processes.

Logically, each controller is a separate process, but to reduce complexity, they are all compiled into a single binary and run in a single process.

Some types of these controllers are:

Node controller: Responsible for noticing and responding when nodes go down.
Job controller: Watches for Job objects that represent one-off tasks, then creates Pods to run those tasks to completion.
Endpoints controller: Populates the Endpoints object (that is, joins Services & Pods).
Service Account & Token controllers: Create default accounts and API access tokens for new namespaces.

**cloud-controller-manager:**
A Kubernetes control plane component that embeds cloud-specific control logic. The cloud controller manager lets you link your cluster into your cloud provider's API, and separates out the components that interact with that cloud platform from components that only interact with your cluster.
The cloud-controller-manager only runs controllers that are specific to your cloud provider. If you are running Kubernetes on your own premises, or in a learning environment inside your own PC, the cluster does not have a cloud controller manager.

***Worker Node Components***

**kubelet**
An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod.

**kube-proxy**
kube-proxy is a network proxy that runs on each node in your cluster, implementing part of the Kubernetes Service concept.

kube-proxy maintains network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster.

</details>

- [Nodes in K8s](https://kubernetes.io/docs/concepts/architecture/nodes/)
- [Control Plane-Node Communication](https://kubernetes.io/docs/concepts/architecture/control-plane-node-communication/)

<details>
<summary>K8s API - Click arrow to read more</summary>
<br>


**Kubernetes API**

The core of Kubernetes' control plane is the API server. The API server exposes an HTTP API that lets end users, different parts of your cluster, and external components communicate with one another.

The Kubernetes API lets you query and manipulate the state of API objects in Kubernetes (for example: Pods, Namespaces, ConfigMaps, and Events).

Most operations can be performed through the kubectl command-line interface or other command-line tools, such as kubeadm, which in turn use the API. However, you can also access the API directly using REST calls.

</details>

- [The Kubernetes API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/)
- [Kubernetes API server](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-apiserver/)

### 1.4 Containers

<p align="center">
  <img width="360" src="./pics/containervsvm.jpeg">
</p>


<details>
<summary>Containers - Click arrow to read more</summary>
<br>

Containers are a form of operating system virtualization. A single container might be used to run anything from a small microservice or software process to a larger application. Inside a container are all the necessary executables, binary code, libraries, and configuration files. Compared to server or machine virtualization approaches, however, containers do not contain operating system images. 

This makes them more lightweight and portable, with significantly less overhead. In larger application deployments, multiple containers may be deployed as one or more container clusters. Such clusters might be managed by a container orchestrator such as Kubernetes.

Reference : https://www.netapp.com/devops-solutions/what-are-containers/

</details>

- [What are Containers?](https://kubernetes.io/docs/concepts/containers/)
- [Containers](https://www.docker.com/resources/what-container)
- [Kubernetes for the Absolute Beginners - Hands-on by Mumshad](https://www.udemy.com/course/learn-kubernetes/)
- [What are Kubernetes Pods Anyway?](https://www.ianlewis.org/en/what-are-kubernetes-pods-anyway)
- [Containers for Beginners](https://k21academy.com/docker-kubernetes/what-are-containers/)
- [Kubernetes for Beginners](https://k21academy.com/docker-kubernetes/kubernetes-for-beginners/)
- [Docker Tutorial for Beginners](https://www.youtube.com/watch?v=fqMOX6JJhGo) (OPTIONAL)
- [Best practices for creating Dockerfiles](https://www.youtube.com/watch?v=JofsaZ3H1qM)
- [Containers vs VMS](https://www.youtube.com/watch?v=cjXI-yxqGTI)
- [Container Images](https://kubernetes.io/docs/concepts/containers/images/)
- [Kubernetes Tutorial for Beginners – Basic Concepts & Examples](https://spacelift.io/blog/kubernetes-tutorial)

### 1.5 Scheduling

- [The Kubernetes Scheduler](https://kubernetes.io/docs/concepts/scheduling-eviction/kube-scheduler/)
- [Assigning Pods to Nodes](https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/)
- [Scheduling framework](https://kubernetes.io/docs/concepts/scheduling-eviction/scheduling-framework/)
- [How the K8s scheduler works](https://www.youtube.com/watch?v=rDCWxkvPlAw)

## :small_blue_diamond: 2. Container Orchestration - 22%

### 2.1 Containers Orchestration Fundamentals

- [What is Kubernetes?](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)
- [Container Orchestration Explained](https://www.youtube.com/watch?v=kBF6Bvth0zw)
- [Containers vs. Pods - Taking a Deeper Look](https://iximiuz.com/en/posts/containers-vs-pods/)

### 2.2 Runtime

- [Container runtimes](https://kubernetes.io/docs/setup/production-environment/container-runtimes/)
- [Making Sense of the Container Runtime Landscape in Kubernetes](https://www.youtube.com/watch?v=RyXL1zOa8Bw)
- [Container Runtime Interface (CRI)](https://kubernetes.io/docs/concepts/architecture/cri/)
- [What are Runtime Classes?](https://kubernetes.io/docs/concepts/containers/runtime-class/)
- [Kubernetes is deprecating Docker as a container runtime after v1.20](https://kubernetes.io/blog/2020/12/02/dont-panic-kubernetes-and-docker/)
- [Kubernetes is deprecating Docker: what you need to know](https://acloudguru.com/blog/engineering/kubernetes-is-deprecating-docker-what-you-need-to-know)
- [Rancher Desktop – An Open Source App for Desktop Kubernetes and Container Management](https://www.suse.com/c/rancher_blog/rancher-desktop-an-open-source-app-for-desktop-kubernetes-and-container-management/)
- [Rancher Desktop GitHub](https://github.com/rancher-sandbox/rancher-desktop)
### 2.3 Security

- [The 4C's of Cloud Native Security](https://kubernetes.io/docs/concepts/security/overview/)

<p align="center">
  <img width="360" src="./pics/4c.jpeg">
</p>

- [Securing a cluster](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/)
- [Cloud native security guide for building secure applications](https://snyk.io/learn/cloud-native-security-for-cloud-native-applications/)
- [Kubernetes Security Best Practices: 10 Steps to Securing K8s](https://www.aquasec.com/cloud-native-academy/kubernetes-in-production/kubernetes-security-best-practices-10-steps-to-securing-k8s/)
- [Kubernetes Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Kubernetes_Security_Cheat_Sheet.html)
- [Kubernetes Security: Common Issues and Best Practices](https://snyk.io/learn/kubernetes-security/)
- [What is Kubernetes Container Security?](https://www.trendmicro.com/en_gb/what-is/container-security/kubernetes.html)
- [Kubernetes Security 101: Fundamentals and Best Practices](https://sysdig.com/learn-cloud-native/kubernetes-security/kubernetes-security-101/)
- [Understand Role Based Access Control (RBAC) in Kubernetes](https://www.youtube.com/watch?v=G3R24JSlGjY)
- [Controlling access to the K8s API](https://kubernetes.io/docs/concepts/security/controlling-access/)

### 2.4 Networking

- [Cluster networking in K8s](https://kubernetes.io/docs/concepts/cluster-administration/networking/)
- [Network Policies in K8s](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
- [Services, Load Balancing and Networking](https://kubernetes.io/docs/concepts/services-networking/)
- [Container Networking From Scratch](https://www.youtube.com/watch?v=6v_BDHIgOY8)
- [CNI - the Container Network Interface - GitHub](https://github.com/containernetworking/cni)
### 2.5 Service Mesh

<p align="center">
  <img width="360" src="./pics/Istio.png">
</p>

- [What's a service mesh? (REDHAT)](https://www.redhat.com/en/topics/microservices/what-is-a-service-mesh)
- [What Is a Service Mesh? (NGINX)](https://www.nginx.com/blog/what-is-a-service-mesh/)
- [The Istio service mesh](https://istio.io/latest/about/service-mesh/)
- [Istio & Service Mesh - simply explained in 15 mins](https://www.youtube.com/watch?v=16fgzklcF7Y)
- [Managing microservice with Istio service mesh](https://kubernetes.io/blog/2017/05/managing-microservices-with-istio-service-mesh/)
- [Istio Architecture](https://istio.io/v1.10/docs/ops/deployment/architecture/)

### 2.6 Storage

- [Storage in Kubernetes](https://kubernetes.io/docs/concepts/storage/)
- [What is Kubernetes Storage?](https://cloud.netapp.com/blog/cvo-blg-kubernetes-storage-an-in-depth-look)
- [Kubernetes Storage 101: Concepts and Best Practices](https://cloudian.com/guides/kubernetes-storage/kubernetes-storage-101-concepts-and-best-practices/)
- [Volumes in Kubernetes](https://kubernetes.io/docs/concepts/storage/volumes/)
- [Persistent Volumes aka PVs in K8s](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)
- [Why Is Storage On Kubernetes So Hard?](https://softwareengineeringdaily.com/2019/01/11/why-is-storage-on-kubernetes-is-so-hard/)
- [A complete storage guide for your Kubernetes storage problems by CNCF](https://www.cncf.io/blog/2020/04/28/a-complete-storage-guide-for-your-kubernetes-storage-problems/)
- [To run or not to run a database on Kubernetes: What to consider](https://cloud.google.com/blog/products/databases/to-run-or-not-to-run-a-database-on-kubernetes-what-to-consider)
- [Kubernetes And Databases](https://www.magalix.com/blog/kubernetes-and-database)
- [Container Storage Interface (CSI) for Kubernetes GA](https://kubernetes.io/blog/2019/01/15/container-storage-interface-ga/)

## :small_blue_diamond: 3. Cloud Native Architecture - 16%

<details>
<summary>Characteristics of Cloud Native Architecture - Click arrow to read more</summary>
<br>

- High level of Automation
- Self-healing
- Secure by default
- Cost-efficient
- Easy-to-maintain
- Scalable

</details>

<details>
<summary>Twelve-Factor App - Click arrow to read more</summary>
<br>


**The Twelve Factors**

- I. Codebase:
One codebase tracked in revision control, many deploys
- II. Dependencies:
Explicitly declare and isolate dependencies
- III. Config:
Store config in the environment
- IV. Backing services:
Treat backing services as attached resources
- V. Build, release, run:
Strictly separate build and run stages
- VI. Processes:
Execute the app as one or more stateless processes
- VII. Port binding:
Export services via port binding
- VIII. Concurrency:
Scale out via the process model
- IX. Disposability:
Maximize robustness with fast startup and graceful shutdown
- X. Dev/prod parity:
Keep development, staging, and production as similar as possible
- XI. Logs:
Treat logs as event streams
- XII. Admin processes:
Run admin/management tasks as one-off processes

Reference: https://12factor.net/

</details>

- [The Cloud Native Glossary](https://github.com/cncf/glossary/blob/main/cloudnative-glossary.pdf)
- [CNCF Cloud Native Interactive Landscape](https://landscape.cncf.io/)
- [The beginners guide to the CNCF landscape](https://www.cncf.io/blog/2018/11/05/beginners-guide-cncf-landscape/)
- [Graduated and incubaring projects in the CNCF eco-system](https://www.cncf.io/projects/)
- [Cloud Native Architecture Fundamentals](https://medium.com/walmartglobaltech/cloud-native-architecture-fundamentals-ac13f979916d)
- [The Twelve-Factor App](https://12factor.net/)
- [Architecting Kubernetes clusters — choosing the best autoscaling strategy](https://learnk8s.io/kubernetes-autoscaling-strategies)
- [Introduction to Monolithic Architecture and MicroServices Architecture](https://medium.com/koderlabs/introduction-to-monolithic-architecture-and-microservices-architecture-b211a5955c63)
- [Microservices Architecture](https://docs.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices)
- [Managing microservice with Istio service mesh](https://kubernetes.io/blog/2017/05/managing-microservices-with-istio-service-mesh/)
- [What is microservices architecture?](https://cloud.google.com/learn/what-is-microservices-architecture)
- [Microservices vs Monolithic Architecture](https://www.mulesoft.com/resources/api/microservices-vs-monolithic)

### 3.1 Autoscaling

- [Autoscaling in Kubernetes](https://kubernetes.io/blog/2016/07/autoscaling-in-kubernetes/)
- [Horizontal Pod Autoscaling (HPA in K8s)](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/)
- [Kubernetes Autoscaling: 3 Methods and How to Make Them Great](https://spot.io/resources/kubernetes-autoscaling-3-methods-and-how-to-make-them-great/)
- [Kubernetes Autoscaling in Production: Best Practices for Cluster Autoscaler, HPA and VPA](https://www.replex.io/blog/kubernetes-in-production-best-practices-for-cluster-autoscaler-hpa-and-vpa)
- [Horizontal Pod autoscaling in GKE (GCP)](https://cloud.google.com/kubernetes-engine/docs/concepts/horizontalpodautoscaler)

### 3.2 Serverless

- [Microservices vs. Serverless Architecture](https://www.sumologic.com/blog/microservices-vs-serverless-architecture/)
- [Serverless Functions as a Service for Kubernetes](https://kubernetes.io/blog/2017/01/fission-serverless-functions-as-service-for-kubernetes/)
- [Serverless containers on K8s](https://knative.dev/docs/)
- [Knative GitHub](https://github.com/knative)

### 3.3 Community & Governance

- [Community & Governance in K8s (K8s GitHub)](https://github.com/kubernetes/community/blob/master/governance.md)
- [The Kubernetes Community](https://kubernetes.io/community/)
- [The Official Kuberenetes GitHub](https://github.com/kubernetes/kubernetes)
- [Kubernetes governance, what you should know](https://www.cncf.io/blog/2020/05/29/kubernetes-governance-what-you-should-know/)
- [Kubernetes Community Values](https://kubernetes.io/community/values/)
- [Kubernetes 1.21: Power to the Community](https://kubernetes.io/blog/2021/04/08/kubernetes-1-21-release-announcement/)
- [Kubernetes in Production: Best Practices for Governance, Cost Management, Security and Access Control](https://www.replex.io/blog/kubernetes-in-production-best-practices-for-governance-cost-management-and-security-and-access-control)

### 3.4 Roles & Personas

- [Personas](https://cluster-api.sigs.k8s.io/user/personas.html)
- [[Podcast] PodCTL #28 - Kubernetes Roles & Personas](https://cloud.redhat.com/blog/podcast-podctl-28-kubernetes-roles-personas)
- [Personas and use cases](https://www.ibm.com/docs/en/cloud-paks/cp-management/1.3.0?topic=about-personas-use-cases)
- [PodCTL - Enterprise Kubernetes - podcast focused on Roles and Personas of K8s environments](https://podctl.buzzsprout.com/110399/653300-kubernetes-roles-personas)

### 3.5 Open Standards

- [Navigating open standards for Kubernetes](https://www.information-age.com/navigating-open-standards-for-kubernetes-123492463/)
- [Open standards can make or break a Kubernetes implementation](https://morioh.com/p/02a05107d000)
- [Three tips to implement Kubernetes with open standards](https://techtelegraph.co.uk/three-tips-to-implement-kubernetes-with-open-standards/)
- [Open Container Initiative](https://opencontainers.org/)
- [CNI - the Container Network Interface](https://github.com/containernetworking/cni)
- [Container Runtime Interface (CRI) – a plugin interface which enables kubelet to use a wide variety of container runtimes - GitHub](https://github.com/kubernetes/cri-api)
 - [Container Storage Interface (CSI) Specification - GitHub](https://github.com/container-storage-interface/spec)
 - [A standard interface for service meshes on Kubernetes](https://smi-spec.io/)

## :small_blue_diamond: 4. Cloud Native Observability - 8%

### 4.1 Telemetry & Observability

- [The Cloud Native Landscape: Observability & Analysis](https://thenewstack.io/the-cloud-native-landscape-observability-and-analysis/)
- [What is Telemetry? The Guide to Application Monitoring](https://www.sumologic.com/insight/what-is-telemetry/)
- [Tools for Monitoring Resources](https://kubernetes.io/docs/tasks/debug-application-cluster/resource-usage-monitoring/)
- [What is OpenTelemetry and why is it the future of instrumentation?](https://www.cncf.io/blog/2021/08/06/what-is-opentelemetry-and-why-is-it-the-future-of-instrumentation/)
- [Migrating telemetry and security agents from dockershim](https://kubernetes.io/docs/tasks/administer-cluster/migrating-from-dockershim/migrating-telemetry-and-security-agents/)
- [Getting started with OpenTelemetry on Kubernetes](https://signoz.io/blog/opentelemetry-kubernetes/)
- [CNCF Advances OpenTelemetry Initiative](https://devops.com/cncf-advances-opentelemetry-initiative/)
- [Splunk Donates eBPF Telemetry Data Collector to CNCF](https://devops.com/splunk-donates-ebpf-telemetry-data-collector-to-cncf/)
- [Use the native logging mechanisms of containers](https://cloud.google.com/architecture/best-practices-for-operating-containers#use_the_native_logging_mechanisms_of_containers)

### 4.2 Prometheus

- [What is Prometheus?](https://prometheus.io/docs/introduction/overview/)
- [An introduction to monitoring with Prometheus](https://opensource.com/article/19/11/introduction-monitoring-prometheus)
- [How Prometheus Monitoring works | Prometheus Architecture explained by Nana Janashia](https://www.youtube.com/watch?v=h4Sl21AKiDg)
- [What is Prometheus and Why Should You Use It?](https://opsani.com/resources/what-is-prometheus-and-why-should-you-use-it/)
- [Metrics For Kubernetes System Components](https://kubernetes.io/docs/concepts/cluster-administration/system-metrics/)
- [Query Examples from Prometheus](https://prometheus.io/docs/prometheus/latest/querying/examples/)
- [Prometheus Cheat Sheet - Basics (Metrics, Labels, Time Series, Scraping)](https://iximiuz.com/en/posts/prometheus-metrics-labels-time-series/)
- [Jaeger: open source, end-to-end distributed tracing](https://www.jaegertracing.io/)

### 4.3 Cost Management

- [Cost management for Kubernetes](https://www.redhat.com/en/technologies/cloud-computing/openshift/cost-management)
- [Kubernetes Cost Analysis: Manage Your Kubernetes Costs](https://harness.io/blog/kubernetes-cost-analysis/)
- [Kubernetes Cost Management and Analysis Guide](https://dev.to/cloudforecast/kubernetes-cost-management-and-analysis-guide-1e1b)
- [Cloud cost optimization: principles for lasting success](https://cloud.google.com/blog/topics/cost-management/principles-of-cloud-cost-optimization)

## :small_blue_diamond: 5. Cloud Native Application Delivery - 8%

### 5.1 Application Delivery Fundamentals

- [Continuous delivery at cloud native speed](https://www.weave.works/use-cases/application-delivery/)
- [What is Helm](https://helm.sh/)
- [What is CI/CD? by RedHat](https://www.redhat.com/en/topics/devops/what-is-ci-cd)
- [What is Infrastructure as Code (IaC)?](https://www.redhat.com/en/topics/automation/what-is-infrastructure-as-code-iac)

### 5.2 GitOps

- [What is GitOps?](https://www.redhat.com/en/topics/devops/what-is-gitops)
- [ArgoCD Kubernetes - YouTube playlist by Just me and Opensource](https://www.youtube.com/playlist?list=PL34sAs7_26wMW4bWKnMIfEd87aPuw75by)
- [ArgoCon 2021 - YouTube playlist](https://www.youtube.com/playlist?list=PLGHfqDpnXFXKwNGO_8usFuTO-rIHNyefC)
- [Guide to GitOps by Weave works](https://www.weave.works/technologies/gitops/)
- [GitOps on Kubernetes: Deciding Between Argo CD and Flux](https://thenewstack.io/gitops-on-kubernetes-deciding-between-argo-cd-and-flux/)
- [Argo CD vs Flux CD — Right GitOps tool for your Kubernetes cluster](https://rajputvaibhav.medium.com/argo-cd-vs-flux-cd-right-gitops-tool-for-your-kubernetes-cluster-c71cff489d26)
- [FluxCD, ArgoCD or Jenkins X: Which Is the Right GitOps Tool for You?](https://blog.container-solutions.com/fluxcd-argocd-jenkins-x-gitops-tools)
- [GitOps tools in comparison by cloudogu](https://cloudogu.com/en/blog/gitops-tools)
- [Flux vs ArgoCD](https://www.sgmoratilla.com/2021-10-28-flux-vs-argocd/)
- [Why is a PULL vs a PUSH pipeline important?](https://www.weave.works/blog/why-is-a-pull-vs-a-push-pipeline-important)
- [Push vs. Pull in GitOps: Is There Really a Difference?](https://thenewstack.io/push-vs-pull-in-gitops-is-there-really-a-difference/)
- [ArgoCD Architecture](https://argo-cd.readthedocs.io/en/stable/operator-manual/architecture/)

### 5.3 CI/CD

- [Kubernetes CICD - CI/CD for Kubernetes | Weaveworks](https://www.weave.works/technologies/ci-cd-for-kubernetes/)
- [Kubernetes for CI/CD at scale](https://platform9.com/blog/kubernetes-for-ci-cd-at-scale/)
- [Kubernetes CI/CD pipelines: What, why, and how](https://ubuntu.com/blog/kubernetes-ci-cd-pipelines-what-why-and-how)
- [Top Open Source CI/CD Tools for Kubernetes to Know](https://cloud.redhat.com/blog/top-open-source-ci/cd-tools-for-kubernetes-to-know)
- [Kubernetes CI/CD Best Practices](https://harness.io/blog/kubernetes-ci-cd-best-practices/)
- [CI/CD Pipelines with Kubernetes | Best Practices and Tools](https://www.containiq.com/post/cicd-pipelines-with-kubernetes)

# [Test your knowledge - Click this for practice questions](./mock-exam-questions/questions.md)

## Slack

1. [Kubernetes Community - #kcna-exam-prep](https://kubernetes.slack.com)
2. [Kubernetes Community](https://kubernauts-slack-join.herokuapp.com/)
3. [Cloud Native Mentoring - #kcna](https://join.slack.com/t/cloudnative-mentoring/shared_invite/zt-119bf6kae-bSGp7NQYrG~FZmjZjhZ~QA)

## Useful training material

- [Kubernetes and Cloud Native Essentials by The Linux Foundation](https://training.linuxfoundation.org/training/kubernetes-and-cloud-native-essentials-lfs250/)
- [Kubernetes and Cloud Native Associate (KCNA) Practice Exams on Udemy by Andrew Brown](https://www.udemy.com/course/kubernetes-and-cloud-native-associate-kcna/)
- [Introduction to GitOps by The Linux Foundation](https://training.linuxfoundation.org/training/introduction-to-gitops-lfs169/)
- [Introduction to DevOps & Site Reliability Engineering by The Linux Foundation](https://training.linuxfoundation.org/training/introduction-to-devops-and-site-reliability-engineering-lfs162/)
- [Oh My Git! An open source game about learning Git!](https://ohmygit.org/)
- [Learn Git Branching](https://learngitbranching.js.org/)

## Useful reading material

- [Delivering Cloud Native Infrastructure as Code by Pulumi](https://www.pulumi.com/why-pulumi/delivering-cloud-native-infrastructure-as-code/)
- [Unlocking the Cloud Operating Model: Provisioning](https://www.hashicorp.com/resources/unlocking-the-cloud-operating-model-provisioning)
- [GitLab’s guide to CI/CD for beginners](https://about.gitlab.com/blog/2020/07/06/beginner-guide-ci-cd/)
- [How to Pass your KCNA Exam by Brad McCoy](https://blog.bradmccoy.io/how-to-pass-your-kcna-exam-cf98cfa7d70f)
- [The KCNA Exam — A quick guide to kicking off your K8S and Cloud Native Journey by Marino Wijay](https://medium.com/@marino.wijay/the-kcna-exam-a-quick-guide-to-kicking-off-your-k8s-and-cloud-native-journey-56a3a5be345)
## Books

- [Kubernetes: Up and Running by O’Reilly](https://learning.oreilly.com/library/view/kubernetes-up-and/9781491935668/)
- [7 Best Books to Get You Started with Kubernetes](https://blog.turbonomic.com/top-kubernetes-book)

## References

- [The Official Kubernetes Documentation](https://k8s.io/docs)

## Useful Youtube vdeos

- [Kubernetes and Cloud Native Associate (KCNA) exam - Katie Gamanji, CNCF](https://www.youtube.com/watch?v=TtUMT5cnVO4)
- [KCNA breakdown by Saiyam Pathak](https://www.youtube.com/watch?v=iGkFHB1kFZ0)
- [Open Source Values & Advocacy & Deep Dive KCNA Exam | CLOUDNATIVE.FM Ep 31](https://www.youtube.com/watch?v=wPbsvF_SGmc)
- [KCNA Deep Dive by Katie Gamanji - The CLOUDNATIVEFM With SAIM ](https://www.youtube.com/watch?v=wPbsvF_SGmc)
- [KCNA Prep - Kubernetes Fundamentals Part 1 ](https://www.youtube.com/watch?v=wnkium96ZVk)
- [KCNA Prep - Kubernetes Fundamentals Part 2 ](https://www.youtube.com/watch?v=ZwCpgLeyKKo)


## Useful Kubernetes repos + Next steps?

- [Kubernetes Certified Administrator by Walid Shaari](https://github.com/walidshaari/Kubernetes-Certified-Administrator)
- [CKA Exercises](https://github.com/moabukar/CKA-Exercises)
- [CKAD Exercises](https://github.com/dgkanatsios/CKAD-exercises)
- [CKS repo by Walid Shaari](https://github.com/walidshaari/Certified-Kubernetes-Security-Specialist)
- [CKS-Exercises](https://github.com/moabukar/CKS-Exercises-Certified-Kubernetes-Security-Specialist)
