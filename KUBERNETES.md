# Kubernetes

[Kubernetes](https://kubernetes.io) is an open-source container orchestration platform designed to automate the deployment, scaling, and management of containerized applications. It provides a robust and scalable solution for managing applications in a microservices architecture, helping users manage complex applications across clusters of machines. Kubernetes handles tasks such as load balancing, service discovery, automated rollouts, self-healing (e.g., restarting failed containers), and scaling based on demand. With its declarative configuration model, Kubernetes ensures that the desired state of the system is maintained. It is widely used in both cloud and on-premises environments for building cloud-native applications and is supported by a large ecosystem of tools and services.

## Kubernetes Distributions

Kubernetes distributions are pre-packaged versions of Kubernetes that include additional features, configurations, and management tools tailored to specific use cases or environments. These distributions simplify the setup, operation, and maintenance of Kubernetes clusters.

Each distribution may include distinctive features, such as advanced security, custom networking, or streamlined management, to meet specific deployment requirements.

### ⭐ kubeadm

[Kubeadm](https://kubernetes.io/docs/reference/setup-tools/kubeadm/) is an official Kubernetes tool that simplifies the process of setting up a basic, production-ready Kubernetes cluster. It initializes the control plane and adds worker nodes to the cluster with minimal manual configuration. Kubeadm provides a streamlined and standardized way to bootstrap Kubernetes, making it ideal for users who want a quick and reliable setup without relying on complex installation scripts.

### ⭐ k3s

[K3s](https://k3s.io) is a lightweight, certified Kubernetes distribution designed for resource-constrained environments, edge computing, and IoT devices. It simplifies Kubernetes installation and management by bundling essential components and using minimal system requirements. K3s is easy to deploy, fully compliant with Kubernetes standards, and supports cloud-native development, making it ideal for use cases like small-scale clusters, development setups, and remote deployments.

* [k3sup](https://github.com/alexellis/k3sup)
* [k3d](https://k3d.io/stable/)

### k0s

[K0s](https://k0sproject.io) is a lightweight, all-in-one Kubernetes distribution designed to simplify cluster management. It is open-source, easy to install, and provides a single binary that includes all components needed for a Kubernetes cluster. K0s is well-suited for use in edge computing, development environments, and production setups, offering a minimalistic and efficient approach to Kubernetes deployment.

### microk8s

[MicroK8s](https://microk8s.io/docs) is a lightweight, single-package Kubernetes distribution designed for simplicity and fast deployment. It is ideal for development, testing, and small-scale production environments. MicroK8s comes with built-in addons for features like DNS, storage, and monitoring, which can be enabled or disabled as needed. Its minimal resource footprint and streamlined setup make it well-suited for local environments and edge computing scenarios.

### ⭐ kind

[Kubernetes Kind (Kubernetes IN Docker)](https://kind.sigs.k8s.io) is a tool designed for running local Kubernetes clusters using Docker containers as nodes. It is ideal for testing and development, allowing users to quickly create Kubernetes clusters without requiring complex setups or additional hardware. Kind supports multi-node clusters, making it useful for simulating production-like environments in a lightweight and portable way.

### rke2

[RKE2](https://docs.rke2.io (Rancher Kubernetes Engine 2)) is a secure, lightweight Kubernetes distribution designed for modern infrastructure, including edge, IoT, and production environments. It is a certified Kubernetes distribution that integrates additional security features such as SELinux and advanced auditing by default. RKE2 simplifies Kubernetes installation and management while maintaining full compatibility with upstream Kubernetes, making it ideal for both resource-constrained and large-scale deployments.

### ⭐ Minikube

[Minikube](https://minikube.sigs.k8s.io/docs/) is a lightweight tool for running a local Kubernetes cluster on your personal computer. It is designed for developers and learners to quickly test and experiment with Kubernetes in a single-node setup. Minikube supports various hypervisors and container runtimes, providing an easy way to explore Kubernetes features and workflows without needing a full production environment.

### Kubespray

[Kubespray](https://github.com/kubernetes-sigs/kubespray) is an open-source tool for deploying and managing production-ready Kubernetes clusters. It uses Ansible playbooks to automate the setup, configuration, and scaling of clusters across various environments, including bare-metal and cloud platforms. Kubespray supports multi-node clusters, high availability, and advanced networking features, making it ideal for users who need a customizable and flexible way to deploy Kubernetes.

### kOps

[Kops (Kubernetes Operations)](https://kops.sigs.k8s.io) is an open-source tool for creating, managing, and maintaining highly-available Kubernetes clusters in cloud environments, especially on AWS. It automates cluster provisioning, upgrades, and scaling, while supporting advanced features like multi-zone deployments and custom configurations. Kops is ideal for production-grade Kubernetes deployments, offering ease of use and strong integration with cloud-native infrastructures.

### Gardener

[Gardener](https://gardener.cloud) is an open-source Kubernetes management tool developed by SAP that automates the provisioning and operation of Kubernetes clusters across multiple environments. It uses Kubernetes itself to manage Kubernetes clusters ("Kubernetes as a Service"), providing consistent cluster management, monitoring, and maintenance. Gardener supports hybrid, multi-cloud, and edge scenarios, enabling efficient, large-scale deployments while maintaining flexibility and standardization.

### OpenShift

[OpenShift](https://github.com/openshift) is an open-source container application platform built around Kubernetes, developed by Red Hat. It provides tools and services for automating application deployment, scaling, and operations across various environments, whether on-premises or in the cloud. OpenShift extends Kubernetes by adding developer-friendly features like integrated CI/CD pipelines, a robust web console, and enhanced security controls. With support for multi-tenant environments, OpenShift simplifies the management of containerized applications, making it a popular choice for enterprise-level deployments.

### Rancher

[Rancher](https://www.rancher.com) is an open-source platform for managing and deploying Kubernetes clusters across various environments, whether on-premises, in the cloud, or at the edge. It provides a unified management layer for Kubernetes, allowing users to easily create, manage, and scale multiple clusters. Rancher simplifies tasks like multi-cluster orchestration, security management, and monitoring, offering a user-friendly interface and robust support for multi-cloud and hybrid cloud environments. It is particularly beneficial for teams looking to manage complex Kubernetes landscapes and enhance operational efficiency.

### KubeMatic

[KubeMatic](https://github.com/kubermatic/kubermatic) is an open-source Kubernetes management platform designed to simplify the deployment, operation, and maintenance of Kubernetes clusters. It provides a centralized interface for managing multiple Kubernetes clusters across different environments, both on-premises and in the cloud. KubeMatic automates tasks like cluster lifecycle management, monitoring, security, and scaling. Its flexible architecture supports multi-cloud and hybrid-cloud scenarios, making it ideal for organizations looking to manage large-scale Kubernetes deployments while maintaining control and consistency across various infrastructure setups.

### Giantswarm

[Giantswarm](https://www.giantswarm.io) is a managed Kubernetes service that simplifies the deployment and management of Kubernetes clusters at scale, offering solutions for both small teams and large enterprises. It provides a high-availability, multi-tenant Kubernetes platform for cloud-native applications. Giantswarm handles the operational complexity of running Kubernetes clusters, including updates, scaling, and security management, allowing teams to focus on developing and deploying their applications. With its platform, users can manage Kubernetes clusters across multiple cloud providers, ensuring consistency, reliability, and ease of use.

### Talos

[Talos](https://www.talos.dev) is a minimalist, secure, and Kubernetes-focused operating system designed specifically for running Kubernetes clusters. Unlike traditional operating systems, Talos is built from the ground up to run as an immutable, API-driven, and container-based platform, making it ideal for managing cloud-native environments. Talos eliminates the complexity of managing a traditional OS, offering seamless updates, improved security, and simplified cluster management. It’s designed for high-performance, scalable environments and supports both on-premises and cloud deployments, making it a great choice for users looking to optimize Kubernetes cluster operations.

### vCluster

[vCluster](https://www.vcluster.com) is a lightweight, virtualized Kubernetes cluster solution that allows users to create Kubernetes clusters within existing clusters, also known as "virtual clusters." Each vCluster runs as a namespace in a host Kubernetes cluster, providing the isolation and flexibility of individual clusters while leveraging the resources and management capabilities of the parent cluster. vCluster simplifies multi-tenant environments, reduces the overhead of managing multiple clusters, and improves developer workflows by providing quick, resource-efficient environments for testing, development, or deployment, all while maintaining control over the infrastructure.

### Cluster API

[Cluster API (CAPI)](https://github.com/kubernetes-sigs/cluster-api) is an open-source project that provides a declarative API for managing Kubernetes clusters. It standardizes the process of creating, scaling, upgrading, and managing Kubernetes clusters across multiple infrastructure providers, both on-premises and in the cloud. Cluster API enables users to automate cluster lifecycle management with the same principles and tools used for managing Kubernetes workloads. By leveraging the power of Kubernetes itself, CAPI integrates with existing Kubernetes-based ecosystems to streamline operations and ensure scalability, flexibility, and consistency across different cloud environments.

## Kubernetes Cloud Services

* [Alibaba Container Service for Kubernetes - ACK](https://www.alibabacloud.com/en/product/kubernetes)
* [Amazon Elastic Kubernetes Service- EKS](https://aws.amazon.com/eks/)
* [Digital Ocean Kubernetes Service- DOKS](https://www.digitalocean.com/products/kubernetes)
* [Fly Kubernetes Service - FKS](https://fly.io/docs/kubernetes/)]
* [Google Kubernetes Engine - GKE](https://cloud.google.com/kubernetes-engine)
* [IBM Cloud Kubernetes Service - ICKS ](https://www.ibm.com/products/kubernetes-service)
* [Microsoft Azure Kubernetes Service - AKS](https://azure.microsoft.com/en-us/products/kubernetes-service)
* [Oracle Kuberntes Engine - OKE](https://www.oracle.com/cloud/cloud-native/kubernetes-engine/)
* [Scaleway - kapsule/](https://www.scaleway.com/en/kubernetes-kapsule/)
* [Stackit Kubernetes Engine - SKE ](https://www.stackit.de/en/product/kubernetes/)
* [Syseleven - Metakube](https://www.syseleven.de/produkte-services/kubernetes/)
* [Telekom Cloud Container Engine - CCE](https://www.open-telekom-cloud.com/de/produkte-services/core-services/cloud-container-engine)
