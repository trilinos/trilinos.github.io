---
title: WebTrilinos Docker Image
permalink: web_trilinos_docker_image.html
folder: packages
---

The WebTrilinos, browser-based Trilinos repository can be accessed via a Docker Image. Instructions for obtaining the Image and installing Docker are below.

**1.Follow these directions to install Docker on your local machine:**

* Linux: [http://docs.docker.com/linux/step_one/](http://docs.docker.com/linux/step_one/)  
* OS X: [http://docs.docker.com/mac/step_one/](http://docs.docker.com/mac/step_one/)  
* Windows: [http://docs.docker.com/windows/step_one/](http://docs.docker.com/windows/step_one/)

_Note_: For OS X and Windows, ensure that hardware virtualization is enabled in your BIOS settings. You may also have to disable Hyper-V in Windows Features.

_Note_: For OS X and Windows, Docker Toolbox will install Oracle VM VirtualBox if it is not already installed. If you already have VirtualBox installed on your machine, you do not have to uninstall it prior to installing Docker Toolbox. Native support for running Docker on Windows and OS X is in “beta” currently. The native support option does not require VirtualBox.

**2. Open Docker:**

* Linux: Open a terminal, and then start the Docker service if it is not already started.

_Note_: For Linux, Docker requires `sudo` to run. You can avoid this by adding users to the `docker group`, but be warned that the `docker group` is equivalent to giving a user `root access`.

* OS X and Windows: Open the Docker Quickstart Terminal application. A terminal window should appear and start the Docker Toolbox VM. 
You will see a single `$` when it is done loading.

_Note_: If you have an issue connecting to the VM (an error message like `No connection could be made because the target machine actively refused it` when you run a command), 
open VirtualBox and delete the ‘default’ machine. Then re-run Docker Quickstart Terminal as an administrator. 
If you still have problems, ensure that hardware virtualization is enabled in your BIOS settings and you have disabled Hyper-V in Windows Features.

**3. Pull the WebTrilinos image by entering the following command:**

`docker pull sjdeal/webtrilinos:12_2`

You can confirm that the image was pulled by running _docker images_

**4. Start a new container from the image by entering the following command (all one line):**

`docker run -d -p 9999:80 --name=WebTrilinos sjdeal/webtrilinos:12_2 usr/sbin/apache2ctl -D FOREGROUND`

This will bind port 9999 of the container to port 80 of the host machine and start Apache in the container. The container port number can be changed from 9999 if you wish.

**5. Open WebTrilinos in a browser:**

* Linux: Access localhost:9999/WebTrilinos from a web browser.
* OS X/Windows: Run docker-machine ip default to find the IP address for the VM, then access <ip>:9999/WebTrilinos from a web browser.

WebTrilinos is already configured to work properly in the container. You can proceed to use WebTrilinos!

Since the Python and MatrixPortal modules are unsupported, it is recommended that users use the C++ interface page as their landing page for using WebTrilinos.

### Docker Command Reference

* `docker exec <container-name> <command>`: Executes a command in a running container
* `docker images`: Lists all images available on the local machine
* `docker inspect <container-name>`: Displays information about a container
* `docker inspect <image-ID>`: Displays information about an image
* `docker ps -a`: Shows all containers
* `docker pull <image-name>`: Pulls an image from the Docker Hub Registry
* `docker rename <container-name> <new-name>`: Renames a container
* `docker rm <container-name>`: Removes a container
* `docker rmi <image-ID>`: Removes an image
* `docker run <image-ID> <command>`: Creates a new container and runs a given command
* `docker start <container-name>`: Starts a stopped container
* `docker stop <container-name>`: Stops a running container
* `docker run -it <image-ID> <command>`: Starts a new container and executes a command

(for example docker run -it --name=WebTrilinos sjdeal/webtrilinos:12_2 /bin/bash, name is optional)