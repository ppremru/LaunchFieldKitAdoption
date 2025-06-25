# Day in the life of a Developer

## Summary of Developer Tools

This document summarizes the key tools a developer would leverage daily when containerizing applications and deploying them on OpenShift Container Platform (OCP).

* **VS Code (Visual Studio Code):** As a versatile and extensible integrated development environment (IDE), VS Code serves as the primary code editor. Developers use it for writing, debugging, and testing application code. Its rich ecosystem of extensions supports various languages, Git integration, and direct interaction with container tools and Kubernetes environments, streamlining the development workflow.

* **Git:** Git is the essential version control system for tracking changes in source code. Developers use Git to manage code repositories, collaborate with team members, branch for new features, merge changes, and maintain a history of all modifications. This ensures code integrity, facilitates rollbacks, and enables efficient team development.

* **Podman:** Podman is a daemonless container engine for developing, managing, and running OCI (Open Container Initiative) containers and pods on a Linux system. For OpenShift development, Podman is crucial for locally building container images, testing them, and managing local containers without requiring a Docker daemon. This local environment closely mirrors the OpenShift runtime, enabling faster iteration and debugging.

* **Helm:** Helm is the package manager for Kubernetes. It simplifies the deployment and management of applications on Kubernetes clusters, including OpenShift. Developers use Helm to define, install, and upgrade even the most complex Kubernetes applications as "charts." This allows for consistent and repeatable deployments across different environments (development, staging, production) and easier management of application dependencies and configurations.

* **Jenkins:** Jenkins is a widely adopted open-source automation server for implementing Continuous Integration (CI) and Continuous Delivery (CD) pipelines. In an OpenShift context, Jenkins automates the build, test, and deployment processes. Developers push code to Git, which triggers Jenkins pipelines to build container images (often using Podman within the pipeline), push them to an image registry, and then deploy or update applications on OpenShift using Helm charts. This ensures rapid and reliable delivery of new features.

These tools collectively form a robust ecosystem for modern containerized application development, enabling efficient coding, version control, local container management, simplified deployment, and automated delivery to OpenShift.
