---
title: PyTrilinos FAQ
permalink: pytrilinos_faq.html
folder: archive
show_sidebar: true
contact: wfspotz@sandia.gov
package: pytrilinos
---

## General Issues

### What is PyTrilinos?

PyTrilinos is a set of Python wrappers for selected Trilinos packages. This allows python programmers to access Trilinos classes dynamically from a python script or the python command-line interpreter.

### What Trilinos packages have python interfaces?

Currently, the list of PyTrilinos modules is
 
*   Amesos
*   Anasazi
*   AztecOO
*   Epetra
*   EpetraExt
*   Galeri
*   IFPACK
*   Komplex
*   LOCA (disabled in releases 7-10 and development branch)
*   ML
*   NOX (re-enabled in release 8)
*   Pliris
*   Teuchos
*   Thyra (development branch only)
*   TriUtils

### How do I use PyTrilinos?

If PyTrilinos is properly installed, then you should be able to import a PyTrilinos module such as Epetra with the python statement

from PyTrilinos import Epetra

You can then use dir(Epetra) to get a list of classes and functions within the Epetra namespace, or help(Epetra) to get the Epetra documentation. As of release 7.0,

from PyTrilinos import *
 
should import all PyTrilinos modules.

### When are you going to wrap **Package X**?

If you would like to see a particular package wrapped, send an email to the [PyTrilinos Lead Developer](mailto:wfspotz@sandia.gov), to help us prioritize which packages should be wrapped next.

NOX was recently resurrected, Anasazi was given a functioning python interface, and Pliris and Komplex were added. Our current priorities are to re-enable LOCA and to provide working wrappers for Thyra.

### Who should I contact if I have more questions?

Questions not answered by the information provided on the website should be directed to the [PyTrilinos Lead Developer](mailto:wfspotz@sandia.gov).

## Prerequisites

### What are the required prerequisites for PyTrilinos?

PyTrilinos requires the following:
 
1.  An installed version of [python](https://www.python.org), version 2.3 or higher. Some packages require the Boolean type introduced in python version 2.3, so this is a requirement for the whole package. Release 8.0 and the development branch of PyTrilinos have been upgraded to be compatible with python 2.6.
2.  The [NumPy module](http://www.numpy.org/), which provides contiguous data arrays, is required for release 7.0 and higher and the development branch. For earlier releases, [Numeric](http://www.numpy.org/old_array_packages.html) is required.
3.  The [swig package](http://www.swig.org), the Simple Wrapper Interface Generator, version 1.3.39 or better, is used to create the wrappers.
4.  All of the Trilinos prerequisites, such as BLAS and LAPACK, are also required.

### What are the optional prerequisites for PyTrilinos?

PyTrilinos can optionally use the following:
 
1.  MPI. If Trilinos is configured to use MPI, then the PyTrilinos interface will be configured to use MPI as well.
2.  Expat, an XML parsing library optionally used by Teuchos.
3.  HDF5, a file format optionally supported by EpetraExt.
4.  The Amesos package can be optionally configured to support a variety of third-party solver libraries, also supported by the PyTrilinos.Amesos module:
    *   KLU
    *   UMFPACK
    *   ScaLAPACK
    *   SuperLU
    *   SuperLUDist
    *   TAUCS
    *   Pardiso
    *   DSCPACK
    *   MUMPS

## Configuration

### How do I configure Trilinos to build the PyTrilinos python wrappers?

 
 
 **Release 10.0 and Development Branch** Run cmake with the
 
 options -D Trilinos_ENABLE_PyTrilions:BOOL=ON and -D BUILD_SHARED_LIBS:BOOL=ON. To ensure that all PyTrilinos packages/modules are enabled, use -D Trilinos_ENABLE_ALL_OPTIONAL_PACKAGES:BOOL=ON.

* * *

 **Release 8.0 or 9.0:** Enable PyTrilinos by configuring Trilinos with the --enable-pytrilinos configure option. If you want to choose a specific python, use --with-python=path.
 
 This will enable python wrappers for each package that is both enabled and also supports a python interface. If you wish to disable the python interface to any enabled package, you can use --disable-pytrilinos-package, where package is replaced by the Trilinos package name.
 
 If ML is enabled, as is the default, then you currently need to --enable-amesos as well in order to get PyTrilinos to compile correctly. You could also --disable-ml if you so choose.

* * *

 **Release 6.0 or 7.0:** Configure Trilinos with --enable-python[=path] or --with-python[=path]. These configure options trigger creation and compilation of wrapper code in the individual packages, and do not require that any particular package be enabled.
 
 It is also possible to enable or disable the python wrappers for specific Trilinos packages, using --enable-package-python or --disable-package-python, where package is replaced by the package name.

* * *

 **Realease 5.0:** Make sure you are building a serial version and use the --enable-pytrilinos flag. You must also enable epetra, epetraext, nox and nox-epetra. When you perform a make install, the python modules will be installed in directories where the default python on your system can find them.

* * *

 If you need to specify where to find swig, configure with --with-swig=path.
 
 If you wish to install PyTrilinos in a non-standard place, use the --prefix=PREFIX configure option to control where both Trilinos and PyTrilinos are installed.

## Building and Installing PyTrilinos

For Trilinos Release 9.0 and earlier:

**I get a compilation error telling me that my BLAS or LAPACK (or some other third-party) library needs to be compiled with a** -fPIC **option. What’s up?**

 PIC stands for position-independent code, and is a requirement for shared libraries. Your third-party libraries need to be compiled with this option _and_ linked as shared (note that some operating systems, such as Mac OS X — which is what I develop on — create position-independent code by default and do not face this problem).
 
 Older versions of PyTrilinos don’t require shared libraries, but they don’t work as well, either. Trilinos release 7.0 requires that Trilinos libraries be shared for MPI support. Release 8.0 and the development branch requires shared Trilinos libraries for serial as well.
 
 Trilinos does not build its libraries as shared. The PyTrilinos package will go back and re-link as shared all of the Trilinos libraries. This is a somewhat ad-hoc process and is currently only supported for Linux and Mac OS X. This means that is you are compiling under Linux or Mac OS X, then your third-party libraries need to be shared.

**I get a whole slew of compilation errors, starting with a message that** Teuchos_any.hpp **has no match for** operator<<. **What is the problem?**

 This is a known problem with the python interface to ML. If ML is enabled (which is the default), then you should also enable Amesos (--enable-amesos) when you configure. If you don’t want or need ML, then you could disable it (--disable-ml) as an alternative.

**When the python wrappers for NOX are being built, there is a call to** swig **with a VERY long list of include files that dies without an error message. How can I fix it?**

 The problem is that the list of include files has a lot of duplicates in it and the list is too long for swig to handle. These duplicates will be stripped if you use GNU make and configure with --with-gnumake.

**How do I install PyTrilinos?**

 The command make install, run from the top build directory will install PyTrilinos. Run from within an enabled package build directory, this will install the individual PyTrilinos module. If you used the --prefix=PREFIX configuration option, make sure that your PREFIX is in your PYTHONPATH environment variable and the PREFIX/lib is in your LD_LIBRARY_PATH environment variable (DYLD_LIBRARY_PATH under Mac OS X).

## NumPy and Numeric Issues

**I have installed** numpy, **but the configure script says**

 failed to find required module numpy.lib.UserArray

**Why?**

 The numpy.lib.UserArray module was added to numpy in version 0.9.6, so this is an indication that your numpy module is too old. See the [NumPy homepage](http://www.numpy.org/). This has actually been fixed, and indicates that you have an obsolete version of PyTrilinos.

**I have installed numpy, but the configure script says**

 numpy/arrayobject.h not found

**Why?**

 NumPy gets installed in a somewhat non-standard place. Prior to Trilinos release 7.0, PyTrilinos did not know how to find it in a portable way. This should not happen, however, after release 7.0.
 
 For earlier versions of the development branch, look in PREFIX/lib/python2.x/site-packages/numpy/core/include, where PREFIX is where python is installed and x is python minor version. I used to create a symbolic link from a place the compiler will find to this directory. This should only happen in an old copy of the development branch, so you should just make sure you have an updated veresion.

## SWIG Issues

**I have an older version of** swig **installed. Do I really need the newer version?**

 Yes. [SWIG](http://www.swig.org) (Simple Wrapper Interface Generator) is the engine that produces most of the PyTrilinos code. Version 1.3.39 properly handles nested packages and sub-packages, which is needed for PyTrilinos.

**When I try to install** swig, **I get a lot of errors when I run ‘make check’. Is this a problem?**

 Probably not. PyTrilinos only cares that swig has the ability to produce python code, not any of the other languages that swig supports. Try:
 
    $ make check-python-examples
    $ make check-python-test-suite
 
Even with these checks, a couple of errors is probably not a problem.

## MPI Issues

**How do I configure PyTrilinos with MPI support?**

 If you configure Trilinos with MPI support, then the PyTrilinos modules can be used in both serial and parallel (using MPI). In parallel, PyTrilinos requires a standard, out-of-the-box Python interpreter. Note that the MPI support for PyTrilinos requires shared libraries for BLAS, LAPACK and MPI. Currently, PyTrilinos has been successfully tested in parallel with OpenMPI and LAM/MPI only. There are known issues using MPICH mpirun.
 
 For Trilinos releases prior to 7.0, you might also need shared libraries for the configured Trilinos packages (the release 7.0 version creates these shared libraries automatically). Under Linux/GCC, you can proceed as follows. Assuming Trilinos/LINUX_MPI is the installation directory for Trilinos, do:
 
    $ cd Trilinos/LINUX_MPI
    $ <...configure Trilinos here...
    $ make
    $ make install
    $ ../packages/PyTrilinos/make_shared_linux.sh
 
 The last script contains the basic instructions to create shared libraries under LINUX/GCC. Then, you have to set the environmental variable LD_LIBRARY_PATH properly, for example under bash:
 
    $ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:${HOME}/Trilinos/LINUX_MPI/lib
 
 There is a similar procedure for Mac OS X, which has its own script, and the applicable environment variable is DYLD_LIBRARY_PATH.

**How do I use PyTrilinos with MPI support?**

 If PyTrilinos is configured with MPI support, then importing the Epetra module will automatically call the MPI_Init() function and arrange for the MPI_Finalize() function to be called when the script exits. This should be done in a safe way that checks that it is legal to call either of these routines. For example, if you have already invoked MPI_Init() via, say, mpi4py, then importing Epetra should not raise an error.
 
 Scripts must use an Epetra communicator. Within python, we recommend the Epetra.PyComm communicator, which returns an Epetra_MpiComm when PyTrilinos is compiled with MPI support and an Epetra_SerialComm otherwise. The script of course, must be written in a “parallel paradigm” that uses the communicator to translate between global and local ID values.
 
 Execute the script in the normal way, typically by prefixing the script invocation with the usual MPI manager:
 
    $ mpirun -np 4 python myScript.py
 
 If PyTrilinos is installed properly, this should work. However, if the Trilinos libraries are in a non-standard place, then you will need to specify this by setting the LD_LIBRARY_PATH environment variable (Linux), or DYLD_LIBRARY_PATH (Mac OS X) and the export this variable with:
 
    $ mpirun -x LD_LIBRARY_PATH -np 4 python myScript.py
 
 We have also successfully run ipython with the ipython1 module interactively controlling multiple processors; imported PyTrilinos modules in parallel; and created and manipulated distributed Trilinos objects. Contact the [PyTrilinos Lead Developer](mailto:wfspotz@sandia.gov) if have questions or are interested in such a capability.
