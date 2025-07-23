# Jenkins Basics for Developers on OpenShift

Jenkins is an open-source automation server widely used for implementing Continuous Integration (CI) and Continuous Delivery (CD) pipelines. In the context of OpenShift, Jenkins plays a crucial role in automating the process of building, testing, and deploying containerized applications.

**What is Jenkins?**
Jenkins automates repetitive tasks in software development. For developers, it primarily serves as the engine that takes their code changes from a version control system (like Git) and transforms them into deployable artifacts (like container images), eventually pushing them to environments like OpenShift.

**Why use Jenkins with OpenShift?**

* **Automated CI/CD:** Jenkins automates the entire software delivery pipeline, from code commit to deployment on OpenShift. This ensures consistent, rapid, and reliable releases.
* **Build Automation:** Automatically builds container images from source code whenever changes are detected in Git.
* **Testing Automation:** Integrates with testing frameworks to automatically run unit, integration, and other tests.
* **Deployment Automation:** Orchestrates the deployment of applications to OpenShift using tools like `oc` (OpenShift CLI) or Helm.
* **Visibility:** Provides a central dashboard to monitor the status of builds, tests, and deployments.

## Key Concepts for Developers

* **Job/Project:** A configured task in Jenkins that performs a specific set of actions (e.g., build an application, run tests, deploy to a stage).
* **Pipeline:** A series of automated steps that define your application's continuous delivery process. Jenkins pipelines are often defined using a `Jenkinsfile` (a Groovy script) stored in your source code repository, enabling "Pipeline-as-Code."
  * **Stages:** Logical divisions within a pipeline (e.g., `Build`, `Test`, `Deploy`).
  * **Steps:** Individual actions within a stage (e.g., `git clone`, `podman build`, `helm upgrade`).
* **Build:** An execution of a Jenkins job or pipeline. Each build has a unique number and logs.

## Developer Interactions / Basic Workflow

1. **Triggering Builds (Automatically):**
    * The most common way for a developer's work to interact with Jenkins is automatically. When you push code changes to your Git repository (e.g., `git push`), a webhook (configured on your Git server) typically notifies Jenkins.
    * Jenkins then triggers the pre-configured CI/CD pipeline associated with your repository.

2. **Triggering Builds (Manually):**
    * **Purpose:** To initiate a build for a specific branch or with specific parameters outside of a Git push.
    * **How:** Navigate to your project/pipeline in the Jenkins UI, then click "Build Now" or "Build with Parameters" (if the pipeline is configured for parameterized builds).
    * **When to use:** For testing a specific feature branch, re-running a failed build, or performing a manual deployment to a specific environment.

3. **Monitoring Build Status:**
    * **Purpose:** To see if your code changes are successfully building, testing, and deploying.
    * **How:** Access the Jenkins dashboard. You'll see a list of recent builds for your project, usually indicated by colors (e.g., blue/green for success, red for failure, yellow for unstable). Click on a specific build number to view its details.
    * **When to use:** After pushing code, to ensure your changes didn't break the build or introduce new issues.

4. **Reviewing Build Logs (Console Output):**
    * **Purpose:** To debug why a build failed or to understand the steps performed during a successful build.
    * **How:** From the build status page, click "Console Output." This displays the live output of all commands executed during the pipeline run.
    * **When to use:** Immediately when a build fails (red status) to identify the error message and line number where the issue occurred.

5. **Accessing Build Artifacts:**
    * **Purpose:** If your Jenkins pipeline generates artifacts (e.g., test reports, compiled binaries, container image manifests), you can access them.
    * **How:** On a successful build page, look for an "Artifacts" or "Build Artifacts" section.
    * **When to use:** To download test reports for local analysis or inspect generated files.

6. **Understanding `Jenkinsfile`:**
    * **Purpose:** The `Jenkinsfile` defines the entire pipeline as code. As a developer, understanding its structure is critical for contributing to the pipeline or debugging issues.
    * **How:** Located in the root of your Git repository. It typically defines stages like `Checkout`, `Build Image`, `Push Image`, `Deploy to OpenShift`. It uses steps that often invoke `oc` or `helm` commands.
    * **When to use:** When you need to understand how your application is being built or deployed, or if you need to propose changes to the CI/CD process.

7. **Credentials and Access:**
    * Jenkins often interacts with OpenShift using service accounts or credentials configured by the operations team. Developers typically don't manage these directly but should be aware that the pipeline has the necessary permissions to deploy to target OpenShift namespaces.

By understanding these basics, a developer can effectively use Jenkins as a powerful tool to automate their application's journey from code to production on OpenShift.
