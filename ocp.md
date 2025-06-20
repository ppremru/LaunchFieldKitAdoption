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
| [Podman in Action](https://developers.redhat.com/e-books/podman-action) | eBook - Podman |

#### Crawl - OCP

Awareness of container orchestration. Focus on foundational concepts, initial access, basic CLI usage, and a simple "Hello World" deployment.

| Recommended Resources | Notes |
| :-------------------- | :---- |
| [What is container orchestration?](https://www.redhat.com/en/topics/containers/what-is-container-orchestration#what-is-container-orchestration) | Intro |
| [What is Kubernetes?](https://www.redhat.com/en/topics/containers/what-is-kubernetes) | K8 - Intro |
| [Red Hat OpenShift vs. Kubernetes](https://www.redhat.com/en/technologies/cloud-computing/openshift/red-hat-openshift-kubernetes) | K8 v OCP |
| [Overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/overview/index) | OCP - Documentation |
| [Tutorial](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/tutorials/index) | OCP - Requires access to a test cluster - UI, CLI, simple app deploy|
| [Interactive labs for Red Hat OpenShift](https://www.redhat.com/en/interactive-labs/openshift) | OCP - Hands-on Login, Build and Deploy applications |

#### Walk

Dive deeper into OpenShift objects, various application deployment strategies, basic networking/security, and monitoring.
To effectively learn OpenShift administration, focus on a combination of structured training, hands-on practice, and leveraging available resources.
These are useful concepts for profiles in operations and development.

| Recommended Resources | Notes |
| :---- | :---- |
| todo | deeper dive  - objects |
| [Kubernetes: A Pod’s Life](https://www.redhat.com/en/blog/kubernetes-pods-life) | Concept of PODS |
| [What are Red Hat OpenShift Operators?](https://www.redhat.com/en/technologies/cloud-computing/openshift/what-are-openshift-operators) | Intro to Operators|
| | |

#### Run

Covers advanced deployment patterns, automation with CI/CD, advanced networking/storage, comprehensive monitoring and security, and cost management.  The Run section is leaning into installation - there are no short cuts, research documentation and experiment.

| Recommended Resources | Notes |
| :---- | :---- |
| todo | installation |
| [5 steps to getting started with Red Hat OpenShift](https://www.redhat.com/en/resources/5-steps-getting-started-with-openshift-checklist) | Sys admin - Intro to Installation |
| [Installation overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/installation_overview/index)| Sys admin - Installation Documentation || todo | walk or run  - deployment strategies |
| [Red Hat OpenShift GitOps](https://www.redhat.com/en/technologies/cloud-computing/openshift/gitops) | Deployment Strategies - GitOps Intro |
| [What is Argo CD?](https://www.redhat.com/en/topics/devops/what-is-argocd) | Deployment Strategies -  ArgoCD |
| [What is Helm?](https://www.redhat.com/en/topics/devops/what-is-helm#overview) | Deployment Strategies - Helm |
| [What is CI/CD?](https://www.redhat.com/en/topics/devops/what-is-ci-cd#why-is-ci/cd-important) | Deployment Strategies - Pipelines
| [Kubernetes Patterns, 2nd Edition](https://developers.redhat.com/e-books/kubernetes-patterns) | eBook - Building and Running containers  |
| [GitOps Cookbook: Kubernetes Automation in Practice](https://developers.redhat.com/e-books/gitops-cookbook?extIdCarryOver=true&intcmp=7015Y000003t7aWQAQ&percmp=RHCTG0250000438148&sc_cid=701f2000000tyN6AAI) | eBook -  Git-based workflow|
| [The Path to GitOps](https://developers.redhat.com/e-books/path-gitops) | eBook - Helm, Kustomize, ArgoCD |
| [Getting GitOps: A practical platform with OpenShift, Argo CD, and Tekton](https://developers.redhat.com/e-books/getting-gitops-practical-platform-openshift-argo-cd-and-tekton) | eBook - ArgoCD Tekton |
| [DevOps Culture and Practice with OpenShift](https://developers.redhat.com/e-books/devops-culture-and-practice-openshift) | eBook - DevOps Culture |
| [5 Ways developers benefit from OpenShift](https://developers.redhat.com/e-books/5-ways-developers-benefit-red-hat-openshift)   | Developer  - eBook|
| todo | walk or run  - networking |
| todo | walk or run  - storage |
| todo | walk or run  - compliance and security |
| todo | walk or run  - monitoring and logging  |
| todo | dev  |
| [The Modern Developer](https://developers.redhat.com/e-books/modern-developer) | Developer - eBook |

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
