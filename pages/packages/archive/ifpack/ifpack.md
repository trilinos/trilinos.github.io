---
title: IFPACK
permalink: ifpack.html
folder: archive
show_sidebar: true
contact: maherou@sandia.gov
package: ifpack
doxygen: true
---

![IFPACK Logo](images/ifpack.png)    

**Welcome to the IFPACK Home**

IFPACK provides a suite of object-oriented algebraic preconditioners for the solution of preconditioned iterative solvers. IFPACK constructors expect an Epetra_RowMatrix object for construction. IFPACK is part of the Trilinos Solver Project and IFPACK object interact well with other Trilinos classes. In particular, IFPACK can be used as a preconditioner for [AztecOO](aztecoo.html).  
IFPACK documentation is created and maintained using Doxygen; the latest Doxygen documentation, containing details about IFPACK and its classes, examples of usage, and more, is accessible [here](docs/dev//ifpack/index.html).

If you use IFPACK for your applications, please let us know by writing an e-mail to the [IFPACK developers](http://trilinos.org/oldsite/packages/ifpack/team.html). Please also cite IFPACK using the following bibtex entry:

    @TechReport{ifpack-guide,
        author      =  {M. Sala and M. Heroux},
        title       =  {Robust Algebraic Preconditioners with {IFPACK} 3.0},
        institution =  {Sandia National Laboratories},
        year        =  {2005},
        number      =  {SAND-0662},
    </pre>

<span style="text-decoration: underline;">**Overview**</span>

IFPACK provides a suite of object-oriented algebraic preconditioners for the solution of preconditioned iterative solvers. IFPACK constructors expect an Epetra_RowMatrix object for construction. IFPACK is part of the Trilinos Solver Project and IFPACK object interact well with other Trilinos classes. In particular, IFPACK can be used as a preconditioner for AztecOO.

IFPACK contains one-level domain decomposition preconditioners of overlapping type. Each “subdomain” is defined by the set of rows assigned to a given processors. Several options are available for the local solution, ranging from simple relaxation schemes, to incomplete factorizations, to direct solvers (through the Amesos package).

To compile IFPACK, one needs the Epetra and Teuchos packages of Trilinos. It is convenient to enable the AztecOO and Galeri packages to compile and run some of the examples, and Amesos to enable direct solvers. ML can take advantage of IFPACK to define smoothers.

<span style="text-decoration: underline;">**IFPACK Publications**</span>

*   [Ifpack User Guide (.pdf)](pdfs/IfpackUserGuide.pdf)
