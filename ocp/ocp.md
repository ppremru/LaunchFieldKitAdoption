# Enablement for OpenShift Container Platform (OCP)

**UNDER CONSTRUCTION**

## Approach

* There are several user profiles in the world of OCP.   For example - 
  1. Administration - Installation and Configuration
  2. DevOps - Day Two Operations, including operators and CI/CD
  3. Developers - Working with containerized applications
* All profiles will benefit from basic knowledge of the following:
  * Container Management tools (not specific to OCP)
    * **ContainerFiles**
    * **Buildah**
    * **Podman**
    * **Quay**
  * Container Orchestration
    * Kubernetes
    * OCP
  * OCP
    * Command line **oc**
    * OCP User Interface (admin and dev views) 
    * Build and Deploy applicatons
    * GitOps Operator
      * **ArgoCD**
      * **Helm**
      * Tekton
* Do you have suggestions for the CoP or **tips** to share?
  * [Podman](./tips-podman.md)
  * [Quay](./tips-quay.md)
  * [Helm](./tips-helm.md)
  * [Jenkins](./tips-jenkins.md)
* Do you have **tips** for OCP Admin to share?
  * [OCP - Install](./tips-ocp-install.md)
  * [OCP - Machine Config Operator](./tips-mco.md)

> *Note because of installation requirements, for enablement it is recommended to use existing clusters from the RHLS labs or no cost labs*

## Key References

* [OpenShift Documentation](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19)
* [Self-managed for Administrators](https://docs.redhat.com/en/essentials/openshift/self-managed-for-administrators)
* [Red Hat OpenShift Cheat Sheet](https://developers.redhat.com/cheat-sheets/red-hat-openshift-container-platform)
* [OpenShift Container Platform 4.x Tested Integrations](https://access.redhat.com/articles/4128421)

## RHLS Core Recommendations

While there are two paths for RHLS OCP courses, system admin and developer, these core courses could be useful to all the profiles.

* [Take a free skills assessment to see where you should start training](https://skills.ole.redhat.com/en) :star:
* [**Containers, Kubernetes and Red Hat OpenShift Technical Overview - Free course**](https://www.redhat.com/en/services/training/do080-deploying-containerized-applications-technical-overview) :star:
* [*Stretch Goals* - Red Hat OpenShift skill paths](https://www.redhat.com/en/resources/openshift-skill-paths-datasheet)

### Integrators and Field Operations

* [Red Hat OpenShift Administration I: Operating a Production Cluster (DO180)](https://www.redhat.com/en/services/training/red-hat-openshift-administration-i-operating-a-production-cluster)
* [Red Hat OpenShift Administration II: Configuring a Production Cluster (DO280)](https://www.redhat.com/en/services/training/red-hat-openshift-administration-ii-configuring-a-production-cluster)

### Developers  

* [Red Hat OpenShift Development I: Introduction to Containers with Podman (DO188)](https://www.redhat.com/en/services/training/do188-red-hat-open-shift-development-introduction-containers-with-podman)
* [Red Hat Certified Specialist in Containers exam (EX188)](https://www.redhat.com/en/services/training/ex188-red-hat-certified-specialist-containers-exam)
* [Red Hat OpenShift Developer II: Building and Deploying Cloud-native Applications (DO288)](https://www.redhat.com/en/services/training/red-hat-openshift-developer-ii-building-and-deploying-cloud-native-applications)
* [Red Hat Certified OpenShift Application Developer exam (EX288)](https://www.redhat.com/en/services/training/ex288-red-hat-certified-openshift-application-developer-exam)

## Independent Learning Path Recommendations

|Phase | Recommended Resources | Notes |
| :--  | :-------------------- | :---- |
|Prep  | [Understanding Containers](https://www.redhat.com/en/topics/containers) | Containers - Exploration of concepts  |
|Prep  | [What is Podman?](https://www.redhat.com/en/topics/containers/what-is-podman) | Containers - Use podman to build, manage, and run images |
|Prep  | [What is a Container Registry?](https://www.redhat.com/en/topics/cloud-native-apps/what-is-a-container-registry) | Containers - Registry|
|Prep  | [What is Buildah?](https://www.redhat.com/en/topics/containers/what-is-buildah) | Containers - Build tool |
|Prep  | [Overview: Container Fundamentals](https://developers.redhat.com/learn/rhel/container-fundamentals) | Containers - Lab |
|Prep  | [Podman in Action](https://developers.redhat.com/e-books/podman-action) | eBook - Podman |
|Prep  | [3 advantages of Podman vs. Docker](https://developers.redhat.com/articles/2023/08/03/3-advantages-docker-podman)| Podman |
|Prep  | [What is CI/CD?](https://www.redhat.com/en/topics/devops/what-is-ci-cd#why-is-ci/cd-important) | CI/CD - Pipelines |
|Crawl | [What is container orchestration?](https://www.redhat.com/en/topics/containers/what-is-container-orchestration#what-is-container-orchestration) | Intro |
|Crawl | [What is Kubernetes?](https://www.redhat.com/en/topics/containers/what-is-kubernetes) | K8 - Intro |
|Crawl | [Red Hat OpenShift vs. Kubernetes](https://www.redhat.com/en/technologies/cloud-computing/openshift/red-hat-openshift-kubernetes) | K8 v OCP |
|Crawl | [Interactive labs for Red Hat OpenShift](https://www.redhat.com/en/interactive-labs/openshift) | OCP - Hands on Lab - Login, Build and Deploy Application |
|Crawl | [Overview: Foundations of OpenShift](https://developers.redhat.com/learn/openshift/foundations-openshift) | OCP - Hands on Lab - Login, Build and Deploy Application |
|Crawl | [Kubernetes: A Pod’s Life](https://www.redhat.com/en/blog/kubernetes-pods-life) | Concept of PODS |
|Crawl | [DevOps with OpenShift Pipelines and OpenShift GitOps](https://developers.redhat.com/articles/2024/09/17/devops-openshift-pipelines-gitops) | DevOps, CI/CD, GitOps |
|Crawl | [What are Red Hat OpenShift Operators?](https://www.redhat.com/en/technologies/cloud-computing/openshift/what-are-openshift-operators) | What is an Operator?   Community v Certified (skip SDK)|
|Crawl | [Get started with Argo CD and GitOps with Red Hat OpenShift](https://www.redhat.com/en/interactive-labs/openshift) |GitOps - Hands on  Lab |
|Crawl | [Red Hat OpenShift GitOps](https://www.redhat.com/en/technologies/cloud-computing/openshift/gitops) | GitOps - Operator |
|Crawl | [What is Argo CD?](https://www.redhat.com/en/topics/devops/what-is-argocd) | GitOps -  ArgoCD |
|Crawl | [What is Helm?](https://www.redhat.com/en/topics/devops/what-is-helm#overview) | GitOps - Helm |
|Run   | [5 steps to getting started with Red Hat OpenShift](https://www.redhat.com/en/resources/5-steps-getting-started-with-openshift-checklist) | Sys admin - Intro to Installation |
|Run   | [Installation overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/installation_overview/index)| Sys admin - Installation Documentation |
|Run   | [Day 2 operations for OpenShift Container Platform](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/postinstallation_configuration/index)| Sys admin - Networking, Machine Configuration |
|Run   | [Security and compliance](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/security_and_compliance/index) | Sys admin - Compliance |
|Run   | [Observability overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/observability_overview/index) | Sys admin - Logging |
|Run   | [Kubernetes Patterns, 2nd Edition](https://developers.redhat.com/e-books/kubernetes-patterns) | eBook - Building and Running containers  |
|Run   | [GitOps Cookbook: Kubernetes Automation in Practice](https://developers.redhat.com/e-books/gitops-cookbook?extIdCarryOver=true&intcmp=7015Y000003t7aWQAQ&percmp=RHCTG0250000438148&sc_cid=701f2000000tyN6AAI) | eBook -  Git-based workflow|
|Run   | [The Path to GitOps](https://developers.redhat.com/e-books/path-gitops) | eBook - Helm, Kustomize, ArgoCD |
|Run   | [Getting GitOps: A practical platform with OpenShift, Argo CD, and Tekton](https://developers.redhat.com/e-books/getting-gitops-practical-platform-openshift-argo-cd-and-tekton) | eBook - ArgoCD Tekton |
|Run   | [DevOps Culture and Practice with OpenShift](https://developers.redhat.com/e-books/devops-culture-and-practice-openshift) | eBook - DevOps Culture |
|Run   | [5 Ways developers benefit from OpenShift](https://developers.redhat.com/e-books/5-ways-developers-benefit-red-hat-openshift)   | eBook - Developer |
|Run   | [Red Hat OpenShift Service Mesh](https://www.redhat.com/en/technologies/cloud-computing/openshift/what-is-openshift-service-mesh) | Service Mesh - Overview, Links to eBooks, Documentation |
