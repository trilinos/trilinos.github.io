---
title: Amesos ScaLAPACK Install
permalink: amesos-scalapack-install.html
folder: archive
---

## ScaLAPACK Installation

_NOTE:_ These intructions were updated in June 2006\. They may not be kept up-to-date. Refer to the [ScaLAPACK website](http://www.netlib.org/scalapack/) for more recent and more complete instructions.

ScaLAPACK must be available on your system before Amesos_Scalapack or Amesos_Mumpscan be used. ScaLAPACK is provided in many high performance libraries, including the Cray Scientific Library (-lsci), Silicon Graphic’s (-lsdsm), Hewlett Packard’s MLIB, Intel’s MKL. Some IBM scientific libraries also support ScaLAPACK. Many high performance computer installations include ScaLAPACK. Hence, it is worth checking to see if ScaLAPACK is already installed on your computer.

Even if ScaLAPACK is available on your system, you may need to build it from the original sources if you are using a different fortran compiler.

To install ScaLAPACK on your system you will need the BLAS and the BLACS. The BLAS are almost certainly installed on your system, but the BLACS are often not installed unless SacaLAPACK is.

To install the BLACS on your system:

*   Obtain the distribution from the [BLACS website](http://www.netlib.org/blacs/) You will need both [mpiblacs.tgz](http://www.netlib.org/blacs/mpiblacs.tgz) and [mpiblacs-patch03.tgz](http://www.netlib.org/blacs/mpiblacs-patch03.tgz). Getting [blacstester.tgz](http://www.netlib.org/blacs/blacstester.tgz) is also wise.
*   Untar these three into the same directory.
*   Edit Bmake.inc, starting from one of the templates in BMAKES/Bmake.inc.
    *   Set BTOPdir to point to the directory that the BLACS are in (generally ends in BLACS)
    *   Set F77, CC, MPIINCdir and MPILIB.
        *   MPIINCdir should be set to a directory including mpif.h.
        *   MPILIB can be left blank if F77=mpif77 and CC=mpicc
    *   Set PLAT to a character string representing your platform (optional).
    *   Follow the directions in BLACS/INSTALL/README. The BLACS/INSTALL directory contains several small routines which will help you set Bmake.inc variables INTFACE and TRANSCOMM and may warn you of more serious problems with your mpi implementation. Note: the executables are placed in the EXE subdirectory.
    *   Type “make mpi” in the BLACS directory to build the BLACS.
    *   Type “cd TESTING; make” to build the BLACS tester (note, the blacs tester takes close to a minute to compile)
    *   Run the blacs tester on 4 processes. On many machines, this can be done with: “cd EXE; mpirun -np 4 xFbtest_MPI-…-0” or “cd EXE; mpirun -np 4 xCbtest_MPI-…-0”
    *   Don’t give up if the BLACS tester fails. It is important that the testers link, but sometimes blacs installations that cause the BLACS tester to fail still work. On one system, the BLACS tests all gave this error message: “MPI Error, rank:0, function:MPI_TYPE_INDEXED, Invalid count argument” but the ScaLAPACK and Amesos_ScaLAPACK installation tests both passed.

To install ScaLAPACK on your system, install the BLACS first(see above), then:

*   Obtain the latest distribution from the [SCALAPACK website](http://www.netlib.org/scalapack/). As of May 2006, the latest distribution is [scalapack-1.7.3.tgz](http://www.netlib.org/scalapack/scalapack-1.7.3.tgz), but you should check for patches and later distributions.
*   Untar the ScaLAPACK code: “tar xzf scalapack-1.7.3.tgz”. Typically this is done in the same directory that you untarred the BLACS code (it will create a scalapack-1.7.3 directory).
*   Edit SLmake.inc.
    *   home to the directory that the ScaLAPACK code resides in. For version 1.7.3, this will end in scalapack-1.7.3\. For earlier versions, it tyically ends in SCALAPACK.
    *   Set PLAT to the same staing that you set it to for the BLACS in the Bmake.inc file (optional).
    *   Set BLACSdir to the directory that the BLACS library files are in (typically ends in BLACS/LIB)
    *   Set F77, CC. Typically (almost always) these are the same compilers used to compile the BLACS.
    *   Set CDEFS to the flags you wish to pass to the C compiler (typically this includes the flags you set in INTFACE in Bmake.inc).
    *   Set SMPLIB to point to your mpi library (typically -lmpi). May be left blank if you use F77=mpif77 and CC=mpicc
    *   Set BLASLIB to point to the BLAS library.
    *   Set BLACSFINIT, BLACSCINIT and BLACSLIB. If you set BLACSdir and PLAT right, you may not have to change these.
*   Type: “make” in the same directory that SLmake.inc is in to build the ScaLAPACK library. Takes several minutes.
*   Check to see that libscalapacl.a was built in this directory.
*   Type: “cd TESTING/LIN; make” to build the linear solver testers. Takes several minutes.
*   Type: “cd ..” to change back to the TESTING directory. Then run xdlu < LU.dat on four processes. On many computers this can be done with “mpirun -np 4 xdlu The results should end with:

    <pre>Finished    240 tests, with the following results:
      240 tests completed and passed residual checks.
        0 tests completed and failed residual checks.
        0 tests skipped because of illegal input values.

    END OF TESTS.</pre>

To build Amesos-Scalapack:

*   Update your configure invocation script by, for example, adding something along the following lines:

    *   --enable-amesos-scalapack F77=gfortran --with-lapack=”-llapack” --with-blas=”-lblas” --with-libs=”/home/username/Trilinos3PL/SCALAPACK/scalapack-1.7.3/libscalapack.a /home/username/Trilinos3PL/SCALAPACK/BLACS/LIB/blacsF77init_MPI-SGI5-0.a /home/username/Trilinos3PL/SCALAPACK/BLACS/LIB/blacs_MPI-SGI5-0.a “
    *   The lapack and blas libraries may or may not need to be listed explicitly and, in some cases, may need to be listed in the --with-libs line. If you are having trouble, you may want to try adding CXXFLAGS=-g to speed compilation.
    
*   **Common problems:** Both undefined externals and multiply defined externals can prevent Trilions from either configuring or building. Two routines, xerbla and lsame, are included in multiple libraries. In general, this should not be a problem, but in some cases, it can be.xerbla and pxerbla the only routines in the scalapack/lapack/blas suite that print. Different fortran compilers use different routines for printing. g77 uses: s_wsfe, do_fio, e_wsfe and s_stop. ifort uses: for_write_seq_fmt, for_write_seq_fmt_xmit and for_stop_core. g95 uses: g95_st_write, g95_stop_blank and others. gfortran uses: gfortran_st_write, gfortran_stop_numeric and others. If any of these routines are listed as undefined by the link step, you may be mixing codes compiled by more than one fortran compiler.Compiling [xerbla.f](http://www.netlib.org/blas/xerbla.f) with the fortran compiler that you intend to use and examining it with “nm xerbla.o” will tell you which routines your fortran compiler uses in its runtime library.

    If the blas library that you are using were compiled by a compiler other than the compiler that you are using, you will either have to link fortran run time libraries from both compilers (not recommended) or make sure that a xerbla.o built by the fortran compiler that you are using gets linked in prior to that blas library. This can be accomplished by listing a library with the correctly compiled xerbla.o in the --with-blas= switch. For example, in one implementation, I added libscalapack.a to the front of the --with-blas command because it had a xerbla.o complied with the fortran compiler that I wanted to use (an f90 compiler for MUMPS). Hence, my configuration invocation included: --with-blas=”/home/kstanley/Trilinos3PL/SCALAPACK/scalapack-1.7.3/libscalapack.a -L/home/kstanley/Linux_IA64Itan_2/lib -lcblas -lf77blas -latlas ” In some cases, it may be necessary (or expedient) to remove xerbla.o and lsame.o from a pre-compiled library. This can often be done with: “ar d libname.a xerbla.o; ar d libname.a lsame.o”

    Problems with incompatible blas libraries often show up as configuration or link errors in the teuchos package as that is the first package to be configured and built in Trilinns.

    Undefined externals in the link phase mean either that object files which you don’t want are being linked in (typically xerbla.o produced by a different fortran compiler than the one you are using) or that you are not linking needed files. If the link step is including files that you do not want, get rid of them, either by eliminating them from the link line, or if that is not possible (for example, a xerbla.o file in a library that you wish to use but which was compiled by a different fortran compiler than the one you want to use) you will need to ensure that the offending file is not linked in by ensuring that the entry point which it satisfies is linked before it in the link step. See the description above for how we convinced the linker to include xerbla.o from libscalack.a instead of the blas.

    If the undefined externals stem from a file that you do wish to include in the link, you will need to include the libraries which satisfy these externals. Linking fortran codes in a link performed by a call to a C++ compiler (as Trilinos typically does) requires that the fortran libraries be listed explicitly. If you don’t know which files contain the fortran runtime libraries that you need, link a trivial fortran code using te fortran compiler as the linker, then add “-v” to that link step to show the files included in the link. Alternatively, you can use “-Wl,--print-map” which will usually cause the linker to print a link map.

    If the names of routines that are typically written in fortran, such as scalapack, lapack or blas routines, are not found by the linker, it is possible that the wrong form of external names is being used. Some fortran compilers use all capital letters for external names, most use lowercase name with a single underscore appended to the end. But, some use lowercase without appending an underscore and some fortran compilers append an additional underscore to routines which include an underscore in their names (like sl_init or blacs_gridinit). “nm” can be used to determine which convention is used in the lapack, scalapack and blas libraries that you are using (if the three libraries do not all stick to the same naming conventino for the entry points, you will probably need to recompile one or more of those libraries). If the Trilinos link step is failing as a result of different fortran naming conventions, Trilinos may be using a different compiler than the one that was used to compile the libraries that you are using.

    If the link works, but the execution fails because a shared library file could not be found, you will need to change the environment variable LD_LIBRARY_PATH. This is typically done in .cshrc, .profile or .bashrc.

    If the configuration fails, the file packages/failing_package/config.log will contain some information about the failure. Often, repeating the last attempt to compile conftest.c as shown in config.log (both conftest.cc and the command used to compile and link it are saved in config.log) will provide useful information. I typically play with this until that compilation and link works before trying another Trilinos configuration.
