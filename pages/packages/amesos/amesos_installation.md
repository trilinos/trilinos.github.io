---
title: Amesos Installation
permalink: amesos_installation.html
folder: packages
---

Adding --enable-amesos to the configure line will allow Amesos to be installed and offers access to the Amesos_Klu class. Access to other classes require some additional installation effort.

We recommend that you create a Trilinos3PL directory to house all of the third party libraries that you will use with Amesos.

Amesos

Amesos configure switches.
UMFPACK

UMFPACK installation supports Amesos_Umfpack.
ScaLAPACK

ScaLAPACK installation supports Amesos_Scalapack. ScaLAPACK is also required for Amesos_Mumps.
MUMPS

MUMPS installation supports Amesos_Mumps.
PARAKLETE

PARAKLETE installation supports Amesos_Paraklete.
SuperLU MPI

SuperLU MPI installation supports Amesos_Superludist.
KLU

Amesos_KLU does not require the installation of any third party package.
DSCPACK

DSCPACK installation supports Amesos_Dscpack.      


### Other Amesos Installation

* [Amesos DSCPACK Install](amesos-dscpack-install.html)
* [Amesos Install](amesos_install.html) 
* [Amesos MUMPS Install](amesos-mumps-install.html)
* [Amesos Paraklete Install](amesos-paraklete-install) 
* [Amesos ScaLAPACK Install](amesos-scalapack-install.html) 
* [Amesos SuperLU MPI Install](amesos-superlu-mpi-install.html) 
* [Amesos UMFPACK Installation](amesos-umfpack-installation.html) 
