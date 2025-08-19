# Tools To Deal With Container Images

## Base images

* [Artifact Distributors](./ARTIFACT-DISTRIBUTORS.md)

### Distroless 1.0

<a href="https://github.com/GoogleContainerTools/distroless">distroless</a> - "Language focused docker images, minus the operating system" _aka_ "scratch for everyone else." 

Read <a href="https://iximiuz.com/en/posts/containers-distroless-images/">my overview of the distroless project on iximiuz.com</a>.

### Chainguard Images

<a href="https://github.com/chainguard-images">Chainguard Images</a> - "A collection of container (OCI) images designed for minimalism and security."

Many of them are distroless and contain only an application and its runtime dependencies. Typically, there is no shell or package manager. Image building procedure is designed to be reproducible and declarative (see **apko** and **melange** below).

## Image Building

### ⭐ BuildKit

<a href="https://github.com/moby/buildkit">BuildKit</a> - "concurrent, cache-efficient, and Dockerfile-agnostic builder toolkit."

A daemon that, in particular, powers the Docker image building. Uses its own intermediate language (LLB) to describe build tasks (but comes with a default frontend that compiles Dockerfiles to LLB). Can produce different forms of artifacts (Docker images, OCI images, tar archives, local files). Uses isolated builder backends (containers, remote servers, in-kubernetes builders, etc). Supports out-of-the-box cross-platform builds, different cache sources & destinations (inline, registry, local, etc). Check out this [good practical overview](https://blog.kubesimplify.com/the-secret-gems-behind-building-container-images-enter-buildkit-and-docker-buildx) for more.

### ⭐ Docker buildx plugin

<a href="https://github.com/docker/buildx">buildx</a> - "Docker CLI plugin for extended build capabilities with BuildKit."

At first sight, the plugin is just another `docker build`-like command but on top of a better build engine (BuildKit). Often I'd just replace `docker build` with `docker buildx build` and call it a day. In actuality, though, `docker buildx` is the de facto standard CLI tool to access the full power of BuildKit. There is much more than just `docker buildx build` (see the list of BuildKit's capabilities above).

### 🧑‍🔬 bake

<a href="https://github.com/docker/buildx/blob/master/docs/reference/buildx_bake.md">bake</a> - container-aware _make_.

This _buildx_ subcommand is worth mentioning separately:

> BuildKit efficiently handles multiple concurrent build requests and de-duplicates work. The build commands can be combined with general-purpose command runners (for example, `make`). However, these tools generally invoke builds in sequence and therefore cannot leverage the full potential of BuildKit parallelization, or combine BuildKit's output for the user. For this use case, we have added a command called `docker buildx bake`.

The `bake` command supports building images (<a href="https://iximiuz.ck.page/posts/container-tools-tips-and-tricks-issue-1">and not only</a>) from HCL or JSON files by describing _make_-like targets. And it also understands docker-compose YAML files.

### Buildah

<a href="https://github.com/containers/buildah">Buildah</a> - "A tool that facilitates building OCI images."

### kaniko

<a href="https://github.com/GoogleContainerTools/kaniko">kaniko</a> - "Build Container Images In Kubernetes."

### 🪦 makisu

<a href="https://github.com/uber-archive/makisu">makisu</a> - [discontinued] "Fast and flexible Docker image building tool, works in unprivileged containerized environments like Mesos and Kubernetes."

### ⚠️ img

<a href="https://github.com/genuinetools/img">img</a> - "Standalone, daemon-less, unprivileged Dockerfile and OCI compatible container image builder." The project looks abandoned.

### ko

<a href="https://github.com/ko-build/ko">ko</a> - "Build and deploy Go applications." `ko` is a simple (no Dockerfiles required) container image builder for Go application without any/many dependencies on the OS base image (e.g., no cgo, no OS package dependencies).

### no

<a href="https://github.com/thesayyn/no">no</a> - "Easy NodeJS containers." Like `ko` but for NodeJS.

### Jib

<a href="https://github.com/GoogleContainerTools/jib">Jib</a> - "Build container images for your Java applications." Like `ko` but for Java - build optimized Docker (or OCI) images for Java applications without a Docker daemon. Available as plugins for Maven and Gradle and as a Java library.

### ⚠️ 👨‍🔬 kim

<a href="https://github.com/rancher/kim">kim</a> - "The Kubernetes Image Manager."

The tool consists of a builder backend (BuildKit daemon bound to the kubelet's underlying containerd socket) and a server-side agent (both deployed as one DaemonSet), and the _kim_ CLI (that talks to the agent) with a classic Docker-like UX for image management (push, pull, etc).

### ⭐ Packer

<a href="https://github.com/hashicorp/packer">Packer</a> - "A tool for creating identical machine images for multiple platforms from a single source configuration."

Packer is primarily focused on producing virtual machine images but it also allows building Docker, LXC, and LXD images using a similar to VM-provisioning procedure (read, by putting shell commands into a HCL file).

### ImageBuilder

<a href="https://github.com/kubernetes-sigs/image-builder">Image Builder</a> - "is a tool designed to create Kubernetes virtual machine images compatible with various infrastructure providers. These VM images are primarily intended for use with Cluster API but are also suitable for other setups that rely on Kubeadm."

The project utilizes Packer and Ansible to automate the image creation process, ensuring consistency and repeatability across different environments. It supports multiple operating systems and cloud platforms, enabling users to customize images according to their specific requirements.

* [ImageBuilder Quickstart](https://image-builder.sigs.k8s.io/capi/quickstart)

### Cloud Native Buildpacks

<a href="https://github.com/buildpacks">Cloud Native Buildpacks</a> - "Transform your application source code into images that can run on any cloud."

### apko

<a href="https://github.com/chainguard-dev/apko">apko</a> - "Build OCI images using APK directly without Dockerfile." A tool to produce minimalistic container images that include only the needed packages.

### melange

<a href="https://github.com/chainguard-dev/melange">melange</a> - "Build APKs from source code". A complimentary tool for apko.

### Chisel

<a href="https://github.com/canonical/chisel">Chisel</a> - an early-day project by Canonical. Similar idea to **apko** and **melange** but on top of the Ubuntu base. Read this <a href="https://devblogs.microsoft.com/dotnet/dotnet-6-is-now-in-ubuntu-2204/">Microsoft devblog article about large(r) scale application of Chisel for producing _.NET on Ubuntu_ images</a>.

### Nixery

<a href="https://github.com/tazjin/nixery">Nixery</a> - "Docker images on the fly with Nix". A Docker-compatible container registry that transparently builds images using the Nix package manager.

### Devbox

<a href="https://github.com/jetpack-io/devbox">Devbox</a> - "Instant, easy, predictable shells and containers."

Devbox is a command-line tool that lets you create isolated shells and containers. You start by defining the list of packages required by your development environment, and Devbox uses that definition to create an isolated environment just for your application. You can use it right away, or turn it into a OCI container image. No Dockerfiles are involved. Powered by Nix.

### buildg

<a href="https://github.com/ktock/buildg">buildg</a> - "Interactive debugger for Dockerfile, with support for IDEs (VS Code, Emacs, Neovim, etc)."

### Binfmt

<a href="https://github.com/tonistiigi/binfmt">Binfmt</a> - "Cross-platform emulator (QEMU) collection distributed with Docker images." A handy tool for cross-platform builds of all kinds.

### xx

<a href="https://github.com/tonistiigi/xx">xx</a> - "Dockerfile cross-compilation helpers."

A collection of tools to support cross-compilation from Dockerfiles that understand the `--platform` flag passed in from `docker build` or `docker buildx build`. These helpers allow you to build multi-platform images from any architecture into any architecture supported by your compiler with native performance. Adding `xx` to your Dockerfile should only need minimal updates and should not require custom conditions for specific architectures. Example: `apk add` becomes `xx-apk add`, `apt-get install` becomes `xx-apt-get install`, `go build` becomes `xx-go build`, etc.

### dockle

<a href="https://github.com/goodwithtech/dockle">dockle</a> - "Container Image Linter for Security, Helping build the Best-Practice Docker Image, Easy to start."

The tool promises to help with following the image building best practices and produce (more) secure Docker images.

### 🎓 Build Containers the Hard Way

<a href="https://github.com/coollog/build-containers-the-hard-way">Build Containers the Hard Way</a> - "GitBook on the low-level details of building Docker containers."

Like Kubernetes the Hard Way, but for building containers.

### container2wasm

<a href="https://github.com/ktock/container2wasm">container2wasm</a> - "Container to WASM converter."

An image converter that enables running unmodified containers on WASM (various runtimes: wasmtime, wamr, wazero, and even in the browser).
The tool creates a WASM image that runs the container (using the standard `runc` runtime) and the Linux kernel on the emulated (via Bochs or TinyEMU) CPU.

### bootc

<a href="https://github.com/containers/bootc">bootc</a> - "Boot and upgrade [virtual or physical machines] via container images."

The project aims to use standard OCI/Docker images for bootable host systems - as a build, transport, and delivery format for base OS images.
Created with bootc container images include a Linux kernel (in e.g. `/usr/lib/modules`), which is used to boot a full-fledged physical or virtual machine.
After booting on a server, such an image runs not in a container but as the host OS.

### docker-to-linux

<a href="https://github.com/iximiuz/docker-to-linux">docker-to-linux</a> - "Make bootable Linux disk image (ab)using Docker."

A similar idea to bootc, but tailored for edu purposes. Launch a base Linux container (Debian, Alpine, etc.), pull in Linux kernel & init system (systemd, OpenRC, etc.), dump container's filesystem to a disk image, install bootloader (syslinux) to this image, and convert it into a QEMU (or the like) VM image.


## Image Inspection

### dive

<a href="https://github.com/wagoodman/dive">dive</a> - "A tool for exploring each layer in a docker image."

### diffoci

<a href="https://github.com/reproducible-containers/diffoci">diffoci</a> - "diff for Docker and OCI container images."

The purpose is to improve the software supply chain security by, for instance, comparing images that were built locally with images pulled from a remote source like Docker Hub.

### container-diff

<a href="https://github.com/GoogleContainerTools/container-diff">container-diff</a> - "Diff your Docker containers."

### 👨‍🔬 car

<a href="https://github.com/tetratelabs/car">car</a> - "Like tar, but for containers!"

Car lets you list or extract files from an OCI (possibly Docker) image, regardless of the platform it was built for. For example, you can extract files from a windows/amd64 image even if you are running linux/arm64.

### ima.ge.cx (site)

<a href="https://ima.ge.cx/">ima.ge.cx</a> - "a site that allows you to inspect the contents of Docker images."

By just specifying the image name in the path like <a href="https://ima.ge.cx/nginx:alpine">https://ima.ge.cx/nginx:alpine</a>, you can browse the image filesystem and even view textual files right in your browser.

### explore (site)

[explore](https://explore.ggcr.dev/) - "A tool for exploring the layers and filesystem of an image from the browser."


## Image Editing

### umoci

<a href="https://github.com/opencontainers/umoci">umoci</a> - "umoci modifies Open Container images."

## Image Optimization

### DockerSlim

<a href="https://github.com/docker-slim/docker-slim">DockerSlim</a> - "Don't change anything in your Docker container image and minify it by up to 30x (and for compiled languages even more)."

## Image Distribution

### ⭐ Distribution

<a href="https://github.com/distribution/distribution">Distribution</a> - "The toolkit to pack, ship, store, and deliver container content."

An open-source registry implementation for storing and distributing container images using the OCI Distribution Specification with the goal to provide a simple, secure, and scalable base for building a large scale registry solution or running a simple private registry. Used by Docker Hub, GitHub Container Registry, GitLab Container Registry, DigitalOcean Container Registry, CNCF Harbor Project, VMware Harbor Registry, and more.

### skopeo

<a href="https://github.com/containers/skopeo">skopeo</a> - "Work with remote images registries - retrieving information, images, signing content."

### go-containerregistry/crane

<a href="https://github.com/google/go-containerregistry/blob/main/cmd/crane/README.md">crane</a> - "A tool for interacting with remote images and registries. You can try out a web version of crane [here](https://crane.ggcr.dev/)"

### go-containerregistry/krane

<a href="https://github.com/google/go-containerregistry/blob/main/cmd/krane/README.md">krane</a> - "A drop-in replacement for crane that supports common Kubernetes-based workload identity mechanisms."

### regclient

<a href="https://github.com/regclient/regclient">regclient</a> - "Docker and OCI Registry Client in Go and tooling using those libraries."

A client interface to interact with registries: inspect images w/o pulling, list repository's tags, list registry's repositories (if supported), efficiently copy images between repositories, import/export OCI and Docker images, etc. Seems to be written from scratch with just a few dependencies.

### ⚠️ reg

<a href="https://github.com/genuinetools/reg">reg</a> - "Docker registry v2 command line client and repo listing generator with security checks." The project looks abandoned.

### OCI Registry Artifact Storage (ORAS)

<a href="https://oras.land/">ORAS</a> - "Push and pull OCI Artifacts to and from OCI Registries."

Since the invention of OCI registries, people have been (ab)using them to store non-container things (Helm charts, OPA policies, even video files can be stored this way). The modern registries are evolving as generic artifact stores, and the ORAS project provides a way to push and pull OCI Artifacts (read _arbitrary files_) to and from OCI Registries. The project consists of a CLI (<a href="https://github.com/oras-project/oras">_oras_</a>) and libraries (<a href="https://github.com/oras-project/oras-go">Go</a>, <a href="https://github.com/oras-project/oras-py">Python</a>).

### 🧑‍🔬 Docker Hub Tool

<a href="https://github.com/docker/hub-tool">Docker Hub Tool</a> - "Docker Hub experimental CLI tool."

A CLI tool for interacting with the Docker Hub. Get information about your images from the terminal. Docker's experiment to build a Docker Hub CLI tool. The intention of this project is to get user feedback and then to add this functionality to the Docker CLI itself.

## ContainerD Snapshotter

A [Containerd Snapshotter](https://github.com/containerd/containerd/blob/main/docs/snapshotters/README.md) is a crucial component in containerized environments, responsible for managing container image layers and filesystem snapshots with high efficiency. It leverages a copy-on-write (CoW) mechanism, which minimizes storage usage by allowing containers to share common layers while enabling rapid container startup. Snapshotters support a wide variety of backend implementations, including popular ones like overlayfs, devmapper, zfs, blockfile, btrfs, native vfs, and erofs. Additionally, there are support options for non-standard, remote plugins such as fuse-overlayfs, nydus-snapshotter, nix-snapshotter, as well as cloud service-specific snapshotters, providing extensive flexibility tailored to different system and infrastructure requirements. This diversity enables containerized applications to be deployed efficiently across various platforms, optimizing performance and storage management.

A great overview of containerd image handling can be found in the blog post by Samuel Karp:

[Containerd Internals: Images](https://samuel.karp.dev/blog/2024/12/containerd-internals-images/)

### OverlayFS

The standard overlayfs snapshotter in containerd uses OverlayFS to provide a copy-on-write (CoW) filesystem, enabling efficient storage and fast container startup. It layers image data dynamically, reducing duplication and improving performance. This is the default snapshotter for most Linux environments due to its simplicity and kernel-level integration.

### DevMapper

The [devmapper snapshotter](https://github.com/containerd/containerd/blob/main/docs/snapshotters/devmapper.md) in containerd leverages Device Mapper to provide thin-provisioned snapshots for container storage. It supports XFS and EXT4 filesystems, enabling efficient space usage and faster provisioning. This snapshotter is ideal for environments requiring persistent storage, strong isolation, and optimized disk utilization.

### ZFS snapshotter

[ZFS Snapshotter](https://github.com/containerd/zfs) is a containerd snapshotter that utilizes the ZFS filesystem to manage container images with advanced features like efficient snapshots, data integrity, and compression. It leverages ZFS's ability to handle large volumes of data and support copy-on-write (CoW) for optimized storage and performance. This snapshotter is ideal for environments requiring high reliability, data protection, and scalability.

### Nydus snapshotter

[Nydus Snapshotter](https://github.com/containerd/nydus-snapshotter) is a high-performance containerd snapshotter that enables data deduplication and lazy loading for container images. It uses a P2P distribution model, reducing storage and network overhead by loading only required data chunks on demand. This optimizes container startup times and enhances efficiency in large-scale deployments.

### FUSE-OverlayFS snapshotter

[fuse-overlayfs-snapshotter](https://github.com/containerd/fuse-overlayfs-snapshotter) is a snapshotter for containerd that leverages FUSE-based overlayfs, enabling unprivileged containers to use overlay filesystems without requiring kernel support. It improves compatibility in environments where native overlayfs is restricted, such as rootless containers. This enhances flexibility and security while maintaining efficient image storage and layering.

### Stargz snapshotter

[Stargz Snapshotter](https://github.com/containerd/stargz-snapshotter) is a containerd snapshotter that enables lazy loading of container images using eStargz format. It reduces startup time by fetching only necessary data on demand, improving efficiency in large-scale deployments. This snapshotter is ideal for speeding up container boot times, especially in cloud and edge environments.

### Overlaybd snapshotter

Accelerated Container Image (ACI) is a [containerd snapshotter](https://github.com/containerd/accelerated-container-image) designed for fast container startup by leveraging lazy loading and on-demand decompression. It optimizes image distribution by fetching only required data, reducing I/O overhead. This improves efficiency in cloud-native environments, especially for large-scale and high-performance workloads.

At the heart of the acceleration is overlaybd, which is a new remote image format based on block device. Overlaybd backstore provides a merged view of a sequence of block-based layers in userspace and outputs as a virtual blocks device through [TCMU](https://www.kernel.org/doc/Documentation/target/tcmu-design.txt). It can be used for container acceleration by supporting fetching image data on-demand without downloading and unpacking the whole image before a container running. With overlaybd image format, we can cold start a container instantly.

### NIX snapshotter

[Nix-snapshotter](https://github.com/pdtpartners/nix-snapshotter) enables Kubernetes to use Nix store paths as container images, bypassing traditional image layers and registries. It integrates with CRI to fetch packages from a Nix binary cache or build them dynamically while maintaining compatibility with standard OCI images. This approach ensures fully declarative and reproducible Kubernetes deployments.

### GKE Image Streaming snapshotter

[GKE Image Streaming](https://cloud.google.com/kubernetes-engine/docs/how-to/image-streaming?hl=de) allows Google Kubernetes Engine (GKE) to pull container images directly from the Google Cloud Storage (GCS) or other cloud repositories, reducing the need for a Docker registry. It supports snapshotted images, enabling efficient image management and faster deployments by leveraging cloud-native image distribution. This feature optimizes image delivery, enhances performance, and simplifies container management in Kubernetes clusters.

### AKS Artifact Streaming snapshotter

[Artifact Streaming](https://learn.microsoft.com/en-us/azure/aks/artifact-streaming) in Azure Kubernetes Service (AKS) enables efficient streaming of container images and other artifacts directly from Azure Container Registry (ACR) to AKS clusters. This approach minimizes storage overhead and improves image pull times by streaming images on-demand rather than pulling them fully at once. It enhances deployment speed and scalability in cloud-native environments by reducing resource usage and optimizing image distribution across clusters.

### AWS snapshotter

The [AWS Snapshotter](https://aws.amazon.com/de/blogs/aws/aws-fargate-enables-faster-container-startup-using-seekable-oci/) leverages Seekable OCI (SOCI) to accelerate container startup times on AWS Fargate by enabling on-demand streaming of container image layers. This approach reduces the need to fully download container images before execution, allowing for faster initialization and more efficient resource usage. SOCI enhances performance, especially for large images, by allowing containers to start quickly while retrieving only the required image data as needed.

## Image Libraries

### go-containerregistry

<a href="https://github.com/google/go-containerregistry">go-containerregistry</a> - "Go library for working with container registries."

### image

<a href="https://github.com/containers/image">image</a> - "A set of Go libraries aimed at working in various way with containers' images and container image registries (pull, push, inspect w/o pulling, translate from one image format to another)."

skopeo is backed by this library.

### storage

<a href="https://github.com/containers/storage">storage</a> - "A Go library which aims to provide methods for storing filesystem layers, container images, and containers" (with a CLI included).
