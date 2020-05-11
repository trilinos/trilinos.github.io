---
title: Amesos Install
permalink: amesos_install.html
folder: packages
show_sidebar: true
contact: amesos-developers@software.sandia.gov
package: amesos
doxygen: true
---

## Quick Amesos Installation

Amesos can built with support for Amesos_Klu and Amesos_Lapack by adding --enable-amesos to your configure invocation.

## Full Amesos Installation

To use Amesos with Amesos_Dscpack, Amesos_Superludist, Amesos_Superlu and/or Amesos_Umfpack, you will need to compile the corresponding third party package: [DSCPACK](dscpack_install.html), [UMFPACK](umfpack_install.html), [SuperLU](superlu_install.html), and [SuperLU_MPI](superludist_install.html), and set two additional switches in the configure invocation. One switch to specify the package that you intend to link in and one to specify where that package has been built.

To use Amesos with Amesos_Dscpack, Amesos_Superludist, Amesos_Superlu and/or Amesos_Umfpack:

*   Enable one of the Amesos classes:
    *   --enable-amesos-dscpack
    *   --enable-amesos-superludist
    *   --enable-amesos-superlu
    *   --enable-amesos-umfpack
*   Specify where to find the third party code in one of the following ways:
    *   Specify the location of all third party libraries:
        *   --with-trilinos3pldir=/home/somedir/Trilinos3PL
    *   **-OR-**
    *   Specify the location of the third party libraries you intend to use, e.g:
        *   --with-libs=/home/somedir/SuperLU_DIST_2.0/SRC/libsuperludist.a
        *   --with-incdirs=-I/home/somedir/SuperLU_DIST_2.0/SRC

Debugging the instalation

Common error messages:

*   error: Cannot find SuperLU Dist library, specify a location using --with-libs …
    *   This messages indicates that configure was unable to link with the superludist library. Check packages/amesos/config.log for details in the section immediately above the line which says Cached variables.
    *   _NOTE:_ The following problem is now less common.
    *   A common problem with the superludist installation is that Superludist uses fortran as the linker, whereas amesos uses a C++ linker (often mpicc). If this is the case you will need to identify the libraries that you need to include in the link and then add them using one of the configure switches, such as “LDFLAGS= “.
    *   NOTE: As soon as “--with-libs= ” is implented, that will be the preferred option.
    *   Identifying the library which you are missing:
        *   Adding -v to the f77 link line will display the libraries which the fortran linker is including. From there, you can either use nm to find the library which satisfies the undefined external that is causing the problem or link in various files to see which one is needed.
    *   Debugging the link and build. We recommend that you break this into the following three steps:
        *   Make sure that you can build and link with mpi and --enable-amesos (but without --enable-amesos-superludist).
        *   Perform an amesos-only configure.
            *   To do this, cp config.log in packages/amesos to RunConfig.csh (or any other name), edit it to add quote marks around any parameters that were quoted in the original configuration invocation, and run it.
        *   Link with whichever linker configure is trying to link superludist with. cp config.log to two files: conftest.c and linkconf.csh.
            *   Edit conftest.c so that it includes only the conftest.c code which configure is attempting to link the superludist ibrary to.
            *   Edit linkconf.csh so that includes only the link line which configure is using.
        *   Run linkconf.sh -- make sure that you get the same error as what appears in config.log.
        *   Edit linkconf.sh until the link succeeds.
    *   Add “LDFLAGS= ” or “--with-libs= ” (if implemented) to the amesos-only configuration script: RunConfig.csh and run it to make sure that it works.
    *   Now add the --with-libs or “LDFLAGS= ” option to the Trilinos level configuration script and rerun that.

Testing

Amesos provides tests and examples. The examples typically require a minute or two to complete. The tests require close to an hour on some architectures.

The easiest way to invoke the examples is:

<pre>cd packages/amesos
make run-examples</pre>

The easiest way to invoke a series of tests that should take no more than an hour in total is:

<pre>cd packages/amesos
make run-tests</pre>

The easiest way to invoke all Amesos tests is:

<pre>cd packages/amesos
make run-tests</pre>

If “a_trivial_mpi_test” fails, or if a large number of tests fail, there could be a problem with the underlying mpi system. Try running “lamboot” and re-running the tests.
