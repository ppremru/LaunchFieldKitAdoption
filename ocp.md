# OpenShift Container Platform (OCP)

**UNDER CONSTRUCTION**

## User Profiles

* Integrators
* Field Ops
* Software Developers

## Key References

* [OpenShift Documentation](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19)
* [Self-managed for Administrators](https://docs.redhat.com/en/essentials/openshift/self-managed-for-administrators)
* [Red Hat OpenShift Cheat Sheet](https://developers.redhat.com/cheat-sheets/red-hat-openshift-container-platform)
* [OpenShift Container Platform 4.x Tested Integrations](https://access.redhat.com/articles/4128421)

## Enablement

### RHLS Core Recommendations (two paths: operations and development)

All profiles:

* [Take a free skills assessment to see where you should start training](https://skills.ole.redhat.com/en)
* [**Containers, Kubernetes and Red Hat OpenShift Technical Overview - Free course**](https://www.redhat.com/en/services/training/do080-deploying-containerized-applications-technical-overview)
* [*Stretch Goals* - Red Hat OpenShift skill paths](https://www.redhat.com/en/resources/openshift-skill-paths-datasheet)

Operations profile:  

* [Red Hat OpenShift Administration I: Operating a Production Cluster (DO180)](https://www.redhat.com/en/services/training/red-hat-openshift-administration-i-operating-a-production-cluster)
* [Red Hat OpenShift Administration II: Configuring a Production Cluster (DO280)](https://www.redhat.com/en/services/training/red-hat-openshift-administration-ii-configuring-a-production-cluster)

Developer Profile:  

* [Red Hat OpenShift Development I: Introduction to Containers with Podman (DO188)](https://www.redhat.com/en/services/training/do188-red-hat-open-shift-development-introduction-containers-with-podman)
* [Red Hat Certified Specialist in Containers exam (EX188)](https://www.redhat.com/en/services/training/ex188-red-hat-certified-specialist-containers-exam)
* [Red Hat OpenShift Developer II: Building and Deploying Cloud-native Applications (DO288)](https://www.redhat.com/en/services/training/red-hat-openshift-developer-ii-building-and-deploying-cloud-native-applications)
* [Red Hat Certified OpenShift Application Developer exam (EX288)](https://www.redhat.com/en/services/training/ex288-red-hat-certified-openshift-application-developer-exam)

### Independent Learning

**UNDER CONSTRUCTION**

#### Crawl - Pre OCP

Awareness of concepts such as containers, container registries, and ???.  These are useful concepts for profiles in operations and development.

| Recommended Resources | Notes |
| :-------------------- | :---- |
| [Understanding Containers](https://www.redhat.com/en/topics/containers) | Containers - Exploration of concepts  |
| [What is Podman?](https://www.redhat.com/en/topics/containers/what-is-podman) | Containers - Use podman to build, manage, and run images |
| [What is a Container Registry?](https://www.redhat.com/en/topics/cloud-native-apps/what-is-a-container-registry) | Containers - Registry|
| [What is Buildah?](https://www.redhat.com/en/topics/containers/what-is-buildah) | Containers - Build tool |
| [Overview: Container Fundamentals](https://developers.redhat.com/learn/rhel/container-fundamentals) | Containers - Lab |
| [Podman in Action](https://developers.redhat.com/e-books/podman-action) | eBook - Podman |
| [3 advantages of Podman vs. Docker](https://developers.redhat.com/articles/2023/08/03/3-advantages-docker-podman)| Podman |

#### Crawl - OCP

Awareness of container orchestration. Focus on foundational concepts, initial access, basic CLI usage, and a simple "Hello World" deployment.  A bit of start-at-the-end approach, use OCP, not focused on installation.

| Recommended Resources | Notes |
| :-------------------- | :---- |
| [What is container orchestration?](https://www.redhat.com/en/topics/containers/what-is-container-orchestration#what-is-container-orchestration) | Intro |
| [What is Kubernetes?](https://www.redhat.com/en/topics/containers/what-is-kubernetes) | K8 - Intro |
| [Red Hat OpenShift vs. Kubernetes](https://www.redhat.com/en/technologies/cloud-computing/openshift/red-hat-openshift-kubernetes) | K8 v OCP |
| [Interactive labs for Red Hat OpenShift](https://www.redhat.com/en/interactive-labs/openshift) | OCP - Hands on Lab - Login, Build and Deploy Application |
| [Overview: Foundations of OpenShift](https://developers.redhat.com/learn/openshift/foundations-openshift) | OCP - Hands on Lab - Login, Build and Deploy Application |
| [Kubernetes: A Pod’s Life](https://www.redhat.com/en/blog/kubernetes-pods-life) | Concept of PODS |

#### Walk

These are useful concepts for profiles in operations and development.

| Recommended Resources | Notes |
| :---- | :---- |
| [DevOps with OpenShift Pipelines and OpenShift GitOps](https://developers.redhat.com/articles/2024/09/17/devops-openshift-pipelines-gitops) | DevOps, CI/CD, GitOps |
| [What are Red Hat OpenShift Operators?](https://www.redhat.com/en/technologies/cloud-computing/openshift/what-are-openshift-operators) | Intro to Operators|
| [Get started with Argo CD and GitOps with Red Hat OpenShift](https://www.redhat.com/en/interactive-labs/openshift) |GitOps - Hands on  Lab |
| [Red Hat OpenShift GitOps](https://www.redhat.com/en/technologies/cloud-computing/openshift/gitops) | GitOps - Operator |
| [What is Argo CD?](https://www.redhat.com/en/topics/devops/what-is-argocd) | GitOps -  ArgoCD |
| [What is Helm?](https://www.redhat.com/en/topics/devops/what-is-helm#overview) | GitOps - Helm |
| [What is CI/CD?](https://www.redhat.com/en/topics/devops/what-is-ci-cd#why-is-ci/cd-important) | CI/CD - Pipelines |


#### Run

Dive into OCP administration - there are no short cuts, research, experiment, rinse and repeat.

| Recommended Resources | Notes |
| :---- | :---- |
| [5 steps to getting started with Red Hat OpenShift](https://www.redhat.com/en/resources/5-steps-getting-started-with-openshift-checklist) | Sys admin - Intro to Installation |
| [Installation overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/installation_overview/index)| Sys admin - Installation Documentation |
| [Day 2 operations for OpenShift Container Platform](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/postinstallation_configuration/index)| Sys admin - Networking, Machine Configuration |
| [Security and compliance](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/security_and_compliance/index) | Sys admin - Compliance |
| [Observability overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/observability_overview/index) | Sys admin - Logging |
| [Kubernetes Patterns, 2nd Edition](https://developers.redhat.com/e-books/kubernetes-patterns) | eBook - Building and Running containers  |
| [GitOps Cookbook: Kubernetes Automation in Practice](https://developers.redhat.com/e-books/gitops-cookbook?extIdCarryOver=true&intcmp=7015Y000003t7aWQAQ&percmp=RHCTG0250000438148&sc_cid=701f2000000tyN6AAI) | eBook -  Git-based workflow|
| [The Path to GitOps](https://developers.redhat.com/e-books/path-gitops) | eBook - Helm, Kustomize, ArgoCD |
| [Getting GitOps: A practical platform with OpenShift, Argo CD, and Tekton](https://developers.redhat.com/e-books/getting-gitops-practical-platform-openshift-argo-cd-and-tekton) | eBook - ArgoCD Tekton |
| [DevOps Culture and Practice with OpenShift](https://developers.redhat.com/e-books/devops-culture-and-practice-openshift) | eBook - DevOps Culture |
| [5 Ways developers benefit from OpenShift](https://developers.redhat.com/e-books/5-ways-developers-benefit-red-hat-openshift)   | eBook - Developer |

#### Optimizing

| Recommended Resources | Notes |
| :---- | :---- |
| [Red Hat OpenShift Service Mesh](https://www.redhat.com/en/technologies/cloud-computing/openshift/what-is-openshift-service-mesh) | Servicemesh - Overview, Links to eBooks, Documentation |

## Tips

The questions below don't always have a quick answer; they often require hands-on experimentation and teamwork to set up and troubleshoot. Refer to the crawl and walk section of recommendations for both ansible and foundations.  Refer to the crawl and walk section of recommendations for both *OCP* and *foundations*.

### Deploy an OCP Cluster

Lean into the user documentation and experiment.

* [Installation overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/installation_overview/index)
* [Disconnected Environment](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/disconnected_environments/index)
* [Updating clusters](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/updating_clusters/index)

### Perform advanced maintenance on an OCP Cluster

* Research and experiment with:
  * OCP Operators
  * GitOps Workflows, Helm charts, ArgoCD
