---
title: MueLu Tutorial
permalink: muelu_tutorial.html
folder: packages
---

The [MueLu tutorial](http://trilinos.org/wordpress/wp-content/uploads/2015/03/MueLu_tutorial.pdf) describes the most important features of MueLu covering the absolute beginner’s level, the advanced users and multigrid experts. It contains accompanying exercises where the interested user can do its own experiments with multigrid parameters. The MueLu tutorial is directly included in the MueLu sources in Trilinos.

To avoid the compilation of MueLu/Trilinos the user has the following options to run the exercises for the MueLu tutorial

*   **VirtualBox image:** [Here](https://software.sandia.gov/trilinos/downloads/MueLu_tutorial.ova) is the MueLu virtual machine image with a pre-compiled version of Trilinos containing the MueLu tutorial. (<span style="color: #ff0000;">Warning</span>, the image is 1.5 GB).  
    _Please note:_ Appendix A of the [MueLu tutorial](http://trilinos.org/wordpress/wp-content/uploads/2015/03/MueLu_tutorial.pdf) has detailed installation instructions of the virtual box image. You will need to install [VirtualBox](https://www.virtualbox.org/ "VirtualBox") to handle virtual box appliances.
*   **Docker container:** We provide a docker container (based on CentOS 7) with a pre-compiled version of the MueLu tutorial. To run the docker container you will need to install [docker](https://www.docker.com/) on your computer. The container comes with an internal VNC server which allows to use the tutorial GUI. Use the following commands to download and run the docker container:  
    `docker pull tawiesn/muelu-tutorial  
    docker run -dP -p 5901:5901 tawiesn/muelu-tutorial`Once the docker container is running use a VNC client to connect to your machine (port 5901). The password is __password__Open a terminal (right mouse button) and change into the `muelu-tutorial` folder. Load the OpenMPI module using the command  
    `module load mpi/openmpi-x86_64`.  
    Then run the MueLu tutorial script with  
    `./hands-on.py`.If you don’t have a VNC client you still can use the docker container and run the MueLu tutorial. But you won’t be able to plot the residuals and errors. Start the container using the command  
    <span style="font-family: Monaco, Consolas, 'Andale Mono', 'DejaVu Sans Mono', monospace; font-size: 13px; font-style: normal;">  
    docker run -i -t --rm tawiesn/muelu-tutorial.</span>

The tutorial has been presented at the CNRS multigrid winter school in [Frejus/France](http://calcul.math.cnrs.fr/spip.php?article250&lang=fr).

Explore [Muelu Docker](muelu_docker.md)