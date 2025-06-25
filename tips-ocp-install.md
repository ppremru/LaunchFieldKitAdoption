# Installing OCP

There are no short cuts, read the user documentation and experiment.

* Reminder:  IaC is your friend.
* [Installation overview](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/installation_overview/index)
* [Disconnected Environment](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/disconnected_environments/index)
* [Updating clusters](https://docs.redhat.com/en/documentation/openshift_container_platform/4.19/html/updating_clusters/index)

## General Tips for System Admins Preparing to Install OpenShift Red Hat Container Platform

WORK IN PROGRESS NOT VALIDATED

Preparing to install OpenShift Container Platform (OCP) is a significant undertaking that requires thorough planning and attention to detail. For a system administrator, it's not just about running an installer; it's about building a robust, scalable, and secure platform.

Here are some general tips to help a system administrator prepare:

### 1. **Thorough Planning and Design**

* **Define Your Use Case:** Understand *why* you're installing OpenShift. What applications will run on it? What are the performance and scalability requirements? This dictates cluster size, node types, and storage choices.
* **Capacity Planning:** Accurately estimate CPU, memory, and storage needs for your master, worker, and infrastructure nodes. Factor in future growth and overhead for OpenShift itself.
* **Network Topology:** Design your network carefully. OpenShift is network-intensive. Plan for sufficient bandwidth, low latency, and proper routing between nodes.
* **IP Address Management (IPAM):** Plan your IP ranges for nodes, services, and pods to avoid conflicts and ensure smooth operation.
* **High Availability (HA):** For production environments, plan for high availability for master nodes (minimum 3 masters), worker nodes, and external services like load balancers.
* **Version Selection:** Choose the appropriate OCP version based on your needs, supported applications, and compatibility with your existing infrastructure. Review release notes for known issues and features.

### 2. **Meet Infrastructure Prerequisites**

* **Operating System:** Ensure all nodes are running a supported version of Red Hat Enterprise Linux (RHEL) or Red Hat CoreOS (RHCOS). For OCP 4.x, RHCOS is the preferred and often mandatory OS for control plane nodes.
* **Hardware Requirements:** Verify that all physical or virtual machines meet the minimum CPU, RAM, and disk space requirements for each node type (master, worker, infrastructure). These can be substantial.
* **Networking Hardware:** Ensure your switches, routers, and firewalls can handle the traffic and policies required for OpenShift.
* **Time Synchronization (NTP):** Absolutely critical! All nodes in the cluster must have accurate and synchronized time using NTP. Time drift can cause severe cluster instability.
* **DNS Resolution:** Reliable DNS is paramount. All OpenShift components and applications rely heavily on DNS for service discovery. Plan for robust forward and reverse DNS.
* **Load Balancer:** A highly available load balancer (e.g., HAProxy, F5, AWS ELB, Azure Load Balancer, Google Load Balancer) is required for distributing traffic to master nodes and application routes.

### 3. **Networking Considerations (Crucial!)**

* **Firewall Rules:** Meticulously configure firewall rules (on hosts and network devices) to allow necessary communication between all OpenShift components and external services. Refer to Red Hat's detailed port requirements.
* **Proxy Configuration:** If you're in an air-gapped or restricted network environment, plan for proxy servers for internet access (for pulls from registries, updates, etc.).
* **OpenShift SDN/CNI:** Understand the default OpenShift Software-Defined Network (OVN-Kubernetes, OpenShiftSDN) or integrate with a third-party Container Network Interface (CNI) plugin if required.
* **Ingress/Egress:** Plan how external traffic will reach your applications (Ingress controllers/Routes) and how applications will access external services (Egress IPs, NetworkPolicy).

### 4. **Storage Planning**

* **Persistent Storage:** Applications running on OpenShift often require persistent storage. Plan for robust, scalable, and highly available storage solutions. Common choices include:
  * **Internal:** OpenShift Data Foundation (ODF, formerly OpenShift Container Storage) based on Ceph.
  * **External:** NFS, iSCSI, Fibre Channel, cloud-specific storage (AWS EBS, Azure Disk, Google Persistent Disk), or specialized storage solutions.
* **Storage Classes:** Define appropriate Storage Classes in Kubernetes/OpenShift to provision persistent volumes dynamically.

### 5. **Security Best Practices**

* **Registry Security:** Plan for a secure image registry (internal OpenShift registry, Quay.io, Docker Hub private, etc.) and establish image scanning policies.
* **Authentication and Authorization:** Integrate OpenShift with your existing identity providers (e.g., LDAP, Active Directory, OAuth providers) for user authentication and define appropriate Role-Based Access Control (RBAC) policies.
* **Security Context Constraints (SCCs):** Understand and plan for OpenShift's SCCs, which control what actions pods can perform and what resources they can access. Many applications need custom SCCs.
* **Secrets Management:** Plan how sensitive information (API keys, database passwords) will be stored and managed securely (e.g., using OpenShift Secrets, HashiCorp Vault, or external secret managers).

### 6. **Installation Method**

* **Installer-Provisioned Infrastructure (IPI):** Simplifies deployment on supported public clouds (AWS, Azure, GCP, vSphere) by automating infrastructure provisioning.
* **User-Provisioned Infrastructure (UPI):** Requires you to provision and manage all infrastructure components yourself. More complex but offers maximum control for bare metal or specific virtualized environments.
* **Automation:** Consider using automation tools like Ansible (especially with the OpenShift Ansible Installer or collections) for UPI installations to ensure consistency and repeatability.

### 7. **Post-Installation & Day 2 Operations**

* **Monitoring and Alerting:** Plan for comprehensive monitoring (using OpenShift's built-in Prometheus/Grafana or integrating with external tools) and alerting for cluster health and application performance.
* **Logging:** Centralize cluster and application logs (using OpenShift Logging or external ELK stack/Splunk).
* **Backup and Restore:** Establish a robust strategy for backing up your etcd (control plane data) and application data.
* **Patching and Upgrades:** Understand the OpenShift upgrade process (minor versions, major versions) and plan your patching strategy for nodes.

### 8. **Documentation and Training**

* **Read the Documentation:** This cannot be stressed enough. The official Red Hat OpenShift documentation is extensive and covers all aspects of planning, installation, and management.
* **Red Hat Support:** Leverage your Red Hat subscription for support and guidance.
* **Training:** Encourage yourself and your team to undergo Red Hat OpenShift training to build necessary skills.

By meticulously addressing these areas during the preparation phase, a system administrator can significantly increase the chances of a successful and robust OpenShift Container Platform installation.
