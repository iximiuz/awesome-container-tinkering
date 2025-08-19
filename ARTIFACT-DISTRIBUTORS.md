# Artifact Distributors

## CNCF Artifact Hub

[Artifact Hub](https://artifacthub.io) is a web-based platform that facilitates the discovery, installation, and
publication of cloud-native packages and configurations. It serves as a centralized repository for various artifacts,
including Helm charts, Kubernetes operators, and other cloud-native components, streamlining the process of finding and
integrating these resources into projects. In September 2024, Artifact Hub was accepted
as a CNCF (Cloud Native Computing Foundation) incubating project, reflecting its growing importance in the cloud-native ecosystem.
By providing a single experience for consumers, Artifact Hub addresses the challenges of discovering and
utilizing cloud-native artifacts across different projects.

It supports a wide range of artifact types, including:

* Argo templates
* Backstage plugins
* container images
* CoreDNS plugins
* Falco configurations
* Gatekeeper policies
* Helm charts
* Helm plugins
* Inspektor Gadgets
* KCL modules
* KEDA scalers
* Keptn integrations
* Knative client plugins
* KubeArmor policies
* Kubectl plugins (Krew)
* Kubewarden policies
* Kyverno policies
* Meshery designs
* OLM operators
* OpenCost plugins
* Open Policy Agent (OPA) policies
* Radius Recipes
* Tekton tasks, pipelines, and step actions
* Tinkerbell actions

Artifact Hub offers features such as interactive exploration of content like Helm chart schemas and templates,
subscription to package updates and security alerts via email or webhooks, visualization of package security reports,
and inspection of package changelogs.

* [Artifact Tool](https://github.com/artifacthub/hub)

## Docker Hub - Official Images

[Docker Hub](https://hub.docker.com) is a cloud-based platform for hosting and sharing container images.
It provides a centralized repository where developers and organizations can find, store, and manage Docker container images.
Features include Official Images—trusted, pre-configured base images maintained by Docker and its partners-
and community-contributed images. Docker Hub supports automated builds, vulnerability scanning, and integrations
with CI/CD workflows, streamlining the containerization process for software development and deployment.

[Docker Official Images](https://hub.docker.com/u/library) are a curated set of Docker repositories hosted on Docker Hub,
providing a wide range of pre-configured images for popular software applications and operating systems.These images
are maintained collaboratively by Docker, Inc., upstream software authors, and the broader Docker community, ensuring they
are up-to-date, secure, and optimized for use in various environments.  Each Official Image undergoes a thorough review process
to meet Docker's standards for best practices, including clear documentation, minimal size, and efficient design.
This ensures that developers have access to reliable and consistent images for their applications.

The Official Images cover a broad spectrum of use cases, from programming languages and databases to web servers
and operating system bases. Examples include images for Python, Node.js, MySQL, NGINX, and Ubuntu.
These images serve as trusted starting points for building and deploying containerized applications, reducing the need for developers
to create images from scratch. Docker continuously enhances the security and transparency of Official Images by implementing measures
such as automated builds, vulnerability scanning, and providing detailed image metadata. This commitment helps maintain the integrity
and trustworthiness of the images available to the community.

## Bitnami Catalog

[Bitnami](https://bitnami.com), a part of VMware Tanzu, provides a comprehensive catalog of open-source applications packaged
for deployment across various platforms, including local environments, Kubernetes, and major cloud services.
Their offerings are designed to simplify the deployment process for developers and IT teams.

In addition to their free application catalog, Bitnami offers two commercial products tailored to enterprise needs:

* __[Bitnami Premium](https://www.arrow.com/globalecs/na/vendors/bitnami/)__:
  * This enterprise-grade version of the Bitnami Application Catalog offers enhanced security features and support for all application versions maintained by upstream projects.
  * It includes enterprise support for over 500 Bitnami packages, maintenance of all long-term support (LTS) branches
  * Unlimited pulls of containers and Helm charts from Docker Hub
  * Secure software supply chain metadata, such as Software Bills of Material (SBOMs) and build-time vulnerability scans.
* __[VMware Tanzu Application Catalog](https://www.vmware.com/products/app-platform/tanzu-application-catalog)__:
  * This catalog allows organizations to curate a custom set of applications.
  * Customizable selection of open-source software components and applications, continuously maintained and packaged for Kubernetes.
  * Meet specific security, compliance, and operational requirements.

These commercial offerings are designed to provide enterprises with secure, compliant,able open-source applications,
enhancing productivity and operational efficiency.

* [Bitnami Helm Charts](https://github.com/bitnami/charts)
* [Bitnami Container Images](https://github.com/bitnami/containers)

## Chainguard - Secure Images

[Chainguard](https://chainguard.dev) - is a cybersecurity company specializing in supply chain security solutions designed
to make the software lifecycle secure by default. Founded in 2021, the company offers hardened container images
that eliminate Common Vulnerabilities and Exposures (CVEs) from the start, covering a wide range of applications including Java,
Python, Go, Postgres, Redis, and NGINX.Their solutions aim to reduce risk by providing rapidly patched, maintained, and updated
open-source software, enabling businesses to meet compliance standards such as FedRAMP, NIST 800-53, PCI-DSS, SOC2, and
CIS benchmarks without sacrificing developer productivity. Chainguard has garnered trust from leading companies like Snowflake,
Canva, HPE, GitLab, Dell Technologies, and Wiz.

## Github Action Marketplace

[GitHub Actions](https://github.com/features/actions), combined with the GitHub Marketplace, provides a powerful automation platform
for software development workflows. The [marketplace](https://github.com/marketplace?type=actions) offers a wide variety
of pre-built actions that developers can easily integrate into their projects. These actions automate tasks like continuous integration,
testing, deployment, monitoring, and security checks. By using the marketplace, developers can simplify and optimize their workflows,
reducing manual effort and speeding up development cycles. GitHub Actions helps teams to automate repetitive tasks, making software delivery faster and more efficient.

## Linuxserver.io

[LinuxServer.io](https://www.linuxserver.io) is a global collective of enthusiasts dedicated to building and maintaining
a comprehensive suite of Docker images, emphasizing Free and Open Source Software principles. Their primary objective is
to deliver user-friendly, standardized Docker images accompanied by clear documentation.  Their images are constructed
from a uniquely curated base, utilizing s6-overlay to ensure high extensibility and uniformity across applications.
This approach optimizes bandwidth and storage by sharing base layers among images. To keep their images current,
LinuxServer.io has implemented an automated build pipeline that rebuilds images in response to upstream application
or dependency updates. This ensures users have access to the latest versions, with a tagging system that clearly indicates
the application version contained in each build. Comprehensive setup guides are available for all images, accessible on GitHub
or their dedicated documentation space. Additional guides and articles can be found on their blog Support
is provided through their [Discord server](https://discord.gg/YWrKVTn) and [Discourse forum](https://discourse.linuxserver.io/),
fostering a community where both team members and users can assist with any issues.

## Dev Containers

[Dev Containers](https://containers.dev/implementors/spec/) (Development Containers) are portable, consistent, and isolated development environments defined using
container technologies like Docker. They simplify the setup of development environments by providing all necessary
dependencies, tools, and configurations in a predefined container. Typically used with Visual Studio Code and its
Dev Containers extension, they enable developers to work in a consistent environment across different systems.

Dev Containers are defined in a .devcontainer folder containing configuration files like devcontainer.json, Dockerfiles,
or Docker Compose files, allowing integration with IDEs and remote development workflows.

References:

* [Codespaces](https://docs.github.com/en/codespaces)
* [VS Code](https://code.visualstudio.com/docs/devcontainers/create-dev-container)

## "Distroless" Container Images

[Distroless Container Images](https://github.com/GoogleContainerTools/distroless) is an open-source project from GoogleContainerTools
that provides minimal container base images without a traditional package manager or shell. These images are focused solely on the
application’s runtime requirements, enhancing security, performance, and size optimization. Distroless images integrate seamlessly with tools like Docker and Kubernetes, promoting better security practices
in containerized applications.

## Nixery

[Nixery](https://nixery.dev) is an on-demand container image registry that dynamically generates Docker images based
on specified Nix packages. By appending package names to the Nixery URL, users can create custom images containing those packages.
For example, pulling nixery.dev/shell/git/htop provides an image with both Git and htop installed.
This approach streamlines workflows by eliminating the need to pre-build and store numerous container images.
NixOS offers robust support for containerization through native systemd-nspawn containers and integration with Docker.
Native NixOS containers are managed declaratively using the containers directive, allowing users to define container
configurations within the NixOS system configuration. This method ensures consistency and reproducibility across container deployments.

For Docker integration, NixOS provides options to enable and configure the Docker service declaratively.
By setting virtualisation.docker.enable = true; in the NixOS configuration, users can install and manage Docker.
Additional settings, such as specifying the storage driver or enabling rootless mode, can be customized
to suit specific requirements. These tools and configurations empower NixOS users to efficiently manage
containerized environments, leveraging the strengths of the Nix package manager for reproducibility and consistency.

See also other Nix Container usage:

* [Nix with systemd-nspawn](https://nixos.wiki/wiki/NixOS_Containers)
* [Nix Docker Support](https://nixos.wiki/wiki/Docker)

## Operator Hub

[OperatorHub.io](https://operatorhub.io) is a central marketplace for Kubernetes operators, offering a wide range of pre-packaged,
Kubernetes-native applications that extend Kubernetes' capabilities. Operators automate the deployment, management, and
scaling of applications within a Kubernetes cluster. The platform allows developers and operators to discover, install,
and manage operators that integrate with Kubernetes environments, simplifying complex workloads like databases, monitoring tools, and
CI/CD pipelines. OperatorHub.io ensures that operators are certified and ready for use, providing a seamless experience for Kubernetes users.

## Gatekeeper - OPA

[Gatekeeper](https://open-policy-agent.github.io/gatekeeper/website/docs/) is a customizable admission webhook for Kubernetes
that enforces policies executed by the Open Policy Agent (OPA), a policy engine for cloud-native environments. It enables organizations
to automate policy enforcement, ensuring consistency and compliance with governance and best practices. Gatekeeper introduces
features such as an extensible, parameterized policy library, native Kubernetes Custom Resource Definitions (CRDs)
for instantiating and extending policies, mutation support, audit functionality, and external data support.
These capabilities allow administrators to detect and reject non-compliant resources and monitor policy violations effectively.

For a collection of sample policies, you can visit the Gatekeeper policy library.

Artifacts:

* https://open-policy-agent.github.io/gatekeeper/website/
* https://open-policy-agent.github.io/gatekeeper-library/website/

## Kyverno

[Kyverno](https://kyverno.io) is a policy engine designed for Kubernetes that allows users to enforce, validate, mutate, and generate resource configurations
within clusters. Unlike traditional engines requiring custom languages, Kyverno uses Kubernetes-style YAML for defining policies,
making it accessible and easy to integrate into Kubernetes workflows.

Artifacts:

* [Sample Policies](https://kyverno.io/policies)

## Krew Kubectl Plugins

[Krew is a plugin manager ](https://krew.sigs.k8s.io)for Kubernetes kubectl that simplifies the discovery, installation, and management of kubectl plugins. It is maintained by the Kubernetes Special Interest Group (SIG)
CLI. Krew allows users to extend kubectl functionality with additional tools and commands that suit specific workflows,
making Kubernetes management more efficient and customizable.

By leveraging Krew, Kubernetes users can enhance their kubectl experience and tailor their CLI environment to specific
needs without modifying core Kubernetes functionality.

* [Kubectl Plugins](https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/)
* [Kubectl Packages](https://krew.sigs.k8s.io/plugins/)

## Homebrew Bottles

In [Homebrew](https://brew.sh), bottles are pre-compiled binary packages for MacOS and Linux that simplify software
installation by eliminating the need for users to compile source code. These gzipped tarballs contain compiled binaries and
are named to include the formula name, version, target operating system, and rebuild version.

* [Bottle spec](https://docs.brew.sh/Bottles)
* [Bottle Packages](https://github.com/orgs/Homebrew/packages)
* [Homebrew usage of ghcr.io container package service](https://github.com/orgs/Homebrew/discussions/4335)
