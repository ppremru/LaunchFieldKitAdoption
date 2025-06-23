# Ansible

## User Profiles

* Infrastructure Developers
* Integrators
* Field Operators

## Key References

* [Ansible Community Documentation](https://docs.ansible.com/)
* [Good Practices for Ansible](https://redhat-cop.github.io/automation-good-practices/)
* [Red Hat Developer - Automation Topics](https://developers.redhat.com/topics/automation)
* [Red Hat Blog - Ansible Channel](https://www.redhat.com/en/blog/channel/red-hat-ansible-automation)
* [Ansible Forum Community Q&A Forum](https://forum.ansible.com/)

## Enablement

### RHLS Core Recommendations

* [Take a free skills assessment to see where you should start training](https://skills.ole.redhat.com/en)
* [Red Hat Enterprise Linux Automation with Ansible (RH294)](https://www.redhat.com/en/services/training/rh294-red-hat-linux-automation-with-ansible)
* [Red Hat Certified Engineer (RHCE) exam (EX294)](https://www.redhat.com/en/services/training/ex294-red-hat-certified-engineer-rhce-exam-red-hat-enterprise-linux-9)
* [*Stretch Goals* - Red Hat Ansible Automation Platform Skills Path](https://www.redhat.com/en/resources/ansible-automation-platform-skills-path-brief)

### Independent Learning

#### Crawl

Identify the basic concepts of ansible.   Focus on ansible-core, not Ansible Automation Platform (AAP).

| Recommended Resources | Notes |
| :-------------------- | :---- |
| [Tales from the field: A system administrator's guide](https://www.redhat.com/rhdc/managed-files/co-system-administrators-guide-to-IT-automation-ebook-1933814OM-202503-en.pdf)  | Intro- Article from Admin Point of View |
| [Ansible vs. Red Hat Ansible Automation Platform](https://www.redhat.com/en/technologies/management/ansible/ansible-vs-red-hat-ansible-automation-platform) | Intro - Ansible and other platforms |
| [Getting Started with Playbooks](https://docs.redhat.com/en/documentation/red_hat_ansible_automation_platform/2.5/html/getting_started_with_playbooks/assembly-intro-to-playbooks#ref-how-do-playbooks-work) | Intro - Documentation |
| [Getting Started with Ansible](https://docs.ansible.com/ansible/latest/getting_started/index.html)  | Intro - Community Documentation |
| [Ansible Basics: Automation Technical Overview](https://www.redhat.com/en/services/training/do007-ansible-essentials-simplicity-automation-technical-overview) | Intro - Video |
| [Learning Ansible Basics](https://www.redhat.com/en/topics/automation/learning-ansible-tutorial) | Core Concepts - Certified Content |
| [What is an Ansible Playbook?](https://www.redhat.com/en/topics/automation/what-is-an-ansible-playbook) | Core concepts - Playbook |
| [What is an Ansible Role—and how is it used?](https://www.redhat.com/en/topics/automation/what-is-an-ansible-role)  | Core concepts - Roles |
| [What is an Ansible Module—and how does it work?](https://www.redhat.com/en/topics/automation/what-is-an-ansible-module#creating-and-sharing-ansible-modules)  | Core concepts - Modules |
| [What is Ansible automation hub and why should you use it?](https://www.redhat.com/en/blog/what-ansible-automation-hub-and-why-should-you-use-it)  | Core concepts - Automation Hub |
| [Ansible Content Collections](https://www.redhat.com/en/technologies/management/ansible/content-collections)  | Core concepts - Collections  |

#### Walk

Start experimenting with ansible using no cost labs.  Use tools for debugging such as ansible lint.

| Recommended Resources | Notes |
| :-------------------- | :---- |
| [Getting started with Ansible Automation Platform](https://developers.redhat.com/products/ansible/getting-started#imnewtoansible) | Labs - Experiment |
| [Interactive labs for Red Hat Ansible Automation Platform](https://www.redhat.com/en/interactive-labs/ansible) | Labs - Experiment |
| [Getting started with Ansible Content Collections](https://developers.redhat.com/learn/ansible/getting-started-ansible-content-collections) | Labs - Collections |
| [Find mistakes in your playbooks with Ansible Lint](https://www.redhat.com/en/blog/ansible-lint)  | Troubleshooting - Ansible Lint |
| [6 troubleshooting skills for Ansible playbooks](https://www.redhat.com/en/blog/troubleshoot-ansible-playbooks)  | Troubleshooting - Tips |
| [Alex Dworjan's Ansible Video YouTube Channel](https://www.youtube.com/watch?v=goclfp6a2IQ&list=PL2_OBreMn7FqZkvMYt6ATmgC0KAGGJNAN)  | Video sessions - from Installation to Runtime |
| [Ansible Video Channel on YouTube](https://www.youtube.com/playlist?list=PLdu06OJoEf2ZWrbPxrQwktHsN1wYzYtHx) | Video sessions - Ansible Fundamentals |

#### Run

| Recommended Resources | Notes |
| :-------------------- | :---- |
| [Deep dive on Ansible VScode extension](https://www.ansible.com/blog/deep-dive-on-ansible-vscode-extension) | VS Code  |

TBD - Security, Networking, ServiceNow, Cloud, Middleware, Windows

## Tips for Ansible Automation

The tips below often require hands-on experimentation and teamwork.

### Deploy Ansible to any Linux environment  

Notes on installing `ansible-core`:

* Ansible Core with RHEL 8 & 9
  * ansible-core is provided in the RHEL 8 and RHEL 9 Application Stream repositories
  * [Updates to using Ansible Core in Red Hat Enterprise Linux](https://www.redhat.com/en/blog/updates-using-ansible-core-in-rhel#:~:text=RHEL%208.6%20%2F%209.0%20(May%202022,2023)%20included%20Ansible%20Core%202.14)
* Install Ansible Community  
  * [Installing Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#)
* Install Ansible on RHEL 7
  * [Quick start guide to Ansible for Linux sysadmins](https://www.redhat.com/en/blog/ansible-quick-start)
* Configure SSH  - Cheat sheet  
  * [SSH into remote machines using Ansible](https://developers.redhat.com/cheat-sheets/ssh-remote-machines-using-ansible)

### Create, troubleshoot, and actively develop against new / existing playbooks

#### High level recommendations

* Create an **environment for development** and testing as well as experimenting
* Install and configure **VS Code**
  * Setup extensions for both YAML and Git
  * Refer to VS Code notes in [Foundations](./foundations.md)
* Practice basic **git** commands
  * Create a repository of your own
  * Experiment with git basic commands such as clone, branch, pull, push, commit, switch
  * Refer to git workflow notes in [Foundations](./foundations.md)
* Experiment with ansible options for **troubleshooting**
  * Experiment with the debug module and the --verbose command line option
  * Refer to the troubleshooting notes in the "Walk" section above

#### Concise tips

##### **Creating / Starting Playbooks**

* **Start Simple**  
Begin with a minimal playbook targeting a single host and a single task.
* **Use Roles**  
For reususability and organization, structure your automation using Ansible Roles (e.g., `ansible-galaxy init my_role`).
* **Name Everything**  
Always give descriptive `name:` attributes to your plays, tasks, and handlers. This makes output clear and troubleshooting easier.
* **Idempotency**  
Design tasks to be repeatable without causing unintended side effects if run multiple times. Ansible modules are generally idempotent by default, but be mindful when scripting.
* **Version Control**  
Store all playbooks, roles, and inventory in a version control system (like Git) from the start.

##### **Troubleshooting Playbooks**

* **Increase Verbosity**  
Use `-v`, `-vv`, `-vvv`, `-vvvv` with `ansible-playbook` for more detailed output. `-vvv` is often a good starting point.
* **Syntax Check**  
Run `ansible-playbook --syntax-check your_playbook.yml` to catch basic YAML and Ansible syntax errors before execution.
* **Dry Run (`--check`)**  
Use `ansible-playbook --check your_playbook.yml` to simulate execution without making actual changes. This helps verify task order and conditions.
* **Diff Mode (`--diff`)** Combine `--check --diff` to see what changes *would* be applied to files.
* **`debug` Module**  
Insert `debug:` tasks to print variable values, task output, or messages at specific points for inspection (e.g., `debug: var: my_variable`).
* **Target Specific Tasks**  
Use `--start-at-task "Task Name"` to begin execution from a particular task, or `--step` to interactively approve each task.
* **Inspect Facts**  
If tasks depend on discovered host facts, run `ansible -m setup hostname` to see all collected facts.
* **Check Paths**  
Verify `roles_path` and `collections_paths` in `ansible.cfg` if roles/collections aren't found.
* **Dependency Order**  
Ensure roles/tasks run in the correct logical sequence, especially if one task's output is an input to another. Remember `meta/main.yml` dependencies run first.

#### **Actively Developing Playbooks**

* **Iterative Development:**  
Write a few tasks, test them, then add more. Don't write the whole playbook at once.
* **Environment Consistency:**  
 Use Ansible Execution Environments or consistent virtual environments (`virtualenv`, `venv`) to manage Python and collection dependencies.
* **`requirements.yml`:**  
 Use a `requirements.yml` file to manage collection and role dependencies for your project, and regularly run `ansible-galaxy install -r requirements.yml`.
* **Clear Variables:**  
 Define variables explicitly (e.g., in `vars/main.yml`, `defaults/main.yml`, `group_vars`, `host_vars`) and use descriptive names.
* **Handlers for Changes:**  
Use handlers for services that need restarting only when a configuration file changes, promoting efficiency.
* **Tags for Granularity:**
Use `tags:` on tasks or plays to allow selective execution (e.g., `ansible-playbook --tags "webserver" your_playbook.yml`).
* **Documentation:**
Add comments within your playbooks and roles (`# Your comment`) to explain logic and intent. For roles, a `README.md` is essential.
* **Testing:**
Implement testing (e.g., Molecule) for complex roles to ensure they work as expected across different scenarios.

### Identify, update, troubleshoot playbook dependencies

Managing Ansible playbook dependencies primarily involves Roles and Collections.   Below are a few hints to follow:

#### **Identifying Dependencies**

* Roles  
  * Check `meta/main.yml` within a role for `dependencies:` listed.  
  * Also, inspect your main playbook's `roles:` section.
* Collections/External Roles
  * Look for `requirements.yml` in your project root.  
  * This file lists collections (e.g.,`community.general`) and roles (e.g., `geerlingguy.docker`) your project needs from Ansible Galaxy or other sources.

#### **Updating Dependencies**

* Roles & Collections
  * Use `ansible-galaxy install -r requirements.yml` to install/update all listed dependencies.  
  * You can specify version constraints (e.g., `collection_name: "==1.2.3"`).

#### **Troubleshooting Dependencies**

* "Not Found" Errors
  * Check paths: Ensure `ansible.cfg` or environment variables correctly point to your `roles_path` and `collections_paths`.
  * Verify installation: Confirm `ansible-galaxy` ran successfully and files exist (e.g., in `~/.ansible/collections`).
  * Typos: Double-check spelling of role/collection names.
* Execution Order Issues
  * Role dependencies: Remember `meta/main.yml` dependencies run before the role that declares them.  
  Roles in a play's `roles`: section execute in listed order.
  * Handlers: Handlers only run when notified and at the end of a play (or specific points).
* Version Conflicts
  * Pin versions: Use `requirements.yml` to explicitly pin versions (e.g., `collection_name: "==1.2.3"`) to avoid unexpected updates.
* Debugging Tools
  * debug module: Insert `debug: var: my_variable or msg: "..."` tasks to inspect variable values and task output.
  * Use ansible-core options
    * `--check`  Perform a dry run to see what would happen without making changes.
    * `--start-at-task`  Control playbook execution flow for focused troubleshooting.
    * `-vvv` View detailed output.
