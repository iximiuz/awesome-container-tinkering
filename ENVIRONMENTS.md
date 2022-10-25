# Handy Container Environments

Solutions to run containers locally and remotely.

See also this [great summary of local container runtimes](https://docs.google.com/spreadsheets/d/1ZT8m4gpvh6xhHYIi4Ui19uHcMpymwFXpTAvd3EcgSm4/edit#gid=0) by Bret Fisher.

### ⭐ Docker Desktop

<a href="https://www.docker.com/products/docker-desktop/">Docker Desktop</a> - "The fastest way to containerize applications."

At the heart of Docker Desktop is a <a href="https://github.com/linuxkit/linuxkit">LinuxKit</a> VM running Docker Engine and fronted by an electron (?) GUI. This architecture makes it work the same way on Windows, macOS, and Linux. Additionally, Docker Desktop comes bundled with a local Kubernetes cluster and a powerful mechanism of (graphical) extensions.

### Rancher Desktop

<a href="https://github.com/rancher-sandbox/rancher-desktop/">Rancher Desktop</a> - "Container Management and Kubernetes on the Desktop."

Similar to Docker Desktop but with more focus on local Kubernetes clusters (although it can be used with the Kubernetes functionality disabled). Uses <a href="https://github.com/lima-vm/lima">Lima VMs</a> instead of LinuxKit. Can run either Docker Engine or containerd + nerdctl inside of a VM.

### Podman Desktop

<a href="https://github.com/containers/podman-desktop">Podman Desktop</a> - "Manage Podman and other container engines from a single UI and tray."

### Lima

<a href="https://github.com/lima-vm/lima">Lima</a> - "Linux virtual machines, typically on macOS, for running containerd."

### Colima

<a href="https://github.com/abiosoft/colima">Colima</a> - "Container runtimes on macOS (and Linux) with minimal setup."

### virt

<a href="https://github.com/apinske/virt">virt</a> - "small Linux VM, ready to run containers, for macOS on ARM." Like Lima but for Podman and using the Apple Virtualization.framework instead of QEMU.

### nerdctl

<a href="https://github.com/containerd/nerdctl">nerdctl</a> - "contaiNERD CTL - Docker-compatible CLI for containerd, with support for Compose, Rootless, eStargz, OCIcrypt, IPFS, ..."

### minikube

<a href="https://github.com/kubernetes/minikube">minikube</a> - "Run Kubernetes locally."

Despite the name, <a href="https://minikube.sigs.k8s.io/docs/faq/#can-i-start-minikube-without-kubernetes-running">minikube can be used without Kubernetes!</a>. Running `minikube start --container-runtime=docker --no-kubernetes` gives you some sort of a Docker Desktop replacement. It also uses a lightweight VM to run Docker Engine and works perfectly fine on Windows, macOS (`arm` performance is poor though), and Linux.

### Vagrant + VirtualBox + Docker provisioner

<a href="https://github.com/hashicorp/vagrant">Vagrant</a> - "Vagrant is a tool for building and distributing development environments."

Vagrant is many things, but in particular it can be used as a handy VirtualBox frontend. With just <a href="https://developer.hashicorp.com/vagrant/docs/provisioning/docker">about 5 lines of config</a>, you can get a local VM with Docker Engine inside. Works the same way on Linux, Windows, and macOS, but no `arm` support is possible. Read more - <a href="https://iximiuz.com/en/posts/how-to-setup-development-environment/">Disposable Local Development Environments with Vagrant, Docker, and Arkade</a>.
