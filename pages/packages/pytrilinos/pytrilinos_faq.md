---
title: PyTrilinos FAQ
permalink: pytrilinos_faq.html
folder: packages
---

# General Issues

**What is PyTrilinos?**

> PyTrilinos is a set of Python wrappers for selected Trilinos packages. This allows python programmers to access Trilinos classes dynamically from a python script or the python command-line interpreter.

**What Trilinos packages have python interfaces?**

> Currently, the list of PyTrilinos modules is
> 
> *   Amesos
> *   Anasazi
> *   AztecOO
> *   Epetra
> *   EpetraExt
> *   Galeri
> *   IFPACK
> *   Komplex
> *   LOCA (disabled in releases 7-10 and development branch)
> *   ML
> *   NOX (re-enabled in release 8)
> *   Pliris
> *   Teuchos
> *   Thyra (development branch only)
> *   TriUtils

**How do I use PyTrilinos?**

> If PyTrilinos is properly installed, then you should be able to import a PyTrilinos module such as <tt>Epetra</tt> with the python statement
> 
> > <tt>from PyTrilinos import Epetra</tt>
> 
> You can then use <tt>dir(Epetra)</tt> to get a list of classes and functions within the <tt>Epetra</tt> namespace, or <tt>help(Epetra)</tt> to get the <tt>Epetra</tt> documentation. As of release 7.0,
> 
> > <tt>from PyTrilinos import *</tt>
> 
> should import all PyTrilinos modules.

**When are you going to wrap** <tt>Package X</tt> **?**

> If you would like to see a particular package wrapped, send an email to the [PyTrilinos Lead Developer](mailto:wfspotz@sandia.gov), to help us prioritize which packages should be wrapped next.
> 
> NOX was recently resurrected, Anasazi was given a functioning python interface, and Pliris and Komplex were added. Our current priorities are to re-enable LOCA and to provide working wrappers for Thyra.

**Who should I contact if I have more questions?**

> Questions not answered by the information provided on the website should be directed to the [PyTrilinos Lead Developer](mailto:wfspotz@sandia.gov).

<div id="prerequisites">

# Prerequisites

**What are the required prerequisites for PyTrilinos?**

> PyTrilinos requires the following:
> 
> 1.  An installed version of [python](https://www.python.org), version 2.3 or higher. Some packages require the Boolean type introduced in python version 2.3, so this is a requirement for the whole package. Release 8.0 and the development branch of PyTrilinos have been upgraded to be compatible with python 2.6.
> 2.  The [NumPy module](http://www.numpy.org/), which provides contiguous data arrays, is required for release 7.0 and higher and the development branch. For earlier releases, [Numeric](http://www.numpy.org/old_array_packages.html) is required.
> 3.  The [swig package](http://www.swig.org), the Simple Wrapper Interface Generator, version 1.3.39 or better, is used to create the wrappers.
> 4.  All of the Trilinos prerequisites, such as BLAS and LAPACK, are also required.

**What are the optional prerequisites for PyTrilinos?**

> PyTrilinos can optionally use the following:
> 
> 1.  MPI. If Trilinos is configured to use MPI, then the PyTrilinos interface will be configured to use MPI as well.
> 2.  Expat, an XML parsing library optionally used by Teuchos.
> 3.  HDF5, a file format optionally supported by EpetraExt.
> 4.  The Amesos package can be optionally configured to support a variety of third-party solver libraries, also supported by the <tt>PyTrilinos.Amesos</tt> module:
> 
> > *   <tt>KLU</tt>
> > *   <tt>UMFPACK</tt>
> > *   <tt>ScaLAPACK</tt>
> > *   <tt>SuperLU</tt>
> > *   <tt>SuperLUDist</tt>
> > *   <tt>TAUCS</tt>
> > *   <tt>Pardiso</tt>
> > *   <tt>DSCPACK</tt>
> > *   <tt>MUMPS</tt>

</div>

<div id="configuration">

# Configuration

**How do I configure Trilinos to build the PyTrilinos python wrappers?**

> <dl>
> 
> <dt>**Release 10.0 and Development Branch** Run <tt>cmake</tt> with the</dt>
> 
> <dd>options <tt>-D Trilinos_ENABLE_PyTrilions:BOOL=ON</tt> and <tt>-D BUILD_SHARED_LIBS:BOOL=ON</tt>. To ensure that all PyTrilinos packages/modules are enabled, use <tt>-D Trilinos_ENABLE_ALL_OPTIONAL_PACKAGES:BOOL=ON</tt>.</dd>
> 
> </dl>

* * *

> **Release 8.0 or 9.0:** Enable PyTrilinos by configuring Trilinos with the <tt>--enable-pytrilinos</tt> configure option. If you want to choose a specific python, use <tt>--with-python=path</tt>.
> 
> This will enable python wrappers for each package that is both enabled and also supports a python interface. If you wish to disable the python interface to any enabled package, you can use <tt>--disable-pytrilinos-package</tt>, where <tt>package</tt> is replaced by the Trilinos package name.
> 
> If ML is enabled, as is the default, then you currently need to <tt>--enable-amesos</tt> as well in order to get PyTrilinos to compile correctly. You could also <tt>--disable-ml</tt> if you so choose.

* * *

> **Release 6.0 or 7.0:** Configure Trilinos with <tt>--enable-python[=path]</tt> or <tt>--with-python[=path]</tt>. These configure options trigger creation and compilation of wrapper code in the individual packages, and do not require that any particular package be enabled.
> 
> It is also possible to enable or disable the python wrappers for specific Trilinos packages, using <tt>--enable-package-python</tt> or <tt>--disable-package-python</tt>, where <tt>package</tt> is replaced by the package name.

* * *

> **Realease 5.0:** Make sure you are building a serial version and use the <tt>--enable-pytrilinos</tt> flag. You must also enable epetra, epetraext, nox and nox-epetra. When you perform a <tt>make install</tt>, the python modules will be installed in directories where the default python on your system can find them.

* * *

> If you need to specify where to find <tt>swig</tt>, configure with <tt>--with-swig=path</tt>.
> 
> If you wish to install PyTrilinos in a non-standard place, use the <tt>--prefix=PREFIX</tt> configure option to control where both Trilinos and PyTrilinos are installed.

</div>

<div id="building-and-installing-pytrilinos">

# Building and Installing PyTrilinos

For Trilinos Release 9.0 and earlier:

**I get a compilation error telling me that my BLAS or LAPACK (or some other third-party) library needs to be compiled with a** <tt>-fPIC</tt> **option. What’s up?**

> <tt>PIC</tt> stands for position-independent code, and is a requirement for shared libraries. Your third-party libraries need to be compiled with this option _and_ linked as shared (note that some operating systems, such as Mac OS X — which is what I develop on — create position-independent code by default and do not face this problem).
> 
> Older versions of PyTrilinos don’t require shared libraries, but they don’t work as well, either. Trilinos release 7.0 requires that Trilinos libraries be shared for MPI support. Release 8.0 and the development branch requires shared Trilinos libraries for serial as well.
> 
> Trilinos does not build its libraries as shared. The PyTrilinos package will go back and re-link as shared all of the Trilinos libraries. This is a somewhat ad-hoc process and is currently only supported for Linux and Mac OS X. This means that is you are compiling under Linux or Mac OS X, then your third-party libraries need to be shared.

**I get a whole slew of compilation errors, starting with a message that** <tt>Teuchos_any.hpp</tt> **has no match for** <tt>operator<<</tt>. **What is the problem?**

> This is a known problem with the python interface to ML. If ML is enabled (which is the default), then you should also enable Amesos (<tt>--enable-amesos</tt>) when you configure. If you don’t want or need ML, then you could disable it (<tt>--disable-ml</tt>) as an alternative.

**When the python wrappers for NOX are being built, there is a call to** <tt>swig</tt> **with a VERY long list of include files that dies without an error message. How can I fix it?**

> The problem is that the list of include files has a lot of duplicates in it and the list is too long for <tt>swig</tt> to handle. These duplicates will be stripped if you use GNU make and configure with <tt>--with-gnumake</tt>.

**How do I install PyTrilinos?**

> The command <tt>make install</tt>, run from the top build directory will install PyTrilinos. Run from within an enabled package build directory, this will install the individual PyTrilinos module. If you used the <tt>--prefix=PREFIX</tt> configuration option, make sure that your <tt>PREFIX</tt> is in your <tt>PYTHONPATH</tt> environment variable and the <tt>PREFIX/lib</tt> is in your <tt>LD_LIBRARY_PATH</tt> environment variable (<tt>DYLD_LIBRARY_PATH</tt> under Mac OS X).

</div>

<div id="numpy-and-numeric-issues">

# NumPy and Numeric Issues

**I have installed** <tt>numpy</tt>, **but the configure script says**

> <tt>failed to find required module numpy.lib.UserArray</tt>

**Why?**

> The <tt>numpy.lib.UserArray</tt> module was added to numpy in version 0.9.6, so this is an indication that your numpy module is too old. See the [NumPy homepage](http://www.numpy.org/). This has actually been fixed, and indicates that you have an obsolete version of PyTrilinos.

**I have installed numpy, but the configure script says**

> <tt>numpy/arrayobject.h not found</tt>

**Why?**

> NumPy gets installed in a somewhat non-standard place. Prior to Trilinos release 7.0, PyTrilinos did not know how to find it in a portable way. This should not happen, however, after release 7.0.
> 
> For earlier versions of the development branch, look in <tt>PREFIX/lib/python2.x/site-packages/numpy/core/include</tt>, where <tt>PREFIX</tt> is where python is installed and <tt>x</tt> is python minor version. I used to create a symbolic link from a place the compiler will find to this directory. This should only happen in an old copy of the development branch, so you should just make sure you have an updated veresion.

</div>

<div id="swig-issues">

# SWIG Issues

**I have an older version of** <tt>swig</tt> **installed. Do I really need the newer version?**

> Yes. [SWIG](http://www.swig.org) (Simple Wrapper Interface Generator) is the engine that produces most of the PyTrilinos code. Version 1.3.39 properly handles nested packages and sub-packages, which is needed for PyTrilinos.

**When I try to install** <tt>swig</tt>, **I get a lot of errors when I run ‘make check’. Is this a problem?**

> Probably not. PyTrilinos only cares that <tt>swig</tt> has the ability to produce python code, not any of the other languages that <tt>swig</tt> supports. Try:
> 
> <pre>$ make check-python-examples
> $ make check-python-test-suite</pre>
> 
> Even with these checks, a couple of errors is probably not a problem.

</div>

<div id="mpi-issues">

# MPI Issues

**How do I configure PyTrilinos with MPI support?**

> If you configure Trilinos with MPI support, then the PyTrilinos modules can be used in both serial and parallel (using MPI). In parallel, PyTrilinos requires a standard, out-of-the-box Python interpreter. Note that the MPI support for PyTrilinos requires shared libraries for BLAS, LAPACK and MPI. Currently, PyTrilinos has been successfully tested in parallel with OpenMPI and LAM/MPI only. There are known issues using MPICH mpirun.
> 
> For Trilinos releases prior to 7.0, you might also need shared libraries for the configured Trilinos packages (the release 7.0 version creates these shared libraries automatically). Under Linux/GCC, you can proceed as follows. Assuming <tt>Trilinos/LINUX_MPI</tt> is the installation directory for Trilinos, do:
> 
> <pre>$ cd Trilinos/LINUX_MPI
> $ <...configure Trilinos here...>
> $ make
> $ make install
> $ ../packages/PyTrilinos/make_shared_linux.sh</pre>
> 
> The last script contains the basic instructions to create shared libraries under LINUX/GCC. Then, you have to set the environmental variable <tt>LD_LIBRARY_PATH</tt> properly, for example under bash:
> 
> <pre>$ export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:${HOME}/Trilinos/LINUX_MPI/lib</pre>
> 
> There is a similar procedure for Mac OS X, which has its own script, and the applicable environment variable is <tt>DYLD_LIBRARY_PATH</tt>.

**How do I use PyTrilinos with MPI support?**

> If PyTrilinos is configured with MPI support, then importing the <tt>Epetra</tt> module will automatically call the <tt>MPI_Init()</tt> function and arrange for the <tt>MPI_Finalize()</tt> function to be called when the script exits. This should be done in a safe way that checks that it is legal to call either of these routines. For example, if you have already invoked <tt>MPI_Init()</tt> via, say, <tt>mpi4py</tt>, then importing <tt>Epetra</tt> should not raise an error.
> 
> Scripts must use an <tt>Epetra</tt> communicator. Within python, we recommend the <tt>Epetra.PyComm</tt> communicator, which returns an <tt>Epetra_MpiComm</tt> when PyTrilinos is compiled with MPI support and an <tt>Epetra_SerialComm</tt> otherwise. The script of course, must be written in a “parallel paradigm” that uses the communicator to translate between global and local ID values.
> 
> Execute the script in the normal way, typically by prefixing the script invocation with the usual MPI manager:
> 
> <pre>$ mpirun -np 4 python myScript.py</pre>
> 
> If PyTrilinos is installed properly, this should work. However, if the Trilinos libraries are in a non-standard place, then you will need to specify this by setting the <tt>LD_LIBRARY_PATH</tt> environment variable (Linux), or <tt>DYLD_LIBRARY_PATH</tt> (Mac OS X) and the export this variable with:
> 
> <pre>$ mpirun -x LD_LIBRARY_PATH -np 4 python myScript.py</pre>
> 
> We have also successfully run <tt>ipython</tt> with the <tt>ipython1</tt> module interactively controlling multiple processors; imported <tt>PyTrilinos</tt> modules in parallel; and created and manipulated distributed Trilinos objects. Contact the [PyTrilinos Lead Developer](mailto:wfspotz@sandia.gov) if have questions or are interested in such a capability.

</div>