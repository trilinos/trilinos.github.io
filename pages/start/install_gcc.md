---
title: Install GCC
permalink: install_gcc.html
folder: start
---

# Installing GCC

Starting with Trilinos 12.0 (and after Trilinos 11.14 on the development branch), some Trilinos packages, including Kokkos and Tpetra, will begin to require certain features from C++11 that will require a minimum GCC version of 4.7.2\. Some common machines (Enterprise Linux 6, OSX) do not meet this minimum requirement.

There are several ways that a person can get a new version of GCC. For OSX in particular, most people have needed to install their own compilers to use Trilinos for a long time. Common solutions include MacPorts, Fink, hpc.sourceforge, and others. The Trilinos Project does not endorse any specific solution. However, on this page, we offer some information for people looking to install GCC from source for OSX or Linux, and also mention the CentOS devtoolset as another possible solution.

Installing GCC from source has gotten much simpler than it used to be thanks to a download_prerequisites script that removes the need to separately build required packages like mpfr, gmp, and mpc. This seems to work well with GCC 4.7.2, but as of January 2015, does not seem to work cleanly with GCC 4.9.

If you try the below instructions and see errors or omissions, please send a note to trilinos-framework@software.sandia.gov.

## Installing GCC from source

Note all instructions are for bash, most will work in all shells however, when setting the environment you may need to convert that to your shell’s commands.

1.Set proxy

At Sandia only, if you have not already done so, you will need to set your http and https proxies. Contact a system administrator or trilinos-framework@software.sandia.gov if you need assistance.

2\. mkdir gcc_hold

3\. cd gcc_hold

4\. Download gcc-4.7.2 source code

Linux:  
wget http://mirrors-usa.go-parts.com/gcc/releases/gcc-4.7.2/gcc-4.7.2.tar.bz2

mac:  
curl -O http://mirrors-usa.go-parts.com/gcc/releases/gcc-4.7.2/gcc-4.7.2.tar.bz2

5\. tar -xjvf gcc-4.7.2.tar.bz2

6\. cd gcc-4.7.2

7\. contrib/download_prerequisites

8\. cd ..

9\. mkdir 4.7.2_build

10\. cd 4.7.2_build

11\. ../gcc-4.7.2/configure --enable-multilib --prefix=<gcc 4.7.2 install path> --enable-languages=c,c++,fortran  
Optionally, the Gold linker can be enabled with --enable-gold

12\. make -j <n> 2>&1 |tee make.out  
Where <n> is a reasonable number of procs to use when compiling

13\. make install (assuming make was clean)

13a. It may also be necessary to install the prerequisite packages to compile some other packages with the installed GCC:

$ for i in mpfr/ mpc/ gmp/; do cd $i; make install; cd ..; done

14\. cd ..

## Installing OpenMPI from source

15\. Download openmpi 1.6.5

Linux:  
wget http://www.open-mpi.org/software/ompi/v1.6/downloads/openmpi-1.6.5.tar.gz

Mac:  
curl -O http://www.open-mpi.org/software/ompi/v1.6/downloads/openmpi-1.6.5.tar.gz

16\. tar -xzvf openmpi-1.6.5.tar.gz

17\. mkdir 4.7.2_openmpi_build

18\. cd 4.7.2_openmpi_build

19\. Set LD_LIBRARY_PATH to point to gcc-4.7.2 for OpenMPI build

export LD_LIBRARY_PATH=<gcc 4.7.2 install path>/lib64

20\. ../openmpi-1.6.5/configure CC=<gcc 4.7.2 install path>/bin/gcc CXX=<gcc 4.7.2 install path>/bin/g++ FC=<gcc 4.7.2 install path>/bin/gfortran F77=<gcc 4.7.2 install path>/bin/gfortran --enable-mpi-thread-multiple --prefix=<openmpi install path>

21\. make -j <n> 2>&1 |tee make.out  
Where n is a reasonable number of procs to use when compiling

22\. make install (assuming make was clean)

23\. Update your environment to point to the new compilers. This should be done in your shell’s rc or profile if you want to use the new compiler and mpi in your default environment.

export PATH=<gcc 4.7.2 install path>/bin:<openmpi install path>/bin:$PATH  
export LD_LIBRARY_PATH=<gcc 4.7.2 install path>/lib64:<openmpi install path>/lib:$LD_LIBRARY_PATH

On mac you will also need to set the DYLD_LIBRARY_PATH  
export DYLD_LIBRARY_PATH=<gcc 4.7.2 install path>/lib64:<openmpi install path>/lib:$DYLD_LIBRARY_PATH

You may also want to set some other values in your environment, depending on your typical usage:

export CC=<gcc 4.7.2 install path>/bin/gcc
export CXX=<gcc 4.7.2 install path>/bin/g++
export FC=<gcc 4.7.2 install path>/bin/gfortran
export F77=<gcc 4.7.2 install path>/bin/gfortran

24\. optional. If you’d like to reclaim the disk space used to build gcc and openmpi it is now safe to delete the gcc_hold dir.

## Devtoolset installation

We are working on a solution that would provide the GCC 4.8.1 compiler through the CentOS devtoolset. This option still involves installing OpenMPI from source. If you are interested in trying this option, please contact trilinos-framework@software.sandia.gov.