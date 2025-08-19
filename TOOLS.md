# Container Development Tools

Here you can find information about some useful container development tools.

## Container Development

| Feature / Tool          | Docker Desktop                                         | OrbStack                     | Colima                                     | Rancher Desktop                   | Podman Desktop                           |
|-------------------------|--------------------------------------------------------|------------------------------|--------------------------------------------|-----------------------------------|------------------------------------------|
| **Platform Support**    | macOS, Windows, Linux                                  | macOS                        | macOS, Linux                               | macOS, Windows, Linux (beta)      | macOS, Windows, Linux                    |
| **Container Engine**    | Docker (dockerd)                                       | Docker-compatible            | Docker (via containerd)                    | containerd or dockerd             | Podman (daemonless)                      |
| **Kubernetes Support**  | Built-in                                               | Built-in                     | Yes                                        | Built-in                          | Partial (via Minikube etc.)              |
| **GUI Dashboard**       | Yes                                                    | Yes                          | No                                         | Yes                               | Yes                                      |
| **Resource Efficiency** | Medium                                                 | High                         | High                                       | Medium                            | High                                     |
| **Open Source**         | Partial (Proprietary)                                  | No (Closed Source)           | Yes                                        | Yes                               | Yes                                      |
| **Licensing**           | Free (limits apply), Paid                              | Paid (free trial)            | Free                                       | Free                              | Free                                     |
| **Notable Highlights**  | Industry standard, feature-rich                        | Fast and light, VM-based     | CLI-focused, simple setup                  | Kubernetes-first, Docker alt      | Dev-focused, OCI-native                  |
| **Official Website**    | [Link](https://www.docker.com/products/docker-desktop) | [Link](https://orbstack.dev) | [Link](https://github.com/abiosoft/colima) | [Link](https://rancherdesktop.io) | [Link](https://podman.io/podman-desktop) |

### Docker for Desktop

[Docker for Desktop](https://www.docker.com/products/docker-desktop) is a popular, full-featured Docker container runtime and GUI for macOS and Windows. It includes Docker Engine, Docker Compose, Kubernetes, and a user-friendly dashboard.

### Orbstack

[Orbstack](https://orbstack.dev) is a fast, lightweight alternative to Docker Desktop for macOS that supports containers, Linux VMs, and Kubernetes with low resource usage.

### Colima

[Colima](https://github.com/abiosoft/colima) is an open-source Docker and Kubernetes runtime for macOS and Linux, built on Lima and QEMU. Known for being minimal, fast, and compatible with Docker CLI.

### Rancher For Desktop

[Rancher For Desktop](https://rancherdesktop.io) is a Kubernetes and container management GUI tool that uses containerd or dockerd, offering a desktop-based way to manage local clusters.

### Podman Desktop

[Podman Desktop](https://podman.io/podman-desktop) is for Podman (daemonless container engine), offering container lifecycle management, Kubernetes YAML generation, and tight Linux support.

## Editor

### NeoVIM

[Neovim](https://neovim.io) is an extensible text editor that serves as an improved version of Vim, aiming to enhance its functionality while maintaining compatibility with Vim's features.

Nvim offers modern features like better extensibility, an asynchronous plugin architecture, and improved performance, making it ideal for both developers and power users. Neovim allows for extensive customization and is highly popular for programming tasks, with strong community support and a growing ecosystem of plugins. It runs on multiple platforms and provides a powerful, keyboard-centric user interface that allows for efficient text editing.

### VSCode

[Visual Studio Code (VS Code)](https://code.visualstudio.com) is a lightweight code editor developed by Microsoft.

VSCode supports a wide range of programming languages and offers powerful features like syntax highlighting, debugging, IntelliSense code completion, and Git integration. VS Code is highly customizable through extensions, enabling users to enhance its functionality with tools for various programming languages, frameworks, and workflows. It is available on Windows, macOS, and Linux, making it a popular choice for developers seeking a fast, efficient, and feature-rich coding environment.

* [Visual Studio Code Kubernetes Tools](https://github.com/vscode-kubernetes-tools/vscode-kubernetes-tools)
* [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
* [yaml-language-server](https://github.com/redhat-developer/yaml-language-server)
* [Docker in Visual Studio Code](https://code.visualstudio.com/docs/containers/overview)

### Jetbrains

[JetBrains Container Tools](https://www.jetbrains.com/) is a set of tools designed to integrate JetBrains development environments, such as IntelliJ IDEA, with containerized workflows.

These tools streamline the management of Docker containers and Kubernetes clusters directly within the JetBrains IDE, providing developers with an integrated experience for building, testing, and deploying containerized applications. JetBrains Container Tools allow users to work with Docker images, interact with Kubernetes clusters, and easily debug and deploy containerized applications, improving productivity in container-centric development environments.

### Eclipse

[ECLIPSE IDE](https://eclipseide.org) is a widely used, open-source integrated development environment primarily geared toward Java development but also supports other languages through plugins, such as C/C++, Python, and JavaScript. 

Eclipse known for its extensibility, Eclipse provides features like code editing, debugging, testing, and version control integration, making it a versatile tool for software development. It supports a variety of build systems, frameworks, and development tools, and is popular among developers for its robust plugin ecosystem, customization options, and compatibility with major platforms. Eclipse IDE is used for both small-scale projects and large enterprise applications.

The [Eclipse Docker Tooling ](https://marketplace.eclipse.org/content/eclipse-docker-tooling)plugin provides the ability to manage Docker images and containers from within the Eclipse IDE.

## CI

### Github Actions

[GitHub Actions](https://github.com/features/actions) is a CI/CD (Continuous Integration and Continuous Deployment) automation tool integrated into GitHub, enabling developers to automate workflows directly within their repositories.

GH allows users to define custom workflows using YAML configuration files for building, testing, and deploying code. GitHub Actions supports event-driven automation, such as running actions on push, pull request, or other events, and integrates seamlessly with GitHub's version control system. With a wide array of pre-built actions available in the GitHub marketplace, users can easily create complex, reusable pipelines for various tasks, improving efficiency and collaboration in the development lifecycle.

* [self-hosted-runners/](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/about-self-hosted-runners)
* [Actuated](https://actuated.com)

### Dagger

[Dagger](https://dagger.io) is a modern, programmable CI/CD (Continuous Integration and Continuous Deployment) engine designed to automate workflows using code. 

Dagger provides a flexible and portable approach to building, testing, and deploying applications in containers, with pipelines defined through a programming language. Dagger integrates with various version control systems and supports seamless integration across different platforms and services. It aims to simplify automation tasks, reduce redundancy, and offer a scalable solution for complex DevOps workflows, making it easier to define, share, and collaborate on pipelines with a developer-friendly, code-first approach.

### Gitlab

[GitLab](https://about.gitlab.com) - "is a web-based DevOps platform that provides a complete set of tools for software development and lifecycle management. It supports features like version control, continuous integration/continuous deployment (CI/CD), project management, and code review, all in a single application."

GitLab is designed to streamline collaboration across development teams, making it easier to plan, build, test, and deploy software. It is open-source with both free and enterprise versions, offering robust scalability, security features, and integration with various development tools, enabling teams to deliver software more efficiently.

### Gitea

[Gitea](https://about.gitea.com) - "is a lightweight, open-source Git hosting platform that provides version control and collaboration features similar to GitHub or GitLab."

Gitea is designed to be fast, simple, and easy to install, offering a self-hosted solution for managing Git repositories. Gitea provides tools for issue tracking, pull requests, code reviews, and continuous integration, all within a user-friendly interface. Its lightweight nature makes it ideal for small teams or individuals who want to manage their code and projects locally or on their own infrastructure, with strong community support and customization options.

### Jenkins

[Jenkins](https://www.jenkins.io) is an automation server used for continuous integration (CI) and continuous delivery (CD)."

Jenkins helps developers automate the building, testing, and deployment of applications by defining workflows through pipelines. Jenkins supports a wide range of plugins to integrate with version control systems, build tools, testing frameworks, and deployment environments. With its large community and strong ecosystem, Jenkins allows teams to streamline software development processes, reduce manual tasks, and ensure more consistent and reliable releases. It can be easily extended and customized to fit various development workflows.

### Tekton 

[Tekton](https://tekton.dev) - "is a framework for building CI/CD systems, providing Kubernetes-native solutions for defining, managing, and running continuous integration and deployment pipelines."

Tekton allows developers to automate the creation of pipelines and workflows within Kubernetes clusters, leveraging Kubernetes resources such as pods and containers. Tekton supports scalability and flexibility, making it easy to integrate with other tools and services. By using reusable components like Tasks and Pipelines, Tekton enables teams to create consistent, portable, and maintainable CI/CD pipelines in cloud-native environments.

## Config Management

### Ansible

[Ansible](https://github.com/ansible/ansible) is an open-source automation tool that simplifies IT infrastructure management, configuration, and application deployment.

Ansible uses a declarative language to describe system configurations and tasks, ensuring consistency across environments. Ansible works by connecting to remote machines over SSH, with no need for agents or special software installed on the managed systems. It is highly extensible, supporting numerous modules for various platforms and applications. Ansible is widely used in DevOps for automating routine tasks, managing cloud infrastructure, and streamlining software deployment processes.

### Terraform

[Terraform](https://www.terraform.io) is an open-source infrastructure as code (IaC) tool developed by HashiCorp that allows users to define, provision, and manage infrastructure using declarative configuration files.

Terraform supports various cloud providers, including AWS, Azure, and Google Cloud, as well as on-premises systems. With Terraform, infrastructure changes are made in a version-controlled manner, enabling reproducible, consistent, and automated provisioning. It integrates with numerous services and enables collaboration in managing infrastructure at scale, making it a popular choice for DevOps and infrastructure teams.

### OpenTofu

[OpenTofu](https://opentofu.org/) is an open-source infrastructure as code (IaC) project that enables the automation of cloud and infrastructure provisioning, similar to Terraform. 

OpenTofu allows developers to define and manage infrastructure with declarative configuration files, making infrastructure reproducible, version-controlled, and easily scalable. OpenTofu focuses on providing transparency, flexibility, and community-driven innovation while supporting multiple cloud platforms and services. Its goal is to offer a fully open-source, collaborative alternative for managing infrastructure, helping users automate their workflows efficiently while ensuring infrastructure consistency.

### Makefile

A [Makefile](https://makefiletutorial.com) is a special file used by the [make](https://www.gnu.org/software/make/) build automation tool to define a set of instructions and dependencies for automating tasks, typically in software development.

Makefile specifies how to build and manage target files (such as executable binaries or libraries) from source files. Makefiles are commonly used for compiling code, managing dependencies, and automating repetitive tasks. They support features such as conditional statements, variable definitions, and rules to control the execution flow. Makefiles improve efficiency and consistency by ensuring tasks are performed correctly and in the right order.

### DevBox

[Devbox](https://www.jetify.com/devbox) - "is a tool for creating isolated, reproducible development environments that can run on any system. Unlike Docker or Nix, Devbox simplifies the process by eliminating the need for complex configuration and language-specific dependencies."

Devbox allows developers to set up environments that are consistent, portable, and easy to use, ensuring compatibility across different machines and minimizing setup issues.

### Task

[Task](https://taskfile.dev) - "is a simple, easy-to-use task runner and build tool designed to streamline automation and reduce complexity compared to traditional tools like GNU Make."

Taskfile provides a straightforward approach to managing tasks and workflows, with an emphasis on simplicity and ease of configuration. Task is suitable for developers who want an intuitive and efficient way to automate repetitive tasks without the overhead of more complicated tools.

### Apache Maven

[Apache Maven](https://maven.apache.org) - "is a powerful build automation tool primarily used for Java projects."

Maven simplifies the process of building, managing, and documenting software by providing a centralized way to manage project dependencies, build configurations, and plugin execution. Maven uses XML-based project configuration files (pom.xml) to define project structure, dependencies, and build processes. It also provides repositories for storing and sharing libraries and other resources. Maven is widely used for its ease of integration, standardized build practices, and ability to manage complex multi-module projects.

### Gradle

[Gradle](https://gradle.org) - "is an open-source build automation tool designed for building, testing, and deploying software, with a focus on performance and flexibility."

Gradle supports multiple programming languages, including Java, Kotlin, Groovy, and others. Gradle uses a Domain-Specific Language (DSL) based on Groovy or Kotlin to define builds, and it integrates with other tools like Maven and Ant. Known for its high performance and ability to handle complex builds, Gradle provides incremental builds and parallel execution to improve speed. It’s commonly used in large-scale projects, including Android development, and supports both small and enterprise-level builds.

## GitOps

[GitOps](https://opengitops.dev) is a modern approach to managing Kubernetes clusters and application delivery by leveraging Git as the single source of truth for declarative infrastructure and application definitions. It uses tools to continuously reconcile the desired state stored in Git with the actual state of the cluster, ensuring consistency and enabling automated, version-controlled updates. This method enhances reliability, traceability, and collaboration in DevOps workflows.

Click here for a more curated list for awesome <a href="https://github.com/weaveworks/awesome-gitops">GitOps resources</a>.

| Tool                  | Description                                                                          | Link                                                                           |
|-----------------------|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| **Argo CD**           | Declarative GitOps CD tool for Kubernetes that syncs and manages app state from Git. | [argoproj.github.io/argo-cd](https://argoproj.github.io/argo-cd)               |
| **Flux**              | CNCF-graduated GitOps tool that automates delivery of Kubernetes workloads.          | [fluxcd.io](https://fluxcd.io)                                                 |
| **Fleet**             | Lightweight GitOps tool from Rancher, designed to manage thousands of clusters.      | [fleet.rancher.io](https://fleet.rancher.io)                                   |
| **Jenkins X**         | Kubernetes-native CI/CD platform using GitOps and Tekton for automation.             | [jenkins-x.io](https://www.jenkins-x.io)                                       |
| **Weave GitOps**      | Enterprise-ready GitOps platform with policy and observability, built on Flux.       | [weave.works/oss/gitops-core](https://www.weave.works/oss/gitops-core)         |
| **Keel**              | Automates Helm and Kubernetes deployments when container images are updated.         | [keel.sh](https://keel.sh)                                                     |
| **Gitkube**           | Simple tool to deploy to Kubernetes by pushing to a Git remote.                      | [github.com/hasura/gitkube](https://github.com/hasura/gitkube)                 |
| **Flagger**           | Progressive delivery operator that automates canaries and A/B rollouts.              | [flagger.app](https://flagger.app)                                             |
| **Pipelines-as-Code** | GitOps-style CI/CD integration for OpenShift Pipelines (Tekton).                     | [openshift.dev/pipelines-as-code](https://www.openshift.dev/pipelines-as-code) |

### ArgoCD

<a href="https://argo-cd.readthedocs.io/en/stable/">Argo CD</a> - "is a Kubernetes-native GitOps continuous delivery tool that automates the deployment and lifecycle management of applications."

ArgoCD ensures application definitions, configurations, and environments are declarative and stored in version control, providing traceability and auditability. By continuously reconciling the desired state in Git with the actual state in the cluster, Argo CD makes deployments automated, reliable, and easy to manage.

### FluxCD

<a href="https://github.com/fluxcd/flux2">FluxCD</a> - "is a Kubernetes-native GitOps tool that ensures clusters stay in sync with configuration sources such as Git repositories or OCI artifacts."

Flux automates deployment updates by applying changes as new code becomes available. Designed for continuous delivery, Flux simplifies managing and versioning infrastructure and application configurations in a declarative manner.

### JenkinsX

[Jenkins X](https://jenkins-x.io) - "is an open-source CI/CD solution designed for Kubernetes and cloud-native applications."

JenkinsX automates the development and deployment of applications by providing a set of tools and workflows tailored for Kubernetes environments. Jenkins X supports GitOps, Kubernetes-native pipelines, and automated promotions through environments such as staging and production. It integrates with popular version control systems like GitHub and GitLab and features a strong focus on automating the entire software delivery pipeline, from code commit to deployment. Jenkins X aims to improve the speed and reliability of software delivery with minimal manual intervention.

### Fleet

[Fleet](https://fleet.rancher.io) is a lightweight GitOps solution built by Rancher (now part of SUSE) designed for massively scalable Kubernetes deployments. It allows you to manage thousands of clusters from a single Git repository. Fleet works by grouping clusters into bundles and applying GitOps workflows to ensure consistency across environments. It’s highly suited for edge, multi-tenant, or enterprise-scale Kubernetes setups.

### Keel

[Keel](https://keel.sh) is an automated deployment tool for Kubernetes that focuses on image update automation. It watches container registries and automatically updates Kubernetes deployments, StatefulSets, or Helm charts when a new image is pushed. Keel is simple to set up and works without requiring a full GitOps setup, making it ideal for small teams or use cases where pushing to Git isn’t preferred.

## SCM

### GIT

[Git](https://git-scm.com) - "is a distributed version control system that allows developers to track changes in source code during software development."

Git enables multiple developers to work on the same project concurrently, manage revisions, and collaborate efficiently. Git is known for its speed, flexibility, and strong branching and merging capabilities. The official Git website (git-scm.com) provides downloads, documentation, and resources to help users understand and use Git effectively. Git is widely adopted by development teams for its powerful tools, scalability, and integration with services like GitHub, GitLab, and Bitbucket.

### Apache Subversion

[Apache Subversion (SVN) ](https://subversion.apache.org)is an open-source version control system used for managing and tracking changes to files and directories over time. 

SVN allows developers to collaborate on projects, maintain history of all changes made, and manage different versions of their work. Subversion is centralized, meaning it uses a central repository where all changes are stored, making it ideal for teams that need to maintain control over their codebase. The official website, subversion.apache.org, provides detailed documentation, installation guides, and resources to help users manage their software development process efficiently using SVN.

* [tortoisesvn](https://tortoisesvn.net/index.de.html)
* [mMigrate from svn to git](https://www.gitkraken.com/blog/migrate-from-svn-to-git-guide)

### Mercurial

[Mercurial (hg)](https://www.mercurial-scm.org) is a distributed source control management (SCM) system designed for efficient handling of large projects. It offers a simple and intuitive command-line interface, fast performance, and strong support for branching and merging. Mercurial is widely used in both open-source and enterprise environments as an alternative to Git.

## Package Management

### Homebrew

<a href="https://brew.sh">Homebrew</a> - "is a popular, open-source package manager for macOS and Linux, simplifying the installation of software and tools via the command line."

Dubbed "The Missing Package Manager," it streamlines the management of libraries, applications, and dependencies, making it easier for developers and users to set up and maintain their systems.

[Bottles](https://docs.brew.sh/Bottles) in Homebrew refer to precompiled binary packages that make software installation faster and easier. Instead of compiling software from source code, Homebrew can install these prebuilt packages (bottles) directly, saving time and system resources. Bottles are available for most commonly used formulae and are automatically preferred over source installations, making Homebrew efficient and user-friendly. These binaries are built on the major macOS and Linux versions to ensure compatibility.

### NIXOS - Package Manager

[NixOS](https://nixos.org) - is a Linux distribution that emphasizes declarative configuration and reproducible builds. 

NIXOS uses the Nix package manager to ensure that systems are defined in a clear and consistent manner through configuration files. NixOS allows for easy rollback of system changes, promotes reliable system management, and simplifies deployment by creating reproducible environments. It's ideal for developers, sysadmins, and those seeking a highly customizable and maintainable Linux setup.

### APT - Advanced Package Tool

[APT (Advanced Package Tool)](https://manpages.debian.org/bookworm/apt/apt.8.de.html) - "is a package management system used by Debian and its derivatives (like Ubuntu) to handle software installation, upgrades, and removal."

APT simplifies the process of managing packages by automatically resolving dependencies, ensuring that software libraries and components required for installation are also handled. It provides a command-line interface with commands like apt-get and apt-cache for installing, updating, and managing packages, offering an efficient and reliable way to manage software on Debian-based systems.

* [APT History](https://en.wikipedia.org/wiki/APT_(software))

### APK

[APK (Alpine Package Keeper)](https://docs.alpinelinux.org/user-handbook/0.1a/Working/apk.html) -  "is the package manager used by the Alpine Linux distribution"

APK is designed to manage system packages, allowing users to install, upgrade, and remove software efficiently. APK simplifies package management by using a lightweight format, ensuring fast installation and low resource consumption. It is the primary method for installing additional software on Alpine Linux, and is part of the apk-tools package, providing users with a reliable tool for maintaining their system's software.

### Helm

[Helm](https://helm.sh) - "is a package manager for Kubernetes that simplifies the deployment and management of applications and services on Kubernetes clusters."

Helm uses Helm charts, which are predefined templates containing all the necessary resources, configurations, and dependencies for deploying an application. Helm allows for easy installation, versioning, and management of Kubernetes applications, making it simpler to handle complex deployments and rollbacks. By using Helm, teams can ensure consistent, repeatable, and scalable deployments within Kubernetes environments.

### Kustomize

[Kustomize](https://kustomize.io) - "is a tool for managing Kubernetes configurations by enabling customization of YAML files without altering the original source code."

Kustomize allows users to create reusable and maintainable Kubernetes manifests by applying "overlays" on top of base configurations. This helps in managing different environments (e.g., development, staging, production) with minimal duplication. Kustomize integrates directly into kubectl, making it a seamless tool for Kubernetes-native configuration management. It simplifies the management of configurations while keeping them consistent across different deployments.

### PIP

[Pip](https://pip.pypa.io/en/stable/getting-started/) - "is the package installer for Python, enabling users to easily install and manage Python libraries and packages."

PIP allows developers to download packages from the Python Package Index (PyPI) and install them into their Python environment. Pip helps manage dependencies, ensuring that the necessary packages for a project are installed and up-to-date. It is an essential tool for Python developers to manage their software environments.

* [PIP](https://pypi.org/project/pip/)

### NPM

[NPM (Node Package Manager)](https://www.npmjs.com) - "is the default package manager for the JavaScript runtime environment Node.js."

NPM helps developers manage and distribute reusable code packages (modules), enabling the installation, sharing, and versioning of libraries and dependencies within JavaScript and Node.js projects. The npm website (npmjs.com) provides access to a vast registry of open-source packages, as well as tools for managing project dependencies, running scripts, and publishing packages. It is a key component of the modern JavaScript ecosystem, widely used for both front-end and back-end development.

### Java Archiv

[JAR](https://docs.oracle.com/en/java/javase/17/docs/specs/jar/jar.html) file is a file format based on the popular ZIP file format and is used for aggregating many files into one. A JAR file is essentially a zip file that contains an optional META-INF directory. A JAR file can be created by the command-line jar tool, or by using the java.util.jar API in the Java platform. There is no restriction on the name of a JAR file, it can be any legal file name on a particular platform.

* [WAR](https://en.wikipedia.org/wiki/WAR_(file_format))
* [EAR](https://en.wikipedia.org/wiki/EAR_(file_format))

## Terminals

### ⭐ Kitty

<a href="https://sw.kovidgoyal.net/kitty">Kitty</a> - The fast, feature-rich, GPU based terminal emulator.

* [https://sw.kovidgoyal.net/kitty/graphics-protocol/](Terminal graphics protocol)

### wezterm

<a href="https://wezfurlong.org/wezterm/">wezterm</a>
 - "is  a fast, modern, and feature-rich terminal emulator and multiplexer, written in Rust for cross-platform support."
 
Wezterm offers GPU-accelerated rendering, flexible configuration, and built-in support for features like multiplexing and tabs. Designed for speed and usability, WezTerm works seamlessly on Windows, macOS, and Linux, catering to developers who need a reliable and customizable terminal experience.

### ⭐ iTerm2

<a href="https://iterm2.com">iTerm2</a> - "is a feature-rich terminal emulator for macOS, serving as a modern replacement for the default Terminal app and the successor to iTerm."

iTerm2 is designed for macOS 10.14 or newer, it enhances the terminal experience with advanced features such as split panes, search, autocomplete, and session restoration. iTerm2 is tailored for developers who want a powerful and customizable terminal environment.

### Ghostty

<a href="https://ghostty.org">ghostty</a> - " is a high-performance, cross-platform terminal emulator that leverages GPU acceleration for fast rendering and uses platform-native UI for a seamless experience."

Ghostty is designed for modern developers, it combines speed, advanced features, and intuitive usability, making it a robust choice for diverse development workflows.

### Apple Terminal

<a href="https://support.apple.com/de-de/guide/terminal/welcome/mac">Apple Terminal</a> - "is a powerful command-line interface included with macOS, allowing users to control their computer and execute tasks using text-based commands."

Terminal provides access to Unix-based tools and scripts, enabling advanced customization, system management, and automation. Terminal supports macOS-native features while being a gateway for developers and power users to interact with the operating system at a deeper level.

### Xterm.js

[Xterm.js](https://xtermjs.org) - is an open-source JavaScript library for embedding terminal functionality into web applications. 

Xterm.js provides a highly configurable and feature-rich terminal emulator, supporting features like Unicode, color, mouse events, and customizable themes. Xterm.js is designed to work seamlessly in modern browsers, allowing developers to integrate terminal interfaces within web applications without requiring external plugins. It is widely used in cloud-based environments, code editors, and other web-based tools where terminal interaction is needed.

* [xterm history](https://invisible-island.net/xterm/)

### ⭐ tmux

[tmux](https://github.com/tmux/tmux/wiki) - is a terminal multiplexer that allows users to run multiple terminal sessions within a single window. 

Tmux includes detailed guides on installation, configuration, and usage of tmux, as well as advanced features like session management, window splitting, and custom key bindings. The wiki also offers troubleshooting tips, example workflows, and community contributions to help users leverage tmux for increased productivity in terminal-based environments. It's a valuable resource for both beginners and advanced users looking to optimize their terminal experience.

### tmate

[Tmate](https://tmate.io) - "is a web-based platform that provides instant, secure SSH access to terminal sessions."

Tmate allows users to share terminal sessions in real time, enabling collaborative debugging, pair programming, or training. Tmate generates a unique URL that can be shared with others to grant them access to the terminal session, without requiring any setup or special configurations. It is built on top of tmux, offering a simple way to collaborate on projects or remotely support users, making it a useful tool for teams, educators, and system administrators.

### ⭐ screen

The [GNU Screen](https://www.gnu.org/software/screen/manual/screen.html) - "is a terminal multiplexer that allows users to manage multiple terminal sessions within a single window."

Screen enables features such as session persistence, where terminal sessions continue running in the background even after disconnection, and the ability to split windows for multitasking. It is especially useful for remote work over SSH, allowing users to resume sessions and manage multiple tasks efficiently. The manual includes installation instructions, usage examples, and advanced features to help users maximize productivity with Screen.

## Shells

### sh

[Bourne shell /bin/sh](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/sh.html) is the standard shell binary on Unix-like systems — it’s the command-line interpreter used for executing shell scripts and interactive commands.

### bash

[Oh My Bash ](https://github.com/ohmybash/oh-my-bash)is a framework for managing and enhancing the Bash shell environment. It provides a collection of plugins, themes, and customizations to improve the terminal experience, making it more user-friendly and visually appealing. With features like improved prompts, auto-suggestions, syntax highlighting, and customizable configurations, Oh My Bash streamlines workflows and boosts productivity for Bash users.

### zsh

Zsh with [Oh My Zsh](https://ohmyz.sh) is a powerful combination for enhancing the terminal experience. Zsh is a highly customizable shell with features like advanced tab completion, globbing, and improved scripting capabilities. Oh My Zsh is a framework that adds even more functionality, providing a wide range of plugins, themes, and configuration options to make your terminal more productive, visually appealing, and efficient. It streamlines workflows, improves usability, and is popular among developers for its flexibility and ease of use.

### fish

[Fish](https://fishshell.com) (short for Friendly Interactive SHell) is a user-friendly, interactive shell designed to be easy to use out of the box. It focuses on interactive use, readability, and sensible defaults rather than strict POSIX compliance.

## Documentation As Code

Code and documentation, created and maintained equally. developers love it, as it’s effective and takes the pain out of documentation.

### Docs as Code

[Docs as Code](https://docsascode.org) is an approach to documentation where documentation is treated like code, using similar processes, tools, and workflows.

It emphasizes version control, collaboration, and automation to create, maintain, and update documentation in a systematic, reproducible manner. This approach enables teams to use the same infrastructure they use for software development (e.g., Git, CI/CD pipelines) for their documentation. Docs as Code promotes quality, consistency, and efficiency in producing technical and product documentation. The Docs as Code website provides guidelines, best practices, and resources for adopting this methodology.

### Arc42

[arc42](https://arc42.org) -  "is a framework for documenting software and system architectures."

Arc42 provides a structured approach to capturing and communicating architectural decisions, designs, and rationale. The framework consists of a set of templates and guidelines to ensure comprehensive, consistent documentation. arc42 covers all aspects of software architecture, including system components, deployment, quality attributes, and technical constraints, making it valuable for teams looking to maintain clear and organized architecture documentation throughout a project's lifecycle.

### ADR

"Documenting Architecture Decisions" emphasizes the importance of capturing and documenting architectural decisions made during software development. It suggests that these decisions should be clearly articulated, concise, and accessible to ensure that they are understood and can be referenced later. The post encourages using simple, lightweight formats to document architecture decisions and highlights the value of preserving rationale behind decisions, which helps future development teams understand and maintain the system.

* [Documenting architecture decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)
* [Architectural Decision Record](https://adr.github.io)
* [adr-tools](https://github.com/npryce/adr-tools)
* [Asciidoc tool ADR](https://unexist.dev/documentation/myself/2024/10/25/decision-records.html)
* [DeciCollab](https://github.com/rossbachp/DeciCollab)

### RFC

* A [Request for Comments (RFC)](https://en.wikipedia.org/wiki/Request_for_Comments) is a publication in a series from the principal technical development and standards-setting bodies for the Internet, most prominently the Internet Engineering Task Force (IETF).
* [Transparent Cross-Team Decision Making using RFCs](https://patterns.innersourcecommons.org/p/transparent-cross-team-decision-making-using-rfcs)

### Presenterm

[Presenterm](https://mfontanini.github.io/presenterm/) - "is a tool that allows you to create and deliver presentations directly from your terminal using markdown format."

Presenterm supports images, animated GIFs, customizable themes, and code highlighting to enhance presentations. Presenterm also enables exporting presentations into PDF format and includes various other features for a streamlined, command-line-driven presentation experience. It's an ideal choice for developers and tech enthusiasts who prefer working in a terminal environment.

### Marp

[Marp](https://marp.app) (Markdown Presentation Ecosystem) is an open-source tool that allows you to create slide decks from Markdown files easily. It’s designed for developers and writers who prefer writing presentations in Markdown syntax instead of complex slide-building software.

Key features of Marp include the ability to author slides using simple Markdown syntax, allowing you to create headings, lists, images, and code blocks with ease. It supports custom themes and styling through CSS, enabling you to personalize the look of your presentations. Marp offers multiple export options, including HTML, PDF, and PowerPoint formats. It also provides a live preview feature so you can see your slides rendered instantly as you edit. Additionally, Marp integrates seamlessly as a CLI tool, a VS Code extension, and a web application, making it flexible for different workflows.

The [Marp CLI](https://github.com/marp-team/marp-cli) is a command-line interface for converting Marp Markdown files into various formats such as HTML, PDF, PowerPoint, and images. It also supports live preview and server modes.

[Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) is an extension that enhances Visual Studio Code with Marp-specific features, allowing you to write and preview slide decks directly within the editor.

### Reveal.js

[Reveal.js](https://revealjs.com) - "is an open-source HTML presentation framework that allows users to create interactive and visually appealing slide decks."

RevealJS supports a range of features such as slide transitions, markdown support, themes, and even live code editing, making it ideal for developers and presenters. Reveal.js offers full customization with the ability to integrate plugins, animations, and multimedia content. It's browser-based and can be easily shared, making it a versatile tool for creating presentations without relying on proprietary software.

### Hugo

[Hugo](https://gohugo.io) - "is a fast, open-source static site generator designed for building websites and blogs. "

Hugo allows developers to create content-driven sites using simple markdown files, and it offers a range of features, including templates, content management, and easy deployment. Known for its speed and flexibility, Hugo can generate sites in seconds and supports various content formats. It is highly customizable and works well with version control and modern web development workflows, making it a popular choice for developers looking to build fast, scalable static websites.

* [HugoMods](https://hugomods.com)
  * Third party Hugo modules and tools for building fast, modular, modern themes and static websites.
* [Hugo Docker Images](https://docker.hugomods.com)
* [Build an amazing docs site](https://getdoks.org)
* [Docsy Theme - for creating great technical documentation sites](https://www.docsy.dev)

### Netlify

[Netlify](https://www.netlify.com) -  "is a platform that simplifies the development, deployment, and hosting of modern web applications."

Netlify offers a seamless workflow for front-end developers, integrating continuous deployment, serverless functions, and content delivery through a global CDN. Netlify supports static sites, dynamic applications, and integrates with popular frameworks like React, Gatsby, and Hugo. With features like form handling, A/B testing, and serverless backend integration, Netlify enables fast and efficient website and application management, making it a popular choice for developers aiming for quick deployment and scalability.

### asciinema

[Asciinema](https://asciinema.org) - "is an open-source platform that allows users to record and share terminal sessions in a lightweight, text-based format."

Asciinema enables developers and users to capture, replay, and share interactive shell sessions, making it easier to demonstrate commands, workflows, or troubleshooting processes. Asciinema recordings are highly compressed and can be embedded into websites, shared via URLs, or stored on the platform for future reference. The tool is popular for creating tutorials, guides, and showcasing technical processes efficiently.

### Formats and Diagrams

* [The Markdown Guide](https://www.markdownguide.org)
* [Asciidoc](https://asciidoc.org)
* [Yaml](https://yaml.org/spec/)
  * [yq](https://mikefarah.gitbook.io/yq) is a lightweight and portable command-line YAML processor.
* [Toml](https://toml.io/en/)
* [Json](https://www.json.org/json-en.html)
  * [jq](https://jqlang.github.io/jq/) is a lightweight and flexible command-line JSON processor.
* [Mermaid](https://mermaid.js.org)
  * [Kubernetes Diagram Guide](https://kubernetes.io/docs/contribute/style/diagram-guide/)
  * [K8s docs mermaid](https://github.com/chrismetz09/K8s-docs-mermaid)
* [plantuml](https://plantuml.com)
  * [Kubernetes-PlantUML](https://github.com/dcasati/kubernetes-PlantUML)
