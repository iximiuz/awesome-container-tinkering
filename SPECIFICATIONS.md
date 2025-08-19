# Container Standards and Specifications

## Open Container Initiative

The [Open Container Initiative](https://opencontainers.org) is an open governance structure for the express purpose of creating open industry standards around container formats and runtimes.

### OCI Runtime Specification

"The <a href="https://github.com/opencontainers/runtime-spec">OCI Runtime Specification</a> aims to specify the configuration, execution environment, and lifecycle of a container."

### OCI Image Format Specification

"The <a href="https://github.com/opencontainers/image-spec">OCI Image Format Specification</a> defines an OCI Image, consisting of an image manifest, an image index (optional), a set of filesystem layers, and a configuration."

### OCI Distribution Specification

"The <a href="https://github.com/opencontainers/distribution-spec">OCI Distribution Specification</a> defines an API protocol to facilitate and standardize the distribution of content."

### OCI Artifacts

<a href="https://github.com/opencontainers/artifacts">OCI Artifacts</a> - store arbitrary stuff (Helm charts, OPA policies, etc) in OCI registries leveraging the `media-type` file of the image manifest.

## Kubernetes Container Standards

Kubernetes defines several container standards to ensure consistent interaction between the system and container runtimes, storage solutions, and networking components. These standards provide a common interface for Kubernetes to work with various underlying technologies.

### Container Runtime Interface - CRI

The CRI is a Kubernetes standard that defines how Kubernetes interacts with container runtimes (like Docker, containerd, and others). It abstracts the specifics of different container runtimes, allowing Kubernetes to run containers without being tied to any one runtime. The CRI provides the API specifications for managing container lifecycle tasks such as creating, starting, and stopping containers.

* [CRI Definition](https://kubernetes.io/docs/concepts/architecture/cri/)
* [CRI API](https://github.com/kubernetes/cri-api/blob/c75ef5b/pkg/apis/runtime/v1/api.proto)
* Drivers:
  * [Containerd](https://containerd.io)
  * [CRI-O](https://cri-o.io)
  * [CRI dockerd](https://github.com/Mirantis/cri-dockerd)

### Container Network Interface - CNI

The CNI standard focuses on providing network connectivity for containers in Kubernetes environments. It defines how network plugins integrate with the Kubernetes system to allocate IP addresses, configure networking, and ensure secure communication between containers and services across clusters.

* [CNI Spec](https://www.cni.dev)
* [CNI Project](https://github.com/containernetworking/cni)

Network Implementations:

* [Flannel](https://github.com/flannel-io/cni-plugin)
* [Calico](https://docs.tigera.io/calico/latest/about/)
* [Cilium](https://cilium.io)
* [Kindnet](https://github.com/aojea/kindnet
  * [Tutorial Kindnet](https://www.tkng.io/cni/kindnet/)
* [Kube-OVN](https://github.com/kubeovn/kube-ovn/)
* [Multus](https://github.com/k8snetworkplumbingwg/multus-cni)

Loadbalaner:

* [Kube VIP](https://kube-vip.io)
* [MetalLB](https://metallb.io)
* [Loxi](https://www.loxilb.io)
* [Kube Proxy](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-proxy/)

### Container Storage Interface - CSI

The CSI standard provides a unified way to expose storage systems to Kubernetes workloads. It enables Kubernetes to support a wide variety of storage backends (such as block and file storage) without requiring integration directly into the Kubernetes codebase. CSI defines the interaction between Kubernetes and storage providers, making it easier to manage persistent volumes (PVs) in Kubernetes clusters.

* [CSI GA Release](https://kubernetes.io/blog/2019/01/15/container-storage-interface-ga/)
* [CSI Spec](https://github.com/container-storage-interface/spec/blob/master/spec.md)
* [CSI Drivers](https://kubernetes-csi.github.io/docs/drivers.html)

### Container Device Interface - CDI

The [Container Device Interface (CDI)](https://github.com/cncf-tags/container-device-interface) is a Kubernetes specification that defines how devices (such as GPUs, specialized hardware, or other physical resources) can be exposed and made accessible to containers running in Kubernetes clusters. CDI allows Kubernetes workloads to efficiently utilize hardware resources directly without relying on custom configurations or vendorspecific solutions.

CDI provides a standard interface for device plugins to interface with Kubernetes and expose devices to containers. This enables Kubernetes to allocate, configure, and manage devices, making it easier to leverage specialized hardware for resource-intensive applications like machine learning or high-performance computing. The interface aims to standardize the management of devices across Kubernetes clusters, promoting flexibility and interoperability.

* [Device Plugins](https://kubernetes.io/docs/concepts/extend-kubernetes/compute-storage-net/device-plugins/)
* [Akri](https://github.com/project-akri/akri)

### Node Resource Interface - NRI

The [Containerd NRI (Node Resource Interface) ](https://github.com/containerd/nri)is an open-source project designed to extend container runtimes with support for exposing node-level resources to containerized workloads. NRI allows container runtimes like containerd to integrate with specific device management systems or hardware capabilities, enabling containers to leverage specialized resources (such as GPUs, network interfaces, or storage devices). By using NRI, Kubernetes and other container orchestration platforms can easily manage these node-level resources, improving efficiency and performance for resource-intensive applications. The NRI project provides a standardized approach for accessing and managing these resources in Kubernetes and other containerized environments.

* [NVIDIA device plugin for Kubernetes](https://github.com/NVIDIA/k8s-device-plugin)

### Dynamic Resource Allocation - DRA

[Dynamic Resource Allocation](https://kubernetes.io/docs/concepts/scheduling-eviction/dynamic-resource-allocation/) is an API for requesting and sharing resources between pods and containers inside a pod. It is a generalization of the persistent volumes API for generic resources. Typically those resources are devices like GPUs.

* [Nvidia DRA Driver](https://github.com/NVIDIA/k8s-dra-driver)
* [Dynamic Resource Allocation in Kubernetes](https://seifrajhi.github.io/blog/k8s-dynamic-resource-allocation-dra/)
* [DRA example driver](https://github.com/kubernetes-sigs/dra-example-driver)
