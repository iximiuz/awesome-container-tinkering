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

<a href="https://github.com/google/gvisor">gVisor</a> - "Application Kernel for Containers." gVisor is an application kernel (<a href="https://en.wikipedia.org/wiki/User-mode_Linux">User-mode Linux</a>), written in Go, that implements a substantial portion of the Linux system surface. It includes an Open Container Initiative (OCI) runtime called runsc that provides an isolation boundary between the application and the host kernel. The runsc runtime integrates with Docker and Kubernetes, making it simple to run sandboxed containers.

### Quark

<a href="https://github.com/QuarkContainer/Quark">Quark</a> - "A secure container runtime with CRI/OCI interface." Quark provides VM-level workload isolation and security with its own hypervisor (QVisor) and a guest kernel (QKernel) - yet another <a href="https://en.wikipedia.org/wiki/User-mode_Linux">User-mode Linux</a> implementation?

### Firecracker

<a href="https://github.com/firecracker-microvm/firecracker">firecracker</a> - "Secure and fast microVMs for serverless computing."

### Kata Containers

<a href="https://github.com/kata-containers/kata-containers">Kata Containers</a> - "An open source project and community working to build a standard implementation of lightweight Virtual Machines (VMs) that feel and perform like containers, but provide the workload isolation and security advantages of VMs."

### libkrun

<a href="https://github.com/containers/libkrun">libkrun</a> - "A dynamic library providing Virtualization-based process isolation capabilities." Can be used for adding VM-isolation capabilities to an OCI runtime like runc, crun, etc.

### bubblewrap

<a href="https://github.com/containers/bubblewrap">bubblewrap</a> - "Unprivileged sandboxing tool."

### systemd-nspawn

<a href="https://github.com/systemd/systemd/blob/main/src/nspawn/nspawn.c">systemd-nspawn</a> - "Like the chroot command, but it is a chroot on steroids." May be used to run a command or OS in a light-weight namespace container.

### NsJail

<a href="https://github.com/google/nsjail">NsJail</a> - "A light-weight process isolation tool, making use of Linux namespaces and seccomp-bpf syscall filters (with help of the kafel bpf language)."

### Kuasar

<a href="https://github.com/kuasar-io/kuasar">Kuasar</a> - "An efficient container runtime that provides cloud-native, all-scenario multiple sandbox container solutions." Kuasar is a _facade runtime_ that turns other runtimes into _sandboxers_ implementing the <a href="https://github.com/containerd/containerd/issues/4131">containerd Sandbox API</a>. Currently supported sandboxers: MicroVM (Cloud Hypervisor, StratoVirt and QEMU), App Kernel (gVisor and Quark), and Wasm (WasmEdge).


## Mid-level container runtimes

### ⭐ containerd

<a href="https://github.com/containerd/containerd">containerd</a> - "An open and reliable container runtime."

### firecracker-containerd

<a href="https://github.com/firecracker-microvm/firecracker-containerd">firecracker-containerd</a> - "enables containerd to manage containers as Firecracker microVMs."

### Flintlock

<a href="https://github.com/weaveworks-liquidmetal/flintlock">Flintlock</a> - "Lock, Stock, and Two Smoking MicroVMs. Create and manage the lifecycle of MicroVMs backed by containerd." Create and manage the lifecycle of MicroVMs, backed by containerd.

### Vorteil

<a href="https://github.com/direktiv/vorteil">Vorteil</a> - "turn your applications and containers into micro virtual machines."

### cri-o

<a href="https://github.com/cri-o/cri-o">cri-o</a> - "Open Container Initiative-based implementation of Kubernetes Container Runtime Interface (CRI)."

### virtlet

<a href="https://github.com/Mirantis/virtlet">virtlet</a> - "Kubernetes CRI implementation for running VM workloads."

### LXC

<a href="https://github.com/lxc/lxc">LXC</a> - "Linux Containers." An alternative (i.e., non-OCI) implementation of containers using Linux OS-level virtualization primitives (namespaces, cgroups, etc). Daemonless, can work as a library or as a CLI tool. Back in 2013, Docker started as UX a layer on top of LXC but eventually moved to its own implementation (known as **runc** nowadays). Read this <a href="https://lwn.net/Articles/907613/">alternative story of containers on LWN.net for more</a>.

### LXD

<a href="https://github.com/lxc/lxd">LXD</a> - "Powerful system container and virtual machine manager." A daughter project of LCX. Like the Docker daemon, LXD is a daemon providing HTTP API to manage containers powered by LXC. LXD comes with a CLI client called _lxc_ (not to be confused with LXC's own CLI clients, though).

### 🪦 rkt

<a href="https://github.com/rkt/rkt">rkt</a> - [discontinued] "rkt is a pod-native container engine for Linux. It is composable, secure, and built on standards."

### 🎓 conman

<a href="https://github.com/iximiuz/conman">conman</a> - a toy container manager written for educational purposes. <a href="https://iximiuz.com/en/series/implementing-container-manager/">Read more about the conman project on iximiuz.com</a>.


## High-level container runtimes

### Docker Engine _aka_ Moby

<a href="https://github.com/moby/moby">Moby</a> - "A collaborative project for the container ecosystem to assemble container-based systems." Docker lives somewhere here.

### Docker Compose

<a href="https://github.com/docker/compose">compose</a> - "Define and run multi-container applications with Docker."

### Podman

<a href="https://github.com/containers/podman">podman</a> - "A tool for managing OCI containers and pods." Daemonless drop-in replacement for Docker (not quite).

### Focker

<a href="https://github.com/sadaszewski/focker">Focker</a> - "A FreeBSD image/jail orchestration tool in the vein of Docker."

A Docker-like tool written in Python and using FreeBSD jails instead of Linux namespaces & co.

### footloose

<a href="https://github.com/weaveworks/footloose">footloose</a> - "Container Machines - Containers that look like Virtual Machines."

Regular containers but with systemd as PID 1 and an SSH daemon inside. Such "machines" behave very much like a VM, it's even possible to run dockerd in them.

### OrbStack

<a href="https://orbstack.dev/">OrbStack</a> - "Run Docker [containers] and Linux [VMs] on your Mac seamlessly and efficiently." It looks like a Docker Desktop alternative (but probably without the Docker Desktop extensions yet) with a bunch of appealing capabilities: promises to be fast(er), has a native macOS UI app, can run full-blown Intel and Apple Silicon Linux VMs with the ease of regular containers. Although it does have one big downside - it's not open-source (but seems to be free for the time being).


## Container-runtime shims

A piece of software that sits in between a low-level container runtime and a higher-level container runtime.

### conmon

<a href="https://github.com/containers/conmon">conmon</a> - "An OCI container runtime monitor."

### conmon-rs

<a href="https://github.com/containers/conmon-rs">conmon-rs</a> - conmon, but in Rust.

### containerd-runtime-shim

<a href="https://github.com/containerd/containerd/blob/main/runtime/v2/README.md">containerd-runtime-shim</a> - "A first class shim API [and a few implementations] for runtime authors to integrate with containerd."

### 🎓 shimmy

<a href="https://github.com/iximiuz/shimmy">shimmy</a> - a toy container runtime shim written for educational purposes. Part of the **conman** project.


## Introspection and debugging tools

### cdebug

<a href="https://github.com/iximiuz/cdebug">cdebug</a> - "a swiss army knife of container debugging."

The `cdebug exec` command is a crossbreeding of `docker exec` and `kubectl debug` commands. You point the tool at a running container, say what toolkit image to use, and it starts a debugging "sidecar" container that feels like a regular `docker exec` session (i.e., shares most of the target container's namespaces and has the same rootfs).

The `cdebug port-forward` command is another crossbreeding - this time it's `kubectl port-forward` and `ssh -L|-R`. With `cdebug port-forward -L` you can forward traffic destined to a host's port to an arbitrary container port even if it wasn't published or the target container is listening on localhost. With `cdebug port-forward -R` (coming soon) you can expose any endpoints accessible from your host back to the container' or Kubernetes network.

### debug-ctr

<a href="https://github.com/felipecruz91/debug-ctr">debug-ctr</a> - "Commandline tool for interactive container troubleshooting."

A debugger that creates a new container out of the original container with the toolkit mounted in a volume.

### docker-debug

<a href="https://github.com/zeromake/docker-debug">docker-debug</a> - "use new container attach on already container go on debug."

Start a new container with an image of choice (`nicolaka/netshoot` by default) that shares (some of) the target container's namesapces. Much like `cdebug exec` but with no `chroot` magic and supports only Docker as a container runtime.

### docker-opener

<a href="https://github.com/artemkaxboy/docker-opener">docker-opener</a> - "Shell-in to any docker container easily."

A multi-purpose tool that in particular can run a shell session into your container (and if there is no shell inside, it'll bring its own busybox).

### cntr

<a href="https://github.com/Mic92/cntr">cntr</a> - "A container debugging tool based on FUSE."

"A replacement for `docker exec` that brings all your developers tools with you" by mounting the file system from one container (or the host) into the target container and creating a nested container with the help of a FUSE filesystem. Supports a huge range of runtimes (docker, podman, LXC/LXD, rkt, systemd-nspawn, containerd) because it operates directly on the OS level.

### 👨‍🔬 kdiag

<a href="https://github.com/solo-io/kdiag">kdiag</a> - "Diagnostics and Debug Tooling" for Kubernetes workloads.

A kubectl plugin to get shell access to scratch containers, stream logs from multiple pods simultaneously, and do reverse port forwarding to Kubernetes clusters.

### ⚠️ amicontained

<a href="https://github.com/genuinetools/amicontained">amicontained</a> - "Container introspection tool. Find out what container runtime is being used as well as features available."


## In-container init systems

### ⭐ tini

<a href="https://github.com/krallin/tini">tini</a> - "A tiny but valid `init` for containers."

Tini is meant to be run in a container - it spawns a single child and waits for it to exit all the while reaping zombies and performing signal forwarding. Written in C, and comes in both, dynamically and statically linked, forms.

### dumb-init

<a href="https://github.com/yelp/dumb-init">dumb-init</a> - "A minimal init system for Linux containers."

A simple process supervisor and init system designed to run as PID 1 inside minimal container environments. It is deployed as a small, statically-linked binary written in C.

### 🧑‍🔬 pid1

<a href="https://github.com/fpco/pid1">pid1</a> - "Do signal handling and orphan reaping for Unix PID1 init processes."

A Haskell library, and an executable based on that library, for initializing signal handlers, spawning child processes, and reaping orphan processes.


## Misc

### 🎓 boker

<a href="https://github.com/icy/bocker">icy/bocker</a> & <a href="https://github.com/p8952/bocker">p8952/bocker</a> - "Docker implemented in around 100 lines of bash."

### 🎓 Gocker

<a href="https://github.com/shuveb/containers-the-hard-way">Containers the hard way: Gocker</a> - "Learning about containers and how they work by creating them the hard way."

Gocker is a "from scratch" implementation of the core functionalities of Docker - to provide an understanding of how exactly containers work at the Linux system call level. Written in Go.

### 🎓 contained.af

<a href="https://github.com/genuinetools/contained.af">contained.af</a> - "A stupid game for learning about containers, capabilities, and syscalls."
