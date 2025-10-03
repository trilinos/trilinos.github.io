---
title: Amesos
permalink: amesos.html
folder: archive
show_sidebar: true
contact: amesos-developers@software.sandia.gov
package: amesos
doxygen: true
---

![](images/AmesosLogo.jpeg) 

**Welcome to the Amesos Home**

_Amesos is a Greek term meaning **direct**._

Amesos is the Direct Sparse Solver Package in Trilinos. The goal of Amesos is to make AX=B as easy as it sounds, at least for direct methods. Amesos provides clean and consistent interfaces to the following third party libraries:

*   LAPACK
*   [UMFPACK version 4.4](http://faculty.cse.tamu.edu/davis/suitesparse.html)
*   [TAUCS version 2.2](http://code.google.com/p/taucs/)
*   [PARDISO version 1.2.3 (outdated)](http://www.pardiso-project.org)
*   [SuperLU version 4.1](http://crd.lbl.gov/%7Exiaoye/SuperLU)
*   [SuperLU_DIST version 2.5](http://crd.lbl.gov/%7Exiaoye/SuperLU)
*   [DSCPACK version 1.0](http://www.cse.psu.edu/%7Eraghavan/Dscpack/)
*   [SCALAPACK version 1.7](http://www.netlib.org/scalapack/scalapack_home.html)
*   [MUMPS version 4.7.3](http://graal.ens-lyon.fr/MUMPS/) (experimental support for version 4.9)

Amesos comes with a serial direct solver, called KLU, and a parallel direct solver, called Paraklete, which can be used to solve sparse linear systems. Each interface can be enabled at configure time. Amesos also offers an interface to Python, thus making all the supported interfaces available within the Python interpreter; see the [PyTrilinos](pytrilinos.html) package for more details.

For a brief overview of Amesos’ usage, click [here](http://trilinos.org/oldsite/packages/amesos/slides-overview.html). This page requires JavaScript and a recent browser. Amesos documentation is created and maintained using Doxygen. Click [here](docs/dev//amesos/index.html) to access the latest Doxygen documentation, containing details about Amesos and its classes, examples of usage, how to interface with other Trilinos packages, and more. You can also check the [Amesos guide](pdfs/AmesosReferenceGuide.pdf) (PDF file, 143 Kbytes) and the [design of Amesos](pdfs/AmesosDesign.pdf) (PDF file, 183 Kbytes). If you want a quick overview of the project, you can give a look [here](pdfs/PARA06-amesos.pdf) to the slides presented at the PARA’06 conference. If you use Amesos for your applications, please let us know by writing an e-mail to the [Amesos developers](mailto:amesos-developers@software.sandia.gov). Please also cite Amesos using the following bibtex entries:

    @article{amesos,
        title = "On the Design of Interfaces to Sparse Direct Solvers",
        author = "M. Sala and K. Stanley and M. Heroux",
        journal = "submitted",
        year = 2006
    }

    @inproceedings{amesos:para06,
        title = "Amesos: A Set of General Interfaces to Sparse Direct Solver Libraries",
        author = "M. Sala and K. Stanley and M. Heroux",
        booktitle = "Proceedings of PARA'06 Conference, Umea, Sweden",
        year = 2006
    }

<span style="text-decoration: underline;">**Overview**</span>

Amesos is a set of C++ interfaces to serial and parallel sparse direct solvers. Amesos contains two nice sparse solvers: KLU and Paraklete. KLU is serial, while Paraklete (distributed with Trilinos 7.0 or higher) is a parallel solver. Amesos also offers an interface to LAPACK, and several other well-know solvers available on the web. The main idea of Amesos is to give a high-level view of direct solvers, as composed by four main phases:

1.  specification of parameters;
2.  initialization of the solver, using matrix sparsity only;
3.  computation of the factors;
4.  solution of the linear system.

Amesos insulates the user from all the low-level details typical of direct solvers, like the matrix format, data distribution for the matrix, the solution and the right-hand side, parameter settings, and so on. Amesos is not based on any matrix format; instead, an matrix interface (specified by using the Epetra_RowMatrix class) is adopted. This facilitates the usage of Amesos classes in any projects whose matrix can be wrapped as an Epetra_RowMatrix.

<span style="text-decoration: underline;">**Trying Amesos**</span>

After installing Amesos, take a look at amesos/example/example_AmesosFactory_HB.exe in your build tree. You can easily modify the source code of this example to load your favorite matrix in Harwell-Boeing format. Please refer to the comments in the code for more details.  
Alternatively, consider running Test_Basic/amesos_test.exe, which accepts matrices in several formats.


