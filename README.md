[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

# Kubernetes-and-Cloud-Native-Associate (KCNA)

<p align="center">
  <img width="360" src="KCNA-logo.jpeg">
</p>

- Note: A documentation of notes & useful used to prepare for the KCNA. Feel free to share them :)

## Exam Brief

- Duration : 1.5 hours
<!-- Number of questions : ??? Multiple choice questions -->
- Passing score: 67%
- Certification validity: 3 years
- Prerequisite: None
- Cost: $250 USD, 1 year exam eligibility, with a free retake within the year.
- [Official KCNA curriculum](https://github.com/cncf/curriculum/blob/master/KCNA_Curriculum.pdf)

  *Linux Foundation offer several discounts around the year such as CyberMonday, Kubecon and various other events - ensure to utilise these*

## KCNA topics overview

- [X] [Kubernetes Fundamentals - 46%](#kubernetes-fundamentals---46)
- [X] [Container Orchestration - 22%](#containerr-orchestration---22)
- [X] [Cloud Native Architecture - 16%](#cloud-native-architecture---16)
- [X] [Cloud Native Observability - 8%](#cloud-native-observability---8)
- [X] [Cloud Native Application Delivery - 8%](#cloud-native-application-delivery---8)

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

## :small_blue_diamond: Kubernetes Fundamentals - 46%
### Fundamental Kuberenetes resources

- [Pods in Kubernetes](https://kubernetes.io/docs/concepts/workloads/pods/)
- [Deployments in Kubernetes](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
- [Services in Kubernetes](https://kubernetes.io/docs/concepts/services-networking/service/)
- [ReplicaSets in Kubernetes](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/)

### Kubernetes Architecture

- [Kubernetes Componenent](https://kubernetes.io/docs/concepts/overview/components/)
- [Nodes in K8s](https://kubernetes.io/docs/concepts/architecture/nodes/)
- [Control Plane-Node Communication](https://kubernetes.io/docs/concepts/architecture/control-plane-node-communication/)
- 

### Kubernetes API

- [The Kubernetes API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/)
- [Kubernetes API server](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-apiserver/)

### Containers

- [What are Containers?](https://kubernetes.io/docs/concepts/containers/)
- [Containers](https://www.docker.com/resources/what-container)
- [Docker Tutorial for Beginners](https://www.youtube.com/watch?v=fqMOX6JJhGo) (OPTIONAL)
- [Best practices for creating Dockerfiles](https://www.youtube.com/watch?v=JofsaZ3H1qM)
- [Containers vs VMS](https://www.youtube.com/watch?v=cjXI-yxqGTI)
- [Container Images](https://kubernetes.io/docs/concepts/containers/images/)

### Scheduling

- [The Kubernetes Scheduler](https://kubernetes.io/docs/concepts/scheduling-eviction/kube-scheduler/)
- [Assigning Pods to Nodes](https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/)
- [Scheduling framework](https://kubernetes.io/docs/concepts/scheduling-eviction/scheduling-framework/)
- [How the K8s scheduler works](https://www.youtube.com/watch?v=rDCWxkvPlAw)

## :small_blue_diamond: Container Orchestration - 22%

### Containers Orchestration Fundamentals

- [What is Kubernetes?](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)
- [Container Orchestration Explained](https://www.youtube.com/watch?v=kBF6Bvth0zw)

### Runtime

- [Container runtimes](https://kubernetes.io/docs/setup/production-environment/container-runtimes/)
- [Container Runtime Interface (CRI)](https://kubernetes.io/docs/concepts/architecture/cri/)
- [What are Runtime Classes?](https://kubernetes.io/docs/concepts/containers/runtime-class/)
- [Kubernetes is deprecating Docker as a container runtime after v1.20](https://kubernetes.io/blog/2020/12/02/dont-panic-kubernetes-and-docker/)
- [Kubernetes is deprecating Docker: what you need to know](https://acloudguru.com/blog/engineering/kubernetes-is-deprecating-docker-what-you-need-to-know)
- []()

### Security

- [The 4C's of Cloud Native Security](https://kubernetes.io/docs/concepts/security/overview/)
- [Securing a cluster](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/)
- [Cloud native security guide for building secure applications](https://snyk.io/learn/cloud-native-security-for-cloud-native-applications/)
- [Kubernetes Security Best Practices: 10 Steps to Securing K8s](https://www.aquasec.com/cloud-native-academy/kubernetes-in-production/kubernetes-security-best-practices-10-steps-to-securing-k8s/)
- [Kubernetes Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Kubernetes_Security_Cheat_Sheet.html)
- [Kubernetes Security: Common Issues and Best Practices](https://snyk.io/learn/kubernetes-security/)
- [What is Kubernetes Container Security?](https://www.trendmicro.com/en_gb/what-is/container-security/kubernetes.html)
- [Kubernetes Security 101: Fundamentals and Best Practices](https://sysdig.com/learn-cloud-native/kubernetes-security/kubernetes-security-101/)
- [Understand Role Based Access Control (RBAC) in Kubernetes](https://www.youtube.com/watch?v=G3R24JSlGjY)
- [Controlling access to the K8s API](https://kubernetes.io/docs/concepts/security/controlling-access/)

### Networking

- [Cluster networking in K8s](https://kubernetes.io/docs/concepts/cluster-administration/networking/)
- [Network Policies in K8s](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
- [Services, Load Balancing and Networking](https://kubernetes.io/docs/concepts/services-networking/)
- [Container Networking From Scratch](https://www.youtube.com/watch?v=6v_BDHIgOY8)

### Service Mesh

- [What's a service mesh? (REDHAT)](https://www.redhat.com/en/topics/microservices/what-is-a-service-mesh)
- [What Is a Service Mesh? (NGINX)](https://www.nginx.com/blog/what-is-a-service-mesh/)
- [The Istio service mesh](https://istio.io/latest/about/service-mesh/)
- [Istio & Service Mesh - simply explained in 15 mins](https://www.youtube.com/watch?v=16fgzklcF7Y)
- [Managing microservice with Istio service mesh](https://kubernetes.io/blog/2017/05/managing-microservices-with-istio-service-mesh/)


### Storage

- [Storage in Kubernetes](https://kubernetes.io/docs/concepts/storage/)
- [What is Kubernetes Storage?](https://cloud.netapp.com/blog/cvo-blg-kubernetes-storage-an-in-depth-look)
- [Kubernetes Storage 101: Concepts and Best Practices](https://cloudian.com/guides/kubernetes-storage/kubernetes-storage-101-concepts-and-best-practices/)
- [Volumes in Kubernetes](https://kubernetes.io/docs/concepts/storage/volumes/)
- [Persistent Volumes aka PVs in K8s](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)
- [Why Is Storage On Kubernetes So Hard?](https://softwareengineeringdaily.com/2019/01/11/why-is-storage-on-kubernetes-is-so-hard/)
- [A complete storage guide for your Kubernetes storage problems by CNCF](https://www.cncf.io/blog/2020/04/28/a-complete-storage-guide-for-your-kubernetes-storage-problems/)
- [To run or not to run a database on Kubernetes: What to consider](https://cloud.google.com/blog/products/databases/to-run-or-not-to-run-a-database-on-kubernetes-what-to-consider)
- [Kubernetes And Databases](https://www.magalix.com/blog/kubernetes-and-database)

## :small_blue_diamond: Cloud Native Architecture - 16%

- [The Cloud Native Glossary](https://github.com/cncf/glossary/blob/main/cloudnative-glossary.pdf)
- [CNCF Cloud Native Interactive Landscape](https://landscape.cncf.io/)
- [The beginners guide to the CNCF landscape](https://www.cncf.io/blog/2018/11/05/beginners-guide-cncf-landscape/)
- [Graduated and incubaring projects in the CNCF eco-system](https://www.cncf.io/projects/)
- [Cloud Native Architecture Fundamentals](https://medium.com/walmartglobaltech/cloud-native-architecture-fundamentals-ac13f979916d)
- [Introduction to Monolithic Architecture and MicroServices Architecture](https://medium.com/koderlabs/introduction-to-monolithic-architecture-and-microservices-architecture-b211a5955c63)
- [Microservices Architecture](https://docs.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices)
- [Managing microservice with Istio service mesh](https://kubernetes.io/blog/2017/05/managing-microservices-with-istio-service-mesh/)
- [What is microservices architecture?](https://cloud.google.com/learn/what-is-microservices-architecture)
- [Microservices vs Monolithic Architecture](https://www.mulesoft.com/resources/api/microservices-vs-monolithic)

### Autoscaling

- [Resource 1]()

### Serverless

- [Microservices vs. Serverless Architecture](https://www.sumologic.com/blog/microservices-vs-serverless-architecture/)
- [Serverless Functions as a Service for Kubernetes](https://kubernetes.io/blog/2017/01/fission-serverless-functions-as-service-for-kubernetes/)
- [Serverless containers on K8s](https://knative.dev/docs/)
- [Knative GitHub](https://github.com/knative)


### Community & Governance

- [Resource 1]()

### Roles & Personas

- [Resource 1]()

### Open Standards

- [Resource 1]()

## :small_blue_diamond: Cloud Native Observability - 8%

### Telemetry & Observability

- [Resource 1]()

### Prometheus

- [Resource 1]()


### Cost Management

- [Resource 1]()
## :small_blue_diamond: Cloud Native Application Delivery - 8%

### Application Delivery Fundamentals

- [Resource 1]()

### GitOps

- [Resource 1]()

### CI/CD

- [Resource 1]()

## Slack

1. [Kubernetes Community - #kcna-exam-prep](https://kubernetes.slack.com)
1. [Kubernetes Community](https://kubernauts-slack-join.herokuapp.com/)

## Books

## Useful Youtube vdeos

## Other KCNA related repos
