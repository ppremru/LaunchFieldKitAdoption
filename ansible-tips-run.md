# Create, troubleshoot, and develop playbooks

The notes below contain summarized information from the crawl, walk and run articles; as well as some information is repeated. *Add lessons learned to this section.*

## High level tips

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

## Concise tips

### Creating / Starting Playbooks

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

### Troubleshooting Playbooks

* **Increase Verbosity**  
Use `-v`, `-vv`, `-vvv`, `-vvvv` with `ansible-playbook` for more detailed output.  `-vvv` is often a good starting point.
* **Syntax Check**  
Run `ansible-playbook --syntax-check your_playbook.yml` to catch basic YAML and Ansible syntax errors before execution.
* **Dry Run**  
Use `ansible-playbook --check your_playbook.yml` to simulate execution without making actual changes.  This helps verify task order and conditions.
* **Diff Mode**  
Combine `--check --diff` to see what changes would be applied to files.
* **`debug` Module**  
Insert `debug:` tasks to print variable values, task output, or messages at specific points for inspection.  EG: `debug: var: my_variable`
* **Target Specific Tasks**  
Use `--start-at-task "Task Name"` to begin execution from a particular task, or `--step` to interactively approve each task.
* **Inspect Facts**  
If tasks depend on discovered host facts, run `ansible -m setup hostname` to see all collected facts.
* **Check Paths**  
Ensure roles/tasks run in the correct logical sequence, especially if one task's output is an input to another.  Remember `meta/main.yml` dependencies run first.

### Actively Developing Playbooks

* **Iterative Development**  
Write a few tasks, test them, then add more. Don't write the whole playbook at once.
* **Environment Consistency**  
Use Ansible Execution Environments or consistent virtual environments (`virtualenv`, `venv`) to manage Python and collection dependencies.
* **`requirements.yml`**  
Use a `requirements.yml` file to manage collection and role dependencies for your project, and regularly run `ansible-galaxy install -r requirements.yml`.
* **Clear Variables**  
Define variables explicitly (e.g., in `vars/main.yml`, `defaults/main.yml`, `group_vars`, `host_vars`) and use descriptive names.
* **Handlers for Changes**   
Use handlers for services that need restarting only when a configuration file changes, promoting efficiency.
* **Tags for Granularity**  
Use `tags:` on tasks or plays to allow selective execution (e.g., `ansible-playbook --tags "webserver" your_playbook.yml`).
* **Documentation**  
Add comments within your playbooks and roles (`# Your comment`) to explain logic and intent. For roles, a `README.md` is essential.
* **Testing**    
Implement testing (e.g., Molecule) for complex roles to ensure they work as expected across different scenarios.

## Identify, update, troubleshoot playbook dependencies

Managing Ansible playbook dependencies primarily involves Roles and Collections.   Below are a few hints to follow:

### Identifying Dependencies

* **Roles**  
  * Check `meta/main.yml` within a role for `dependencies:` listed.  
  * Also, inspect your main playbook's `roles:` section.
* **Collections/External Roles**  
  * Look for `requirements.yml` in your project root.  
  * This file lists collections (e.g.,`community.general`) and roles (e.g., `geerlingguy.docker`) your project needs from Ansible Galaxy or other sources.

### Updating Dependencies

* **Roles & Collections**  
  * Use `ansible-galaxy install -r requirements.yml` to install/update all listed dependencies.  
  * You can specify version constraints (e.g., `collection_name: "==1.2.3"`).

### Troubleshooting Dependencies

* **"Not Found" Errors**  
   * Check paths: Ensure `ansible.cfg` or environment variables correctly point to your `roles_path` and `collections_paths`.
   * Verify installation: Confirm `ansible-galaxy` ran successfully and files exist (e.g., in `~/.ansible/collections`).
   * Typos: Double-check spelling of role/collection names.
* **Execution Order Issues**  
   * Role dependencies: Remember `meta/main.yml` dependencies run before the role that declares them.  
   * Roles in a play's `roles`: section execute in listed order.
   * Handlers: Handlers only run when notified and at the end of a play (or specific points).
* **Version Conflicts**  
   * Pin versions: Use `requirements.yml` to explicitly pin versions (e.g., `collection_name: "==1.2.3"`) to avoid unexpected updates.
* **Debugging Tools**  
   * debug module: Insert `debug: var: my_variable or msg: "..."` tasks to inspect variable values and task output.
   * Use ansible-core options  
     * `--check`  Perform a dry run to see what would happen without making changes.  
     * `--start-at-task`  Control playbook execution flow for focused troubleshooting.  
     * `-vvv` View detailed output.  
