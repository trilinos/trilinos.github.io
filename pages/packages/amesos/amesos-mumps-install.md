---
title: Amesos MUMPS Install
permalink: amesos-mumps-install.html
folder: packages
---

## MUMPS Support

Trilinos 10.0 includes support for MUMPS version 4.7.3\. There is experimental support for MUMPS 4.9 (please contact the amesos-developers for details).

MUMPS Installation

_NOTE:_ These intructions were updated in June 2006\. They may not be kept up-to-date. Refer to the [MUMPS website](http://mumps.enseeiht.fr) for more recent and more complete instructions.

MUMPS and ScaLAPACK must both be available on your system before Amesos_Mumpscan be used.

MUMPS requires a fortran 90 compiler. Most high performance computer systems include a fortan 90 compiler and the gnu compilers now include the gnu f95 compiler, gfortran, by default. MUMPS has been shown to work with Intel’s fortran 90 compiler, [ifort](http://www.intel.com/cd/software/products/asmo-na/eng/compilers/flin/index.htm), which can be evaluated for free, IBM’s mpxlf90_r, and [gfortran](http://gcc.gnu.org/wiki/GFortran) among others. First, choose your fortran compiler and then install ScaLAPACK using that compiler (if it isn’t already installed on your computer).

You will need to request a copy of MUMPS using the [MUMPS request form](http://mumps.enseeiht.fr/index.php?page=dwnld#form). They will give you a link to the latest MUMPS public release.

To install ScaLAPACK on your system refer to the [instructions for installing Amesos_Scalapack](http://trilinos.org/oldsite/packages/amesos/scalapack_install.html)

To build MUMPS:

*   Untar MUMPS into your MUMPS directory: “tar xzf MUMPS_4.6.1.tar.gz”
*   Create a Makefile.inc, starting from one of the templates in the Make.inc directory.
    *   Set CC, FC, and FL (typically the same as FC, the fortran compiler)
    *   Set BLACSdir, BLACSFINIT, BLACSINIT and BLACSLIB to point to the BLACS libraries that you used in Amesos_Scalapack
    *   Set SCALIB to point to the ScaLAPACK library that you used in Amesos_Scalapack.
    *   Set OPTF, OPTC and OPTL to the compilation and link flags that wish to use.
    *   Set CDEFS to match INTFACE in Bmake.inc and CDEFS in SLmake.inc. Syntax is slightly different though.
*   make
*   Run the MUMPS example codes on four processors, on some machines this can be done as follows:
    *   “mpirun -np 4 c_example” expected result:

        <pre>Solution is : (    1.00      2.00)</pre>

    *   “mpirun -np 4 dsimpletest < input_simpletest_real” expected result ends in:

        <pre> ****** SOLVE & CHECK STEP ********

         STATISTICS PRIOR SOLVE PHASE     ...........
         NUMBER OF RIGHT-HAND-SIDES                    =           1
         BLOCKING FACTOR FOR MULTIPLE RHS              =           1
         ICNTL (9)                                     =           1
          --- (10)                                     =           0
          --- (11)                                     =           0
          --- (20)                                     =           0
          --- (21)                                     =           0
          Solution is   0.999999999999998        2.00000000000000     
           3.00000000000000        4.00000000000000        5.00000000000000</pre>

To build Amesos-Mumps:

*   Update your configure invocation script, making sure to specify your fortran compiler, something along the following lines:
    *   --enable-amesos-mumps F77=gfortran --with-lapack=”-llapack” --with-blas=”-lblas” --with-libs=”/home/kstanley/Trilinos3PL/MUMPS_4.6.1/MUMPS_4.6.1/lib/libdmumps.a /home/kstanley/Trilinos3PL/MUMPS_4.6.1/MUMPS_4.6.1/PORD/lib/libpord.a /home/username/Trilinos3PL/SCALAPACK/scalapack-1.7.3/libscalapack.a /home/username/Trilinos3PL/SCALAPACK/BLACS/LIB/blacsF77init_MPI-SGI5-0.a /home/username/Trilinos3PL/SCALAPACK/BLACS/LIB/blacs_MPI-SGI5-0.a “
    *   The lapack and blas libraries may or may not need to be listed explicitly and, in some cases, may need to be listed in the --with-libs line. If you are having trouble, you may want to try adding CXXFLAGS=-g to speed compilation.
*   Common Problems: Refer to the common problems section in [the Amesos_Scalapack installation guide](http://trilinos.org/oldsite/packages/amesos/scalapack_install.html).