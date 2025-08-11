---
title: PyTrilinos
permalink: pytrilinos.html
folder: archive
show_sidebar: true
contact: wfspotz@sandia.gov
package: pytrilinos
---

<img border="0" alt="Trilinos Team" src="images/PyTrilinos.jpg" width="10" height="10">

Welcome to the PyTrilinos home
PyTrilinos is a set of [python](https://www.python.org) wrappers for selected [Trilinos](http://trilinos.github.io) packages. 
This allows a [python](https://www.python.org) programmer to dynamically import Trilinos packages into a [python](https://www.python.org) 
script or the [python](https://www.python.org) command-line interpreter, allowing the creation and manipulation of Trilinos objects 
and the execution of Trilinos algorithms, without the need to constantly recompile.

PyTrilinos adds a level of convenience to Trilinos users; quick and dirty tests can be run immediately, unit testing can be built quickly within the [python](https://www.python.org) unit testing framework, 
object-oriented design can be explored more efficiently, and full-fledged applications can be developed using [python](https://www.python.org).

PyTrilinos is intended to supplement the outstanding efforts of the community of [SciPy](http://www.scipy.org) developers by providing robust solver capabilities to the scientific [python](https://www.python.org) community.
 As such, it has a high degree of compatibility with [NumPy](http://www.numpy.org/), the _n_-dimensional array module that provides contiguous, homogeneous data support for all [SciPy](http://www.scipy.org) modules.

A description of the linear algebra modules of PyTrilinos can be found in the Sandia report [SAND2005-3835](pdfs/UsersGuide.pdf). You may also examine various conference presentations of PyTrilinos:

*   [Reproducible Research in Computational Geophysics](pdfs/RRCG06-PyTrilinos.pdf)
*   [SciPy 2006](pdfs/SciPy06-PyTrilinos.pdf)
*   [PARA’06 Conference](pdfs/PARA06-pytrilinos.pdf)
*   [SIAM Parallel Processing 2006](pdfs/SIAMPP06-PyTrilinos.pdf)
*   [SciPy 2005](pdfs/SciPy05-PyTrilinos.pdf)

General questions can be directed to the [PyTrilinos users mailing list](https://software.sandia.gov/mailman/listinfo/pytrilinos-users).

If you use PyTrilinos for your applications, please let us know by writing an e-mail to the [PyTrilinos developers](http://trilinos.org/oldsite/packages/pytrilinos/team.html). Please also cite PyTrilinos using the following bibtex entry:

@Article\{PyTrilinos,
  author      = \{M. Sala and W. Spotz and M. Heroux\},
  title       = \{\{PyTrilinos\}: High-Performance
                 Distributed-Memory Solvers for \{Python\}\},
  journal     = \{ACM Transactions on Mathematical Software (TOMS)\},
  year        = \{2008\},
  month       = \{March\},
  volume      = \{34\},
  issue       = \{2\};
\}

<span style="text-decoration: underline;">**Overview**</span>

**Description.** PyTrilinos provides a python interface to several of the most popular Trilinos packages. The following packages are supported:

*   Teuchos
*   Thyra (currently disabled)
*   Epetra
*   TriUtils
*   EpetraExt
*   Pliris
*   AztecOO
*   Galeri
*   Amesos
*   IFPACK
*   Komplex
*   Anasazi
*   ML
*   NOX
*   LOCA (currently disabled)

**External Compatibility.** PyTrilinos provides python access to highly robust, sparse and dense, serial and parallel, linear, nonlinear and eigen solver packages. As such, it is a complementary package to [SciPy](http://www.scipy.org), a collection of python interfaces to scientific open-source software. [SciPy](http://www.scipy.org) works on multidimensional arrays of strided, homogeneous data. This data is provided by the [numpy](http://www.numpy.org/) module. PyTrilinos has been designed for extensive compatibility with [numpy](http://www.numpy.org/).

This compatibility comes in two forms. The first form is that many Trilinos C++ methods accept or return pointers to arrays of data. The corresponding PyTrilinos python methods accept or return [numpy](http://www.numpy.org/) arrays, or for input arguments, python sequences that can be converted to [numpy](http://www.numpy.org/) arrays. The second form of compatibility is that certain Epetra classes, namely

*   Epetra.IntVector
*   Epetra.MultiVector
*   Epetra.Vector
*   Epetra.FEVector
*   Epetra.IntSerialDenseMatrix
*   Epetra.IntSerialDenseVector
*   Epetra.SerialDenseMatrix
*   Epetra.SerialDenseVector

represent contiguous, homogeneous arrays of data, and as such overlap in functionality with [numpy](http://www.numpy.org/) arrays. These classes are therefore redesigned in python such that they also inherit essentially from the numpy.ndarray class, meaning that other scientific software will recognize them as [numpy](http://www.numpy.org/) arrays.

**Parallelism.** PyTrilinos also supports MPI parallelism. If Trilinos is built with MPI support enabled, PyTrilinos will support MPI as well. Most of the Trilinos parallelism support is encapsulated in the Epetra_Comm class and its derivatives, which means PyTrilinos parallelism is encapsulated in the Epetra.Comm class and its derivatives. When the Epetra or Teuchos module is imported, it automatically calls MPI_Init() and registers MPI_Finalize() with the python atexit module. Scripts can be executed using a standard python interpreter, called via the standard mpirun command (or equivalent).
