---
title: WebTrilinos Docker Image
permalink: web_trilinos_docker_image.html
folder: packages
---

The WebTrilinos, browser-based Trilinos repository can be accessed via a Docker Image. Instructions for obtaining the Image and installing Docker are below.

1.  <span style="font-weight: 400;">Follow these directions to install Docker on your local machine:</span>

<span style="font-weight: 400;">Linux: [http://docs.docker.com/linux/step_one/](http://docs.docker.com/linux/step_one/)  
</span><span style="font-weight: 400;">OS X: [http://docs.docker.com/mac/step_one/](http://docs.docker.com/mac/step_one/)  
</span><span style="font-weight: 400;">Windows: [http://docs.docker.com/windows/step_one/](http://docs.docker.com/windows/step_one/)</span>

<span style="font-weight: 400;">**</span>_<span style="font-weight: 400;">Note</span>_<span style="font-weight: 400;">: For OS X and Windows, ensure that hardware virtualization is enabled in your BIOS settings. You may also have to disable Hyper-V in Windows Features.</span>

<span style="font-weight: 400;">**</span>_<span style="font-weight: 400;">Note</span>_<span style="font-weight: 400;">: For OS X and Windows, Docker Toolbox will install Oracle VM VirtualBox if it is not already installed. If you already have VirtualBox installed on your machine, you do not have to uninstall it prior to installing Docker Toolbox. Native support for running Docker on Windows and OS X is in “beta” currently. The native support option does not require VirtualBox.</span>

1.  <span style="font-weight: 400;">Open Docker:</span>

<span style="font-weight: 400;">Linux: Open a terminal, and then start the Docker service if it is not already started.</span>

<span style="font-weight: 400;">**</span>_<span style="font-weight: 400;">Note</span>_<span style="font-weight: 400;">: For Linux, Docker requires</span> <span style="font-weight: 400;">sudo</span> <span style="font-weight: 400;">to run. You can avoid this by adding users to the</span> <span style="font-weight: 400;">docker</span> <span style="font-weight: 400;">group, but be warned that the</span> <span style="font-weight: 400;">docker</span> <span style="font-weight: 400;">group is equivalent to giving a user</span> <span style="font-weight: 400;">root</span> <span style="font-weight: 400;">access.</span>

<span style="font-weight: 400;">OS X and Windows: Open the Docker Quickstart Terminal application. A terminal window should appear and start the Docker Toolbox VM. You will see a single</span> <span style="font-weight: 400;">$</span> <span style="font-weight: 400;">when it is done loading.</span>

<span style="font-weight: 400;">**</span>_<span style="font-weight: 400;">Note</span>_<span style="font-weight: 400;">: If you have an issue connecting to the VM (an error message like</span> <span style="font-weight: 400;">No connection could be made because the target machine actively refused it</span> <span style="font-weight: 400;">when you run a command), open VirtualBox and delete the ‘default’ machine. Then re-run Docker Quickstart Terminal as an administrator. If you still have problems, ensure that hardware virtualization is enabled in your BIOS settings and you have disabled Hyper-V in Windows Features.</span>

1.  <span style="font-weight: 400;">Pull the WebTrilinos image by entering the following command:</span>

<span style="font-weight: 400;">docker pull sjdeal/webtrilinos:12_2</span>

<span style="font-weight: 400;">You can confirm that the image was pulled by running</span> <span style="font-weight: 400;">docker images</span><span style="font-weight: 400;">.</span>

1.  <span style="font-weight: 400;">Start a new container from the image by entering the following command (all one line):</span>

<span style="font-weight: 400;">docker run -d -p 9999:80 --name=WebTrilinos sjdeal/webtrilinos:12_2 usr/sbin/apache2ctl -D FOREGROUND</span>

<span style="font-weight: 400;">This will bind port 9999 of the container to port 80 of the host machine and start Apache in the container. The container port number can be changed from 9999 if you wish.</span>

1.  <span style="font-weight: 400;">Open WebTrilinos in a browser:</span>

<span style="font-weight: 400;">Linux: Access localhost:9999/WebTrilinos from a web browser.</span>

<span style="font-weight: 400;">OS X/Windows: Run</span> <span style="font-weight: 400;">docker-machine ip default</span> <span style="font-weight: 400;">to find the IP address for the VM, then access <ip>:9999/WebTrilinos from a web browser.</span>

<span style="font-weight: 400;">WebTrilinos is already configured to work properly in the container. You can proceed to use WebTrilinos!</span>

Since the Python and MatrixPortal modules are unsupported, it is recommended that users use the C++ interface page as their landing page for using WebTrilinos.

### <span style="font-weight: 400;">Docker Command Reference</span>

<span style="font-weight: 400;">docker exec <container-name> <command></span> <span style="font-weight: 400;">Executes a command in a running container</span>

<span style="font-weight: 400;">docker images</span> <span style="font-weight: 400;">Lists all images available on the local machine</span>

<span style="font-weight: 400;">docker inspect <container-name></span> <span style="font-weight: 400;">Displays information about a container</span>

<span style="font-weight: 400;">docker inspect <image-ID></span> <span style="font-weight: 400;">Displays information about an image</span>

<span style="font-weight: 400;">docker ps -a</span> <span style="font-weight: 400;">Shows all containers</span>

<span style="font-weight: 400;">docker pull <image-name></span> <span style="font-weight: 400;">Pulls an image from the Docker Hub Registry</span>

<span style="font-weight: 400;">docker rename <container-name> <new-name></span> <span style="font-weight: 400;">Renames a container</span>

<span style="font-weight: 400;">docker rm <container-name></span> <span style="font-weight: 400;">Removes a container</span>

<span style="font-weight: 400;">docker rmi <image-ID></span> <span style="font-weight: 400;">Removes an image</span>

<span style="font-weight: 400;">docker run <image-ID> <command></span> <span style="font-weight: 400;">Creates a new container and runs a given command</span>

<span style="font-weight: 400;">docker start <container-name></span> <span style="font-weight: 400;">Starts a stopped container</span>

<span style="font-weight: 400;">docker stop <container-name></span> <span style="font-weight: 400;">Stops a running container</span>

<span style="font-weight: 400;">docker run -it <image-ID> <command></span> <span style="font-weight: 400;">Starts a new container and executes a command</span>

<span style="font-weight: 400;">(for example</span> <span style="font-weight: 400;">docker run -it --name=WebTrilinos sjdeal/webtrilinos:12_2 /bin/bash, name is optional</span><span style="font-weight: 400;">)</span>