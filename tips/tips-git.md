# Git Tips

## Key References

* [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
* [Git and GitHub learning resources](https://docs.github.com/en/get-started/start-your-journey/git-and-github-learning-resources)

## Git Basic Workflow Commands

Here's a short list of essential Git commands for the basic workflow:
* **`git init`**: Initializes a new Git repository in the current directory.
* **`git clone [URL]`**: Creates a local copy of a remote repository.
* **`git add .`**: Stages all changes (new, modified, deleted files) for the next commit.
* **`git add [filename]`**: Stages specific files for the next commit.
* **`git commit -m "Your commit message"`**: Records the staged changes as a new commit in the repository history.
* **`git status`**: Shows the current state of the working directory and staging area.
* **`git log`**: Displays the commit history.
* **`git branch [branch-name]`**: Creates a new branch.
* **`git checkout [branch-name]`**: Switches to a different branch.
* **`git merge [branch-name]`**: Integrates changes from one branch into the current branch.
* **`git pull`**: Fetches changes from the remote repository and merges them into the current branch.
* **`git push`**: Uploads local commits to the remote repository.

## More on Git

Git is a distributed version control system that helps developers track changes in their source code, collaborate with others, and manage different versions of their projects. Here are the fundamental commands:
* **`git init`**:
  * **Purpose:** Initializes a new Git repository in the current directory. This command creates a hidden `.git` folder that stores all the necessary repository data.
  * **When to use:** When starting a new project that you want to put under version control.

* **`git clone <repository-url>`**:
  * **Purpose:** Creates a local copy of an existing Git repository from a remote location (like GitHub, GitLab, Bitbucket, or an internal Git server).
  * **When to use:** When you want to start working on an existing project that's already in a Git repository.

* **`git add <file(s)>`** or **`git add .`**:
  * **Purpose:** Stages changes for the next commit. `git add <file>` stages a specific file, while `git add .` stages all changes in the current directory and its subdirectories. Staging means telling Git which changes you want to include in your next snapshot.
  * **When to use:** After you've made changes to files and want to include them in your next commit.

* **`git commit -m "Your descriptive message"`**:
  * **Purpose:** Records the staged changes as a new snapshot in the repository's history. Each commit includes a unique ID and a message describing the changes.
  * **When to use:** After staging your changes and you're ready to save them as a version point in your project's history. The message should clearly explain what was changed.

* **`git status`**:
  * **Purpose:** Shows the status of your working directory and staging area. It tells you which files are untracked, modified, or staged for commit.
  * **When to use:** Frequently, to check the current state of your repository and understand what changes are pending.

* **`git log`**:
  * **Purpose:** Displays the commit history of the current branch. It shows commit IDs, authors, dates, and commit messages.
  * **When to use:** To review past changes, understand who made what changes, and find specific commits.

* **`git pull`**:
  * **Purpose:** Fetches changes from a remote repository and integrates (merges) them into your current local branch. This is how you get updates from your team.
  * **When to use:** Before starting work each day, or before pushing your own changes, to ensure your local repository is up-to-date with the remote.

* **`git push`**:
  * **Purpose:** Uploads your local commits to a remote repository. This makes your changes available to others.
  * **When to use:** After committing your changes locally, when you're ready to share them with the remote repository and your team.

* **`git branch`**:
  * **Purpose:** Lists all local branches. `git branch <new-branch-name>` creates a new branch.
  * **When to use:** To see existing branches or to start a new feature or bug fix on a separate line of development.

* **`git checkout <branch-name>`** (or `git switch <branch-name>` for newer Git versions):
  * **Purpose:** Switches to a different branch. This updates your working directory to reflect the files of that branch.
  * **When to use:** To move between different lines of development, work on multiple features concurrently, or switch to a stable branch.

These commands form the foundation of daily Git usage for any developer working on a version-controlled project.
