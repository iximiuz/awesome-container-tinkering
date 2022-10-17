# Tools To Deal With Container Images

## Base images

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

### 👨‍ bake

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

<a href="https://github.com/ko-build/ko">ko</a> - "Build and deploy Go applications on Kubernetes."

### Jib

<a href="https://github.com/GoogleContainerTools/jib">Jib</a> - "Build container images for your Java applications."

### 👨‍🔬 kim

<a href="https://github.com/rancher/kim">kim</a> - "The Kubernetes Image Manager."

The tool consists of a builder backend (BuildKit daemon bound to the kubelet's underlying containerd socket) and a server-side agent (both deployed as one DaemonSet), and the _kim_ CLI (that talks to the agent) with a classic Docker-like UX for image management (push, pull, etc).

### ⭐ Packer

<a href="https://github.com/hashicorp/packer">Packer</a> - "A tool for creating identical machine images for multiple platforms from a single source configuration."

Packer is primarily focused on producing virtual machine images but it also allows building Docker, LXC, and LXD images using a similar to VM-provisioning procedure (read, by putting shell commands into a HCL file).

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


## Image Inspection

### dive

<a href="https://github.com/wagoodman/dive">dive</a> - "A tool for exploring each layer in a docker image."

### container-diff

<a href="https://github.com/GoogleContainerTools/container-diff">container-diff</a> - "Diff your Docker containers."

### explore (SaaS)

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

### OCI Registry Artifact Storage (ORAS)

<a href="https://oras.land/">ORAS</a> - "Push and pull OCI Artifacts to and from OCI Registries."

Since the invention of OCI registries, people have been (ab)using them to store non-container things (Helm charts, OPA policies, even video files can be stored this way). The modern registries are evolving as generic artifact stores, and the ORAS project provides a way to push and pull OCI Artifacts (read _arbitrary files_) to and from OCI Registries. The project consists of a CLI (<a href="https://github.com/oras-project/oras">_oras_</a>) and libraries (<a href="https://github.com/oras-project/oras-go">Go</a>, <a href="https://github.com/oras-project/oras-py">Python</a>).


## Libraries

### go-containerregistry

<a href="https://github.com/google/go-containerregistry">go-containerregistry</a> - "Go library for working with container registries."

### image

<a href="https://github.com/containers/image">image</a> - "A set of Go libraries aimed at working in various way with containers' images and container image registries (pull, push, inspect w/o pulling, translate from one image format to another)."

skopeo is backed by this library.

### storage

<a href="https://github.com/containers/storage">storage</a> - "A Go library which aims to provide methods for storing filesystem layers, container images, and containers" (with a CLI included).
