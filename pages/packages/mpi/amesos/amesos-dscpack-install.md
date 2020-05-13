---
title: Amesos DSCPACK Install
permalink: amesos-dscpack-install.html
folder: packages
---

## DSCPACK Installation

_NOTE:_ These intructions were updated in September 2005\. They may not be kept up-to-date. Refer to the SuperLU documentation for more recent and more complete instructions.

DSCPACK must be installed before Amesos_Dscpack can be used. Follow these steps to install DSCPACK on your system:

*   Obtain the DSCPACK distribution from [Padma Raghavan’s DSCPACK web site](http://www.cse.psu.edu/%7Eraghavan/Dscpack). You will have to submit a form asking for a password.
*   Untar the DSCPACK code in your Trilinos3PL directory.
*   Build DSCPACK
    *   Edit DSCPACK1.0/DSC_LIB/Makefile to use the correct compilers for your system.
    *   Note:Trilinos3PL/config/DSCPACK1.0/DSC_LIB contains the Makefile files that I used.
    *   cd DSCPACK1.0/DSC_LIB; make lib_dbl
*   Build and run an example:
    *   Edit DSCPACK1.0/Makefile to use the correct compilers for your system and include MPI and BLAS libraries.
    *   Note:Trilinos3PL/config/DSCPACK1.0 contains the Makefile files that I used.
    *   make all
    *   mpirun -np 2 ./Solve1 2 3 4 1 1 1 1 2 1
    *   Expected output:

        <pre>...starting with 2 processors in solver group

        ...Grid  2X 3X 4, Order 1, Factor 1, Solve  1, RHS 1, Processor 2, 
         NumLocalNonz = 35
        Stats after Matrix number 1 [1]

        _________________________________________________________________________________________________________
                            P       Type       rank     |A|(K)  #solves         sol-err       count-err          sample
                            2     TS-LLT         24       0.07        1    0.0000000000    0.0000000000    1.0000000000
                    O-time(s)  S-time(s)  N-time(s)   N-ops(M)  N-rate(M)     |L|(K) SO-time(s)  SO-ops(M) SO-rate(M) 
               min       0.00       0.00       0.00       0.00       0.52       0.07       0.00       0.00       ----
               max       0.00       0.00       0.00       0.00       0.55       0.07       0.00       0.00       ----
           overall       ----       ----       ----       0.00       0.96       0.15       ----       0.00       1.14
              Memory(Mbytes)        min        max    overall
                    Estimate       0.00  NumLocalNonz = 35
              0.00       0.01
                    Observed       0.00       0.00       0.01
              Observed L-mem       0.00       0.00       0.00
              Observed stack       0.00       0.00       0.00
                Solve-memory       0.00       0.00       0.00

        _________________________________________________________________________________________________________</pre>

*   Update your configure invocation script by, for example, adding the following:
    *   --enable-amesos-dscpack
    *   --with-libs=”-L/home/username/Trilinos3PL/DSCPACK1.0/DSC_LIB” or --with-libs=”/home/username/Trilinos3PL/DSCPACK1.0/DSC_LIB/dsclibdbl.a”
    *   --with-incdirs=”-I/home/username/Trilinos3PL/DSCPACK1.0/DSC_LIB”