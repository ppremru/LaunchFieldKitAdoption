# Launch Field-Kit Adoption Repository

This repository serves as a community of practice (CoP), designed to aid new team members in effectively onboarding a project called *Field-Kit* built on a Red Hat product *stack*.  Specifically, this document serves as a guide for preparing technicians to support and improve the **Field Kit** solution.

## What is a Field-Kit?

A *Field-Kit*, as used in this document, describes a hardware configuration of servers. These servers are specifically intended to run software applications, whether they are virtualized or containerized, for use by operaters in the field.

A *Field-Kit* deployment and configuration solution exists in a separate repository.  That solution leverages Ansible to install OpenShift Container Platform (OCP).   OCP is configured to support virtualized systems and containerized applications. This Community of Practice (CoP) aims to equip the technical support team with the skills to maintain and enhance this solution.

## Which Products are in the Stack?

This CoP facilitates product enablement for the following Red Hat products:

* Red Hat Enterprise Linux (RHEL)
* Ansible-core  
* OpenShift Container Platform  
* OpenShift-Virt
* Enterprise Application Platform (EAP)
* Ansible Automation Platform (AAP)

# About the Community

## What is a CoP?

Communities of practice (CoP) can form around various topics, such as project management, artificial intelligence, cybersecurity, or, in this case, enablement. A community of practice is a group of people who come together around a shared interest to share knowledge, solve problems, and develop expertise over time. Unlike teams or task forces, which often focus on specific goals and deliverables, a community of practice is about long-term learning, collaboration, and continuous improvement. Community members can come from different departments, roles, or skill levels. Instead of obsessing over achieving immediate results, a good community of practice focuses on learning, sharing best practices, and evolving together.     

This article highlights the goals of a CoP: [Speed automation adoption with a community of practice](https://www.redhat.com/rhdc/managed-files/ma-automation-community-of-practice-ebook-1698261kvm-202502-en.pdf)

## Why do we need this CoP?

With a delivered *Field-Kit* solution in hand, the project team must provide support and plan for future enhancements. A diverse range of user profiles exists, each with unique enablement requirements. Some users possess expert-level knowledge, while others are novices or only need a basic overview.  Establishing community-driven knowledge article collections can effectively map out pathways and offer valuable reference recommendations.

### Enablement Material

Acknowledging diverse backgrounds, learning styles, and capabilities, team member enablement should be adaptable. This framework serves as a guide, not a rigid rule set.

Available resources:

* Formal Red Hat Learning Subscription (RHLS) courses  
* Red Hat free training materials  
* Blog posts  
* Technical documentation

In addition, structured "lunch and learn" sessions should be scheduled with the team on a regular basis to allow for a more in-depth investigation into particular topics.

### CoP User Profile

To address the varying expertise levels across our technology stack, given the team's diverse roles, we are forming this Community of Practice. The identified profiles within the team include:   TODO:  need a brief description of jprofiles.

[Table of Stack and Profile](./tableStackProfile.pdf "table 1")

* Infrastructure Developers   
* Integrators  
* Software Developers  
* Field Ops

### Enablement Maturity

Given the diverse skillset within the team, the adoption and enablement of the technology stack will evolve in a phased approach, with stages frequently occurring concurrently. These stages include:

1. **Crawl:** Initial exploration, unsure of the starting point.  
2. **Walk:** Basic experimentation within a development environment.  
3. **Run:** Supporting the production environment with troubleshooting, debugging, and minor modifications.    
4. **Stretch:** Ongoing support of the production environment, encompassing troubleshooting, debugging, and additional releases.

### Bringing it all together
The *Enablement Recommendations* are organized into RHLS (requires purchase) focused courses and independent learning (no charge).   The expectation is that the independent learning is for shorter time commitements - focus on the **Crawl** and **Walk** phases of **maturity**.  Most of the RHLS courses start with the **Crawl**, **Walk**, then proceed to more focused labs and exams that lead to **Run**.

# Enablement Recommendations

* [Red Hat Enterprise Linux (RHEL)](./rhel.md)
* [Ansible](./ansible.md)
* [OpenShift Container Platform (OCP)](./ocp.md)
* [OpenShift Virtualization (OCP-Virt)](./ocp-virt.md)
* [Ansible Automation Platform (AAP)](./aap.md)
* [Enterprise Application Platform (EAP)](./eap.md)

