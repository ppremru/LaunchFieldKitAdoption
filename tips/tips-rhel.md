# Tips for the new user on RHEL

For a new user on Red Hat Enterprise Linux (RHEL), here's a short list of fundamental commands to get started with navigating the system and managing files:

**Navigation & Information:**

* **`pwd`**: **P**rint **w**orking **d**irectory. Shows your current location in the file system.
* **`ls`**: **L**i**s**t directory contents. Shows files and folders in your current directory.
    * `ls -l`: Long listing format, showing more details (permissions, owner, size, date).
    * `ls -a`: Shows all files, including hidden ones (those starting with a dot `.`).
    * `ls -la` or `ll`: Combines long listing and all files.
* **`cd [directory]`**: **C**hange **d**irectory. Navigates to a different folder.
    * `cd ~`: Go to your home directory.
    * `cd ..`: Go up one directory level.
    * `cd -`: Go back to the previous directory you were in.
* **`clear`**: Clears the terminal screen.
* **`man [command]`**: Displays the **man**ual page (help document) for a specific command. This is incredibly useful for learning about options and usage.

**File & Directory Management:**

* **`mkdir [directory_name]`**: **M**a**k**e **dir**ectory. Creates a new folder.
* **`touch [filename]`**: Creates an empty file.
* **`cp [source] [destination]`**: **C**o**p**y files or directories.
    * `cp -r [source_directory] [destination_directory]`: Copies a directory and its contents recursively.
* **`mv [source] [destination]`**: **M**o**v**e or rename files and folders.
* **`rm [filename]`**: **R**e**m**ove a file. *Use with caution! There's no trash bin.*
    * `rm -r [directory_name]`: Removes a directory and its contents recursively.
    * `rm -i [filename]` or `rm -ir [directory_name]`: Prompts for confirmation before deleting.
* **`cat [filename]`**: Displays the **cat**alog (content) of a file to the terminal.
* **`head [filename]`**: Displays the first 10 lines of a file (useful for large files).
* **`tail [filename]`**: Displays the last 10 lines of a file (useful for logs).

**System Information & Permissions:**

* **`sudo [command]`**: **S**uper **u**ser **do**. Executes a command with elevated privileges (as root). You'll usually be prompted for your password.
* **`df -h`**: **D**isk **f**ree. Shows disk space usage in a human-readable format.
* **`free -h`**: Shows memory usage in a human-readable format.
* **`top`**: Displays real-time information about running processes and system resource usage.
* **`ps aux`**: Displays running processes.
* **`chmod [permissions] [filename]`**: **Ch**ange **mod**e. Changes file permissions (e.g., `chmod 755 script.sh`). This is a more advanced topic but essential for executables.
* **`chown [user]:[group] [filename]`**: **Ch**ange **own**er. Changes the owner and group of a file.

This list provides a solid starting point for interacting with RHEL from the command line!
