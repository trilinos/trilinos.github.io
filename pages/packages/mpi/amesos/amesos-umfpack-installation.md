---
title: Amesos UMFPACK Installation
permalink: amesos-umfpack-installation.html
folder: mpi
---

## UMFPACK Installation

_NOTE:_ These intructions were updated in February 2007 for Umfpack 5\. They may not be kept up-to-date. Refer to the Umfpack documentation for more recent and more complete instructions.

UMFPACK must be installed before Amesos_Umfpack can be used. Follow these steps to install UMFPACK on your system:

*   Obtain the UMFPACK distribution from [Tim Davis’s web site](http://faculty.cse.tamu.edu/davis/suitesparse.html)
*   Untar the UMFPACK code in your Trilinos3PL directory.
    *   Note that UMFPACK 5 requires two additional packages: UFconfig and AMD. Download and untar all three.
    
*   Build UMFPACK
    *   Edit UFconfig/UFconfig.mk
    *   Note:Trilinos3PL/config/UMFPACKv5 contains the UFconfig.mk files that I used.
    *   cd UMFPACK
    *   make
    
*   Check the results:
    *   Execuing “make” in the UMFPACK directory runs tests and compares results against expected results.
    
*   Update your configure invocation script by, for example, adding the following:
    *   --enable-amesos-umfpack
    *   --with-libs=”/directory_path/UMFPACK/Lib/libumfpack.a “
    *   --with-incdirs=”-I/directory_path/UMFPACK/Include/”
    
*   Note that libamd.a is no longer required as AMD is automatically included in Amesos.
