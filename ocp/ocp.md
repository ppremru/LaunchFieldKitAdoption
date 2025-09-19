# About Enablement for OpenShift Container Platform (OCP)

## There are different user profiles in the world of OCP.   For example -

  1. Administrators - Platform installation
  2. DevOps - Day Two Operations, including configuration of operators and CI/CD
  3. Developers - Containerization of applications

## Checklist

All profiles will benefit from basic knowledge of the following:

- Container Management tools (not specific to OCP)
  - **ContainerFiles**
  - **Buildah**
  - **Podman**
  - **Quay**
- Container Orchestration*
  - Difference between Kubernetes and OCP
- OpenShift Container Platform and Tools
  - **oc** Command line
- OCP User Interface (admin and dev views)
  - **GitOps** Operator
  - **ArgoCD**
  - **Helm**
  - **Tekton**

> *Note because of installation requirements, for enablement it is recommended to use existing clusters from the RHLS labs or no cost labs*

## Key References

- [OpenShift Documentation](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19)
- [Self-managed for Administrators](https://docs.redhat.com/en/essentials/openshift/self-managed-for-administrators)
- [Red Hat OpenShift Cheat Sheet](https://developers.redhat.com/cheat-sheets/red-hat-openshift-container-platform)
- [OpenShift Container Platform 4.x Tested Integrations](https://access.redhat.com/articles/4128421)

## RHLS Core Recommendations

While there are two paths for RHLS OCP courses, system admin and developer, these core courses could be useful to all the profiles.

- [Take a free skills assessment to see where you should start training](https://skills.ole.redhat.com/en) :star:
- [**Containers, Kubernetes and Red Hat OpenShift Technical Overview - Free course**](https://www.redhat.com/en/services/training/do080-deploying-containerized-applications-technical-overview) :star:
- [*Stretch Goals* - Red Hat OpenShift skill paths](https://www.redhat.com/en/resources/openshift-skill-paths-datasheet)

### Integrators and Field Operations

- [Red Hat OpenShift Administration I: Operating a Production Cluster (DO180)](https://www.redhat.com/en/services/training/red-hat-openshift-administration-i-operating-a-production-cluster)
- [Red Hat OpenShift Administration II: Configuring a Production Cluster (DO280)](https://www.redhat.com/en/services/training/red-hat-openshift-administration-ii-configuring-a-production-cluster)

### Developers  

- [Red Hat OpenShift Development I: Introduction to Containers with Podman (DO188)](https://www.redhat.com/en/services/training/do188-red-hat-open-shift-development-introduction-containers-with-podman)
- [Red Hat Certified Specialist in Containers exam (EX188)](https://www.redhat.com/en/services/training/ex188-red-hat-certified-specialist-containers-exam)
- [Red Hat OpenShift Developer II: Building and Deploying Cloud-native Applications (DO288)](https://www.redhat.com/en/services/training/red-hat-openshift-developer-ii-building-and-deploying-cloud-native-applications)
- [Red Hat Certified OpenShift Application Developer exam (EX288)](https://www.redhat.com/en/services/training/ex288-red-hat-certified-openshift-application-developer-exam)

## Independent Learning Path Recommendations

### Labs for Getting Started with OpenShift

- [Overview: Container Fundamentals](https://developers.redhat.com/learn/rhel/container-fundamentals)  
- [Overview: Foundations of OpenShift](https://developers.redhat.com/learn/openshift/foundations-openshift)
- [Interactive labs for Red Hat OpenShift](https://www.redhat.com/en/interactive-labs/openshift)

### GitOps *updated 2025 Sept*

- Intro
  - [What is CI/CD?](https://www.redhat.com/en/topics/devops/what-is-ci-cd#why-is-ci/cd-important)
  - [What is GitOps?](https://www.redhat.com/en/topics/devops/what-is-gitops#what-is-gitops)
  - [What is a Container Registry?](https://www.redhat.com/en/topics/cloud-native-apps/what-is-a-container-registry)

- And More ... 
  - [What is Argo CD?](https://www.redhat.com/en/topics/devops/what-is-argocd)
  - [What is Helm?](https://www.redhat.com/en/topics/devops/what-is-helm#overview)
  - [What is the OpenShift GitOps Operator?](https://www.redhat.com/en/technologies/cloud-computing/openshift/gitops)
  - [Red Hat OpenShift GitOps](https://www.redhat.com/en/technologies/cloud-computing/openshift/gitops)
  - [Introduction to GitOps with OpenShift](https://www.redhat.com/en/blog/introduction-to-gitops-with-openshift)
  - [An Introduction to the Quay Container Registry](https://www.redhat.com/en/blog/introduction-quay)
  - [How to Validate GitOps Manifests](https://developers.redhat.com/articles/2023/10/10/how-validate-gitops-manifests#)

- Labs
  - Instruqt Lab  [Get started with Argo CD and GitOps with Red Hat OpenShift](https://www.redhat.com/en/interactive-labs/openshift) *patience required on start-up time*
    
- Reference Material
  - [ArgoCD Documentation](https://argo-cd.readthedocs.io/en/stable/)
    
- eBooks
  - [The Path to GitOps](https://developers.redhat.com/e-books/path-gitops)
    
- Videos
  - [Getting Started with ArgoCD](https://demo.openshift.com/en/latest/argocd/) *15 minutes, oldie but goody*
  - [Red Hat OpenShift GitOps (Argo CD) | Intro & Setup](https://developers.redhat.com/devnation/shorts/red-hat-openshift-gitops) *leads into short sessions*

### Container Management

- Intro
  - [Understanding Containers](https://www.redhat.com/en/topics/containers)  
  - [What is Podman?](https://www.redhat.com/en/topics/containers/what-is-podman)
  - [What is Buildah?](https://www.redhat.com/en/topics/containers/what-is-buildah)
  - [3 advantages of Podman vs. Docker](https://developers.redhat.com/articles/2023/08/03/3-advantages-docker-podman)
  - [What is a Container Registry?](https://www.redhat.com/en/topics/cloud-native-apps/what-is-a-container-registry)
 
- And More ... 
  - [What is container orchestration?](https://www.redhat.com/en/topics/containers/what-is-container-orchestration#what-is-container-orchestration)
  - [What is Kubernetes?](https://www.redhat.com/en/topics/containers/what-is-kubernetes)
  - [Red Hat OpenShift vs. Kubernetes](https://www.redhat.com/en/technologies/cloud-computing/openshift/red-hat-openshift-kubernetes)
  - [Kubernetes: A Pod’s Life](https://www.redhat.com/en/blog/kubernetes-pods-life)

### OpenShift Container Platform Concepts

- [5 steps to getting started with Red Hat OpenShift](https://www.redhat.com/en/resources/5-steps-getting-started-with-openshift-checklist) :star:
- [DevOps with OpenShift Pipelines and OpenShift GitOps](https://developers.redhat.com/articles/2024/09/17/devops-openshift-pipelines-gitops)
- [What are Red Hat OpenShift Operators?](https://www.redhat.com/en/technologies/cloud-computing/openshift/what-are-openshift-operators)
- [Installation overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/installation_overview/index)
- [Day 2 operations for OpenShift Container Platform](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/postinstallation_configuration/index)
- [Security and compliance](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/security_and_compliance/index)
- [Observability overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/observability_overview/index)

### More e-books

- [Podman in Action](https://developers.redhat.com/e-books/podman-action)
- [DevOps Culture and Practice with OpenShift](https://developers.redhat.com/e-books/devops-culture-and-practice-openshift)
- [5 Ways developers benefit from OpenShift](https://developers.redhat.com/e-books/5-ways-developers-benefit-red-hat-openshift)
- [Kubernetes Patterns, 2nd Edition](https://developers.redhat.com/e-books/kubernetes-patterns)
- [GitOps Cookbook: Kubernetes Automation in Practice](https://developers.redhat.com/e-books/gitops-cookbook?extIdCarryOver=true&intcmp=7015Y000003t7aWQAQ&percmp=RHCTG0250000438148&sc_cid=701f2000000tyN6AAI)

- [Getting GitOps: A practical platform with OpenShift, Argo CD, and Tekton](https://developers.redhat.com/e-books/getting-gitops-practical-platform-openshift-argo-cd-and-tekton)
- [Red Hat OpenShift Service Mesh](https://www.redhat.com/en/technologies/cloud-computing/openshift/what-is-openshift-service-mesh)
