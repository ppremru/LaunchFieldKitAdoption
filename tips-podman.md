## Podman Basics 

**What is Podman?**
Podman is a daemonless, open-source container engine for developing, managing, and running OCI (Open Container Initiative) compliant containers and pods. Unlike Docker, Podman doesn't require a constantly running daemon process, which can simplify its usage and enhance security. It's often considered the native container engine for Red Hat-based systems.

**Why use Podman for OpenShift Development?**

* **Local Development Mirroring:** OpenShift's underlying container runtime uses `CRI-O`, which shares many characteristics and compatibility with Podman. Developing with Podman locally provides an environment that closely mirrors how your containers will behave on an OpenShift cluster.
* **Daemonless Operation:** No need to run a background service, simplifying local setup and reducing resource consumption.
* **Rootless Containers:** Podman allows running containers as a non-root user, enhancing security and aligning well with OpenShift's security model (which generally discourages root usage in containers).
* **Image Building:** Developers can use Podman to build container images (`Containerfile` or `Dockerfile`) locally before pushing them to an image registry for deployment on OpenShift.
* **Pod Management:** Podman can manage "pods" (groups of containers), which aligns with Kubernetes' and OpenShift's fundamental unit of deployment.

## Essential Podman Commands

* **`podman build -t <image-name>:<tag> .`**:
  * **Purpose:** Builds a container image from a `Containerfile` (or `Dockerfile` - Podman uses both) located in the current directory (`.`). The `-t` flag tags the image with a name and optional version.
  * **When to use:** After writing your `Containerfile` and application code, to create the runnable image for your application.

* **`podman run -p <host-port>:<container-port> <image-name>:<tag>`**:
  * **Purpose:** Runs a new container from a specified image. The `-p` flag maps a port on your host machine to a port inside the container, allowing you to access the application.
  * **When to use:** To test your application locally in a containerized environment before deploying to OpenShift.

* **`podman ps`**:
  * **Purpose:** Lists currently running containers. Add `-a` (`podman ps -a`) to see all containers, including stopped ones.
  * **When to use:** To check if your containers are running, view their IDs, names, and status.

* **`podman stop <container-id-or-name>`**:
  * **Purpose:** Stops one or more running containers.
  * **When to use:** To gracefully shut down a running container.

* **`podman rm <container-id-or-name>`**:
  * **Purpose:** Removes one or more stopped containers.
  * **When to use:** To clean up your local environment by deleting containers you no longer need.

* **`podman rmi <image-id-or-name>`**:
  * **Purpose:** Removes one or more container images from your local storage.
  * **When to use:** To free up disk space by deleting outdated or unused images.

* **`podman login <registry-url>`**:
  * **Purpose:** Authenticates Podman to a container registry (e.g., Docker Hub, Quay.io, or your OpenShift internal registry). This is necessary before pushing or pulling private images.
  * **When to use:** Before pushing your newly built images to a remote registry, or pulling images from a private one.
  * **OpenShift Consideration:** For OpenShift's internal registry, you'll typically use `podman login default-route-openshift-image-registry.<your-openshift-cluster-domain> -u $(oc whoami) -p $(oc whoami -t)`.

* **`podman push <image-name>:<tag> <registry-url>/<project>/<image-name>:<tag>`**:
  * **Purpose:** Pushes a local image to a specified container registry.
  * **When to use:** After you've built and tested your image locally, to make it available for OpenShift deployments.
  * **OpenShift Consideration:** The target registry URL usually follows the pattern of your OpenShift internal registry (e.g., `default-route-openshift-image-registry.<cluster-domain>/<namespace>/<image-name>`).

* **`podman pull <image-name>:<tag>`**:
  * **Purpose:** Pulls a container image from a registry to your local machine.
  * **When to use:** To get a base image, or to pull an existing application image from a registry for local testing.

* **`podman images`**:
  * **Purpose:** Lists all local container images.
  * **When to use:** To see what images you have downloaded or built on your machine.

By integrating these Podman commands into your daily workflow, developers can efficiently build, test, and manage their container images locally, ensuring a smooth transition to deployment on OpenShift.
