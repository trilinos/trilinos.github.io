---
title: Amesos SuperLU MPI Install
permalink: amesos-superlu-mpi-install.html
folder: packages
---

SuperLU MPI Installation

_NOTE:_ These intructions were updated in September 2005\. They may not be kept up-to-date. Refer to the SuperLU documentation for more recent and more complete instructions.

SuperLU MPI must be installed before Amesos_Superludist can be used. Follow these steps to install SuperLU MPI on your system:

*   Obtain the distribution from [Xiaoye Li’s SuperLU web site](http://crd-legacy.lbl.gov/~xiaoye/SuperLU/) by clicking on the download link in the “SuperLU_DIST Version 2.0” section.
*   Untar the SuperLU dist code in your Trilinos3PL directory.
*   Build SuperLU MPI
    *   Follow the intructions in README (edit make.inc, ‘make lib’), ignoring the section on MATLAB
    *   Note:Trilinos3PL/config/SuperLU_DIST_2.0 contains the make.inc files that I used.
*   Run an example:
    *   Follow the instructions in EXAMPLE/README:
        *   cd EXAMPLE
        *   make pddrive
        *   mpirun -np 4 pddrive -r 1 -c 4 g20.rua
    *   Expected output:

        <pre>(0) .. ||X-Xtrue||/||X|| = 1.110223e-15
                EQUIL time             0.01
                COLPERM time           0.00
                ROWPERM time           0.02
                SYMBFACT time          0.00
                DISTRIBUTE time        0.01
                FACTOR time            0.05
                Factor flops    9.957800e+04    Mflops      2.11
                SOLVE time             0.03
                Solve flops     3.325800e+04    Mflops      1.18
                REFINEMENT time        0.03     Steps       1</pre>

*   Update your configure invocation script by, for example, adding the following:
    *   --enable-amesos-superludist
    *   --with-libs=”-L/home/username/Trilinos3PL/SuperLU_DIST_2.0 -lsuperludist” or --with-libs=”/home/username/Trilinos3PL/SuperLU_DIST_2.0/libsuperludist.a”
    *   --with-incdirs=”-I/home/username/Trilinos3PL/SuperLU_DIST_2.0/SRC”


