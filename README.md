# Launch Field-Kit Adoption

This repository serves as a community of practice (**CoP**), designed to aid new team members in effectively onboarding a project referred to as *Field-Kit* built on a *Red Hat product Stack*.  Specifically, this document serves as a guide for preparing technicians to support and improve the *Field-Kit* solution.

## What is a Field-Kit?

A *Field-Kit*, as used in this document, describes a hardware configuration of servers. These servers are specifically intended to run software applications, whether they are virtualized or containerized, for use by users (operators) in the field.

The deployment and configuration of applications to a *Field-Kit* exists in a separate repository.  That solution leverages Ansible to install OpenShift Container Platform (OCP).   OCP is configured to support virtualized systems and containerized applications. This Community of Practice (CoP) aims to equip the technical support team with the skills to maintain and enhance this solution.

## Which Products are in the Stack?

This CoP facilitates product enablement for the following Red Hat products:

* Red Hat Enterprise Linux (RHEL)
* Ansible-core  
* OpenShift Container Platform (OCP)
* OpenShift-Virtualization (OCP-Virt)
* Enterprise Application Platform (EAP)
* Ansible Automation Platform (AAP)

## About the Community

### What is a CoP?

Communities of practice (CoP) can form around various topics, such as project management, artificial intelligence, cybersecurity, or, in this case, enablement. A community of practice is a group of people who come together around a shared interest to share knowledge, solve problems, and develop expertise over time. Unlike teams or task forces, which often focus on specific goals and deliverables, a community of practice is about long-term learning, collaboration, and continuous improvement. Community members can come from different departments, roles, or skill levels. Instead of obsessing over achieving immediate results, a good community of practice focuses on learning, sharing best practices, and evolving together.

### Why do we need this CoP?

With a *Field-Kit* solution in hand, the project team must provide support and plan for future enhancements. A diverse range of user profiles exists, each with unique enablement requirements. Some users possess expert-level knowledge, while others are novices.  Establishing community-driven knowledge article collections can effectively map out pathways and offer valuable reference recommendations. The CoP maintains a versioned set of living documents that provide recommendations - it will take time to cultivate for the team.

### Enablement Material

Acknowledging diverse backgrounds, learning styles, and capabilities, team member enablement should be adaptable. This framework serves as a guide, not a rigid rule set.  Examples of enablement materials:

* Red Hat Learning Subscription (RHLS)
* Red Hat Hands-on Labs (no cost)
* Product Documentation
* Blog Posts
* eBooks
* YouTube

### User Profiles

The user profiles identified for the team include:

1. **Infrastructure Developers**
2. **Integrators**  
3. **Software Developers**
4. **Field Operators**

[Table - Stack and Profile](./tableStackProfile.pdf "table 1")  
*NOTE: A possible topic to address in the future is to develop a RACI chart specific to these roles.*

### Enablement Maturity

Given the diverse skills within the team, the adoption and enablement of the technology stack will evolve in a phased approach. Maturity stages include:

1. **Crawl**  
Initial exploration
2. **Walk**  
Initial experimentation, quick wins with product capabilities, domain specific solutions, developing good practices
3. **Run**  
Supporting production environment with troubleshooting, debugging, and minor modifications, developing and sharing good practices
4. *Optimizing*  
Ongoing support of the production environment, encompassing cross-functional domains

### Bringing it all together

Completing structured courses, reading, experimentation and collaboration are essential to mastering the skills of the product stack.   The team needs time to absorb new information, skills, and tools. There's an initial learning phase, followed by a period of practice and refinement to achieve proficiency.  Approach:

1. **Red Hat Learning Subscriptions (RHLS)**  
RHLS courses offer structured, comprehensive Red Hat training with features like hands-on labs, instructor-led videos, and expert support, which are not typically found in no-cost materials.  
2. **Independent Learning**  
No cost materials offer foundational using a variety of media from blogs to videos to hands-on labs.
3. **Hands-on Exploration**  
A sandbox dedicated to development provides team members the freedom to innovate and experiment without consequences.
4. **Collaboration**  
Collaboration fosters peer-to-peer learning by regularly demonstrating experiments, problems, and solutions.

## Enablement Recommendations

Collection of recommended links for RHLS and Independent Learning:

* [Foundations](./foundations.md)
* [Red Hat Enterprise Linux (RHEL)](./rhel.md)
* [Ansible](./ansible.md)
* [OpenShift Container Platform (OCP)](./ocp.md)
* [OpenShift Virtualization (OCP-Virt)](./ocp-virt.md)
* [Ansible Automation Platform (AAP)](./aap.md)
* [Enterprise Application Platform (EAP)](./eap.md)

*Assumption:  The CoP will tune these recommendations after experimentation and collaboration.*
