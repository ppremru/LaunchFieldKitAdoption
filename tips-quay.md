# Getting Started with Quay.io: The Basics for New Users

Quay.io (often just called Quay) is a hosted container image registry service provided by Red Hat. Think of it as **GitHub for your container images** (Docker, OCI images, etc.). It's where you store, manage, and distribute your containerized applications.

## What is Quay.io?

* **Container Registry:** Its main job is to be a central hub for your container images. When you build a Docker image, for instance, you can **"push" it to Quay.io to store it**. Other users or systems can then **"pull" that image** to use it.
* **Managed Service:** Quay.io is fully managed, meaning Red Hat handles the infrastructure, scaling, and maintenance. You don't have to worry about setting up and running your own registry.
* **Security Focused:** A key feature of Quay.io is its strong emphasis on security. This includes:
  * **Vulnerability Scanning (Clair):** It automatically scans your images for known security vulnerabilities (CVEs) in operating system packages and programming language libraries.
  * **Granular Access Control:** You can set precise permissions on your repositories, defining who can read, write, or administer them.
  * **Robot Accounts:** These are special accounts for automated systems (like CI/CD pipelines) to securely interact with your repositories.
* **Integration with Git Providers:** You can connect Quay.io to your Git repositories (GitHub, GitLab, Bitbucket, etc.) to enable **automated image builds** whenever changes are pushed to your code.
* **Organizations and Teams:** Quay.io offers features for collaborative work, allowing you to create organizations and teams to manage shared repositories and permissions effectively.

## Why Use Quay.io?

* **Centralized Storage:** Provides a single, reliable place to store all your container images.
* **Improved Security:** Built-in vulnerability scanning and strong access controls help you maintain a secure software supply chain.
* **Automation:** Integrates with your development workflow for automated image builds and deployments.
* **Collaboration:** Features like organizations and teams make teamwork on container projects much easier.
* **Reliability:** As a Red Hat managed service, it's designed for high availability and performance.

## Basic Usage for New Users

### 1. Create a Quay.io Account

Head over to [Quay.io](https://quay.io) and sign up. You'll likely use your Red Hat credentials if you have them, or create a new account. Your chosen **username will be part of your default namespace** for repositories (e.g., `quay.io/<your_username>/my-repo`).

### 2. Understand Repositories

* A **repository** is where your container images are stored. Each repository can hold multiple versions (called **tags**) of an image.
* **Public vs. Private:**
  * **Public Repositories:** Anyone can pull images from a public repository without authentication. These are free and unlimited.
  * **Private Repositories:** Only authorized users or robot accounts can access private repositories. These usually require a paid plan on Quay.io.

### 3. Create Your First Repository

Once you're logged in, look for an option like "Create New Repository."

* Give your repository a name (use lowercase letters, numbers, and underscores).
* Choose whether it will be public or private.
* Click "Create."

### 4. Authenticate with Quay.io

To push or pull images, you'll need to log in from your local machine using a container client like **Podman** or **Docker**.

```bash

# Using Podman (recommended by Red Hat):
podman login quay.io

# Using Docker:
docker login quay.io

```

You'll be prompted for your Quay.io username and password.

### 5.  Pulling an Image

To download an image from Quay.io:

```bash

podman pull quay.io/<username_or_org>/<repository_name>:<tag>
# Example: podman pull quay.io/myuser/my-app:latest

```

If the repository is public, you can pull it even without logging in.

#### 6. Pushing an Image

To upload an image to Quay.io:

a. **Build your image locally:**

```bash
podman build -t my-app:latest . # Or docker build
```

b. Tag your image for Quay.io:

You need to retag your local image with the Quay.io registry address and your repository name.

```bash
podman tag my-app:latest quay.io/<username_or_org>/my-app:latest
```

c. **Push the tagged image:**

```bash
podman push quay.io/<username_or_org>/my-app:latest
```

#### 7. Managing Tags

* **Tags** are labels (like latest, v1.0, dev) that identify specific versions of your images within a repository.  
* You can view, add, move, and delete tags through the Quay.io web UI or via its API.

#### 8. Explore Security Features

After you push an image, Quay.io will automatically scan it for vulnerabilities. You can view these reports in the web UI for your repository. Be sure to check out **Robot Accounts** for automated pushes and pulls from CI/CD pipelines.

#### 9. Organizations and Teams (for collaboration)

If you're working with a team, create an **Organization** in Quay.io. This provides a shared namespace for repositories that multiple users can access. Within an organization, you can create **Teams** and assign specific permissions (read, write, admin) to those teams for different repositories.

### **Next Steps**

* **Official Documentation:** The Quay.io documentation (check [docs.projectquay.io](https://docs.projectquay.io/) or Red Hat's Quay.io documentation) is your best resource for in-depth information.  
* **Automated Builds:** Learn how to set up build triggers to automatically build and push images from your Git repositories.  
* **Webhooks:** Configure webhooks to send notifications about repository events (e.g., new image pushed, vulnerability detected).  
* **CLI Tools:** While podman and docker are essential, explore other tools like skopeo for more advanced image operations.

Quay.io offers a robust set of features for managing your container images, especially with its focus on security and collaboration. Start with the basics of creating repositories, pushing/pulling images, and then explore its advanced capabilities as your needs grow.
