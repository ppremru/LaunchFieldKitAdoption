# About the Field-Kit and Stack

## What is a Field-Kit?

A *Field-Kit*, as used in this document, describes a hardware configuration of servers. These servers are specifically intended to run software applications, whether they are virtualized or containerized, for use by users (operators) in the field.

The deployment and configuration of applications to a *Field-Kit* exists in a separate repository.  That solution leverages Ansible to install OpenShift Container Platform (OCP).   OCP is configured to support virtualized systems and containerized applications. This Community of Practice (CoP) aims to equip the technical support team with the skills to maintain and enhance this solution.

## Which Products are in the Stack?

This CoP facilitates product enablement for the following **Red Hat** products in current release:

* Red Hat Enterprise Linux (RHEL)
* Ansible-core
* OpenShift Container Platform (OCP)
* OpenShift-Virtualization (OCP-Virt)

Future release:

* Enterprise Application Platform (EAP)
* Ansible Automation Platform (AAP)

## Field Kit Diagrams WORK IN PROGRESS

* [Overview of Red Hat Stack](./diagram-arch.md)
* [Overview of Field Kit Delivery](./diagram-process.md)
* [1 - Build Field Kit Package](./diagram-1.md)
* [3 - Prepare SysCon](./diagram-3.md)
* [4 - Deploy Field Kit](./diagram-4.md)
* [5 - Verify Field Kit](./diagram-5.md)
* [Data Dump](./diagram-all.md)