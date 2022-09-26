# Container Runtimes And Related Tools

Partially systematized. Eventually, will include some commentary.


## Low-level container runtimes

### ⭐ runc

<a href="https://github.com/opencontainers/runc">runc</a> - "CLI tool for spawning and running containers according to the OCI specification." The reference implementation of the holly <a href="https://github.com/opencontainers/runtime-spec">OCI Runtime Specification</a>. Written in Go.

### crun

<a href="https://github.com/containers/crun">crun</a> - "A fast and lightweight fully featured OCI runtime and C library for running containers" - much like runc but written in C and with a possibility to use as a library.

### youki

<a href="https://github.com/containers/youki">youki</a> - "A container runtime written in Rust." Same as above, but in Rust.

### runj

<a href="https://github.com/samuelkarp/runj">runj</a> - "An experimental, proof-of-concept OCI-compatible runtime for FreeBSD jails."

### 🪦 runv

<a href="https://github.com/hyperhq/runv">runv</a> - "Hypervisor-based Runtime for OCI."

### sysbox

<a href="https://github.com/nestybox/sysbox">sysbox</a> - "An open-source, next-generation "runc" that empowers rootless containers to run workloads such as Systemd, Docker, Kubernetes, just like VMs." Started as an independent project but was <a href="https://www.docker.com/blog/docker-advances-container-isolation-and-workloads-with-acquisition-of-nestybox/">acquired by Docker Inc. in May 2022</a>.

### gVisor

<a href="https://github.com/google/gvisor">gVisor</a> - "Application Kernel for Containers." gVisor is an application kernel, written in Go, that implements a substantial portion of the Linux system surface. It includes an Open Container Initiative (OCI) runtime called runsc that provides an isolation boundary between the application and the host kernel. The runsc runtime integrates with Docker and Kubernetes, making it simple to run sandboxed containers.

### Firecracker

<a href="https://github.com/firecracker-microvm/firecracker">firecracker</a> - "Secure and fast microVMs for serverless computing."

### Kata Containers

<a href="https://github.com/kata-containers/kata-containers">Kata Containers</a> - "An open source project and community working to build a standard implementation of lightweight Virtual Machines (VMs) that feel and perform like containers, but provide the workload isolation and security advantages of VMs."

### bubblewrap

<a href="https://github.com/containers/bubblewrap">bubblewrap</a> - "Unprivileged sandboxing tool."

### systemd-nspawn

<a href="https://github.com/systemd/systemd/blob/main/src/nspawn/nspawn.c">systemd-nspawn</a> - "Like the chroot command, but it is a chroot on steroids." May be used to run a command or OS in a light-weight namespace container.


## Container-runtime shims

A piece of software that sits in between a low-level container runtime and a higher-level container runtime.

## conmon

<a href="https://github.com/containers/conmon">conmon</a> - "An OCI container runtime monitor."

## conmon-rs

<a href="https://github.com/containers/conmon-rs">conmon-rs</a> - conmon, but in Rust.

## containerd-runtime-shim

<a href="https://github.com/containerd/containerd/blob/main/runtime/v2/README.md">containerd-runtime-shim</a> - "A first class shim API [and a few implementations] for runtime authors to integrate with containerd."


## Mid-level container runtimes

### ⭐ containerd

<a href="https://github.com/containerd/containerd">containerd</a> - "An open and reliable container runtime."

### firecracker-containerd

<a href="https://github.com/firecracker-microvm/firecracker-containerd">firecracker-containerd</a> - "enables containerd to manage containers as Firecracker microVMs."

### cri-o

<a href="https://github.com/cri-o/cri-o">cri-o</a> - "Open Container Initiative-based implementation of Kubernetes Container Runtime Interface."

### lxc

<a href="https://github.com/lxc/lxc">lxc</a> - "Linux Containers."

### lxd

<a href="https://github.com/lxc/lxd">lxd</a> - "Powerful system container and virtual machine manager."

### 🪦 rkt

<a href="https://github.com/rkt/rkt">rkt</a> - [discontinued] "rkt is a pod-native container engine for Linux. It is composable, secure, and built on standards."


## High-level container runtimes

### Moby (Docker)

<a href="https://github.com/moby/moby">Moby</a> - "A collaborative project for the container ecosystem to assemble container-based systems." Docker lives somewhere here.

### Docker Compose

<a href="https://github.com/docker/compose">compose</a> - "Define and run multi-container applications with Docker"

### Podman

<a href="https://github.com/containers/podman">podman</a> - "A tool for managing OCI containers and pods." Daemonless drop-in replacement for Docker (not quite).


## Misc

### boker

<a href="https://github.com/icy/bocker">icy/bocker</a> & <a href="https://github.com/p8952/bocker">p8952/bocker</a> - "Docker implemented in around 100 lines of bash."

### contained.af

<a href="https://github.com/genuinetools/contained.af">contained.af</a> - "A stupid game for learning about containers, capabilities, and syscalls."
