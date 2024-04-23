# Image Registries, Artifact Managment And Related Tools

Here you can find information about image registries and general artifact management

## Image registries projects

### Docker Registry

[Registry](https://docs.docker.com/registry/), the open source implementation for storing and distributing container images and other content, has been donated to the CNCF. Registry now goes under the name of Distribution, and the documentation has moved to [distribution project](https://github.com/distribution/distribution).

### ⭐ Registries Reference Project Distribution

<a href="https://github.com/distribution/distribution">distribution</a> - "The Registry is a stateless, highly scalable server side application that stores and lets you distribute container images and other content. The Registry is open-source, under the permissive Apache license." The reference implementation of the holly <a href="https://github.com/opencontainers/distribution-spec">OCI Distribution Specification</a>. Written in Go.

You can find a lot of helpful information at the [Distribution website](https://distribution.github.io/distribution/about/).

## Artifact Managmenent

### Harbor

[harbor](https://goharbor.io) stands as an open-source registry, safeguarding artifacts through policies and role-based access control. It ensures that images undergo scanning to eliminate vulnerabilities and are signed as trusted. As a CNCF Graduated project, Harbor guarantees compliance, performance, and interoperability, enabling you to consistently and securely manage artifacts across cloud-native compute platforms such as Kubernetes and Docker.

### Artifact Hub

[Artifact Hub](https://github.com/artifacthub/hub) serves as a web-based platform facilitating the discovery, installation, and publication of packages and configurations for Cloud Native environments.

The challenge of discovering artifacts for CNCF projects can be daunting. The proliferation of individual artifact hubs for each project not only duplicates efforts but also fragments the user experience for artifact consumers. Artifact Hub addresses this by offering a unified platform accessible to all CNCF projects, streamlining the artifact discovery process and ensuring a cohesive experience for consumers.

You have the option to utilize the official CNCF Artifact Hub at <a href="https://artifacthub.io">artifacthub.io<a> or easily install it using the Artifact Hub Helm Chart, available at <a href="https://artifacthub.io/packages/helm/artifact-hub/artifact-hub">artifact-hub</a>.

### Nexus

[Nexus Repository](https://help.sonatype.com/en/docker-registry.html) supports Docker registries with the Docker repository and OCI Image format for hosted and proxy repositories. You can expose these repositories to the client-side tools directly or as a repository group, which is a repository that merges and exposes the contents of multiple repositories in one convenient URL. The Nexus general artifact management solution for multiple package systems like, Helm Charts, Java/Maven, Go, PyPi, NpM, NuGet, R, RubyGems, Yum or raw artifacts.

### Artifactory

[JFrog Artifactory](https://jfrog.com/de/artifactory/) is the comprehensive solution for storing and overseeing all your artifacts, binaries, packages, files, containers, and components, essential for your software supply chain.

As the central hub for DevOps, JFrog Artifactory seamlessly integrates with your existing tools and processes, enhancing automation, ensuring integrity, and fostering best practices throughout your workflow.

### Chart Museum

[ChartMuseum](https://chartmuseum.com) is an open-source Helm Chart Repository server written in Go (Golang), with support for cloud storage backends, including Google Cloud Storage, Amazon S3, Microsoft Azure Blob Storage, Alibaba Cloud OSS Storage and Openstack Object Storage.

## Cloud registry services

### Docker Hub

[Docker Hub](https://hub.docker.com) is the world's first registry service to create, manage, and deliver your team's container applications. Docker Hub is an online service that includes a registry for Docker images and repositories. The registry is divided into a public and a private part. In the public section, any user can upload their self-created images and make them available to others. Additionally, there are official images, such as those from Linux distributors. In the private section of Docker Hub, users can upload their Docker images, thus easily distributing them, for example, within a company, without them being publicly discoverable.

### GHCR

The [Github Container registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry) stores container images within your organization or personal account, and allows you to associate an image with a repository. You can choose whether to inherit permissions from a repository, or set granular permissions independently of a repository. You can also access public container images anonymously. You can also store other package systems like RubyGems, npm, Maven/Gradle, NUGET artifacts.

The [Homebrew project](https://brew.sh) hosts macOS and Linux bottles](https://docs.brew.sh/Bottles) on its platform :)

### ACR

[Azure Container Registry](https://azure.microsoft.com/products/container-registry) create, store, secure, scan, replicate, and manage container images and artifacts with a fully managed, geo-replicated instance of an OCI distribution. Establish cross-environment connections (e.g., Azure Kubernetes Service and Azure Red Hat OpenShift) and cross-service connections with Azure services such as App Service, Machine Learning, and Batch.

### GCR

The [Google Container Registry](https://cloud.google.com/artifact-registry) is describe as an evolution of Container Registry, Artifact Registry serves as the central interface through which your company can manage container images and language packages (such as Maven and npm). The product is fully integrated into Google Cloud's tools and runtimes and supports native artifact protocols. This allows it to be easily integrated into your CI/CD tools for setting up automated pipelines.

### ECR

[Amazon Elastic Container Registry](https://aws.amazon.com/ecr/) (Amazon ECR) is a fully managed container registry that provides high-performance hosting, allowing you to reliably deploy application images and artifacts anywhere.

### quay.io

The mission of [Quay](https://quay.io) is store your containers securely. Ensure your apps are stored privately, with access that you control. Quay is teamwork optimized, with powerful access controls. It use offen by Red Hat based project like podman or RKT.

## Tools

### skopeo

<a href="https://github.com/containers/skopeo">skopeo</a> - "Work with remote images registries - retrieving information, images, signing content."

### go-containerregistry/crane

<a href="https://github.com/google/go-containerregistry/blob/main/cmd/crane/README.md">crane</a> - "A tool for interacting with remote images and registries. You can try out a web version of crane [here](https://crane.ggcr.dev/)"

### go-containerregistry/krane

<a href="https://github.com/google/go-containerregistry/blob/main/cmd/krane/README.md">krane</a> - "A drop-in replacement for crane that supports common Kubernetes-based workload identity mechanisms."

### regclient

<a href="https://github.com/regclient/regclient">regclient</a> - "Docker and OCI Registry Client in Go and tooling using those libraries."

A client interface to interact with registries: inspect images w/o pulling, list repository's tags, list registry's repositories (if supported), efficiently copy images between repositories, import/export OCI and Docker images, etc. Seems to be written from scratch with just a few dependencies.

### OCI Registry Artifact Storage (ORAS)

<a href="https://oras.land/">ORAS</a> - "Push and pull OCI Artifacts to and from OCI Registries."

Since the invention of OCI registries, people have been (ab)using them to store non-container things (Helm charts, OPA policies, even video files can be stored this way). The modern registries are evolving as generic artifact stores, and the ORAS project provides a way to push and pull OCI Artifacts (read _arbitrary files_) to and from OCI Registries. The project consists of a CLI (<a href="https://github.com/oras-project/oras">_oras_</a>) and libraries (<a href="https://github.com/oras-project/oras-go">Go</a>, <a href="https://github.com/oras-project/oras-py">Python</a>).

### 🧑‍🔬 Docker Hub Tool

<a href="https://github.com/docker/hub-tool">Docker Hub Tool</a> - "Docker Hub experimental CLI tool."

A CLI tool for interacting with the Docker Hub. Get information about your images from the terminal. Docker's experiment to build a Docker Hub CLI tool. The intention of this project is to get user feedback and then to add this functionality to the Docker CLI itself.

### Helm

[Helm](https://helm.sh) stands as a package manager tailored for Kubernetes environments, streamlining the deployment process of applications and services within Kubernetes clusters. Its primary advantage lies in simplifying the orchestration of complex deployments, particularly those that are highly repeatable or needed across diverse scenarios. By providing a structured approach to managing Kubernetes manifests and configurations, Helm empowers users to efficiently package, version, and deploy their applications, fostering consistency and scalability across Kubernetes deployments.

### Trivy

[Trivy](https://trivy.dev) emerges as a leading all-in-one open-source security scanner renowned for its reliability, speed, and user-friendly interface. With Trivy, users can effortlessly uncover vulnerabilities, pinpoint Infrastructure as Code (IaC) misconfigurations, conduct SBOM discovery, perform Cloud scanning, and address Kubernetes security risks, among other critical security tasks. Its popularity stems from its comprehensive feature set and seamless usability, making it a go-to solution for security professionals and developers seeking to fortify their systems against potential threats.

### Grype

[Grype](https://github.com/anchore/grype) stands out as an indispensable vulnerability scanner designed specifically for analyzing container images and filesystems, delivering robust security assessments to identify and mitigate potential risks efficiently. Leveraging its capabilities, users gain actionable insights into vulnerabilities present within their containerized environments, ensuring enhanced security posture and proactive risk management.

### Syft

[Syft](https://github.com/anchore/syft), renowned as a potent SBOM (software bill of materials) tool, excels in providing comprehensive insights into container images and filesystems, empowering users with invaluable visibility into software dependencies and vulnerabilities. Moreover, its seamless integration with the docker CLI as the [sbom-cli-plugin](https://github.com/docker/sbom-cli-plugin) further enhances its accessibility and usability within containerized environments.

### Cosign

[Cosign](https://github.com/sigstore/cosign) presents a comprehensive array of functionalities, ranging from its pioneering 'Keyless signing' feature supported by the Sigstore public good Fulcio certificate authority and Rekor transparency log, to its versatile support for Hardware and KMS signing, seamless integration with cosign-generated encrypted private/public keypairs for signing, robust Container Signing capabilities, secure Verification, and Storage in an OCI registry, alongside flexibility for users to employ their own PKI solutions.

### Notary

The [notary](https://github.com/notaryproject/notary) client and server leverage The [Update Framework (TUF)](https://theupdateframework.io), a robust and secure framework designed to address the challenges of software distribution and updates. Rooted in a strong foundation of security principles, TUF provides a comprehensive solution for ensuring the integrity and authenticity of software packages throughout their lifecycle. By implementing TUF within the notary client and server, users benefit from a proven, standardized approach to securing software distribution, safeguarding against various threats such as tampering, supply chain attacks, and unauthorized modifications.

### OpenPubKey

[OpenPubkey](https://github.com/openpubkey/openpubkey) introduces a groundbreaking protocol that harnesses the capabilities of OpenID Providers (OPs) to establish secure bindings between identities and public keys. By extending OpenID Connect (OIDC), OpenPubkey facilitates the inclusion of user- or workload-generated public keys, empowering identities to authenticate and sign messages or artifacts within the OIDC ecosystem. This innovative approach enhances security and trust, enabling seamless integration of identity management with cryptographic operations, and fostering a more robust foundation for secure communication and transactions. 

In 2023, Docker Inc. announced their adoption of the [OpenPubKey](https://www.docker.com/blog/signing-docker-official-images-using-openpubkey/) project to bolster their Secure Build Pipeline Solution. This strategic move underscores their commitment to enhancing security within their ecosystem by leveraging the capabilities of OpenPubKey to fortify identity management and cryptographic operations throughout the build pipeline.
