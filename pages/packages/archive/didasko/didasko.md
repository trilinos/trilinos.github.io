---
title: Didasko
permalink: didasko.html
folder: archive
show_sidebar: true
contact: maherou@sandia.gov
package: didasko
doxygen: true
---

![Didasko Logo](images/didasko_logo.jpeg)

**Welcome to the Didasko Home**

Note that the primary Trilinos tutorial can now be found [here.](https://github.com/trilinos/Trilinos_tutorial/wiki "Trilinos Hands On Tutorial") Didasko may be retired in a future release.

Didasko, the tutorial of Trilinos, offers a quick introduction to several Trilinos packages. It contains a printable [PDF](pdfs/Trilinos7.0Tutorial.pdf) document and a variety of well-commented [browsable examples](https://trilinos.org/didasko/examples.html) that illustrate how to use Trilinos. The PDF file and the examples are distributed within Trilinos; see the [download page](download.html).

Didasko contains examples for the following Trilinos packages: [Teuchos](teuchos.html), [Epetra](epetra.html), [EpetraExt](epetraext.html), [TriUtils](triutils.html), [Amesos](amesos.html), [AztecOO](aztecoo.html), [IFPACK](ifpack.html), [ML](ml.html), [NOX](nox_and_loca.html), [Anasazi](anasazi.html), [Belos](belos.html), [TPetra](tpetra.html).

With Didasko, you can quickly and effectively learn how to create and use distributed linear algebra objects, define PDE-like linear systems, solve them with direct and iterative solvers, defined a variety of preconditioners, and solve nonlinear systems. Didasko examples are short, easy to understand, and typically each example focuses on a well-defined topic.

In order to take advantage of Didasko, we suggest to compile Trilinos with the following flags:

<div>--enable-epetra --enable-aztecoo --enable-amesos --enable-anasazi \  
--enable-ifpack --enable-ml --enable-nox --enable-teuchos \  
--enable-triutils --enable-belos</div>

(The above flags refer only to the enabling/disabling of packages, and are typically completed by other flags, for example to specify the location of BLAS, LAPACK, MPI, etc.) Most of the required packages are enabled by default. No example can effectively run without Epetra, and most require AztecOO and Triutils and Galeri  
.

From this web page you can:

*   [Browse](docs//didasko/index.html) the source of all Didasko’s examples;
*   Check the FAQ page.

If you want to cite didasko and/or the Trilinos tutorial PDF document, please use the following bibtex entry:

<pre>@TechReport{trilinos-tutorial,
  author      =  {M. Sala and M. A. Heroux and D. M. Day (editors)},
  title       =  {Trilinos Tutorial},
  institution =  {Sandia National Laboratories},
  year        =  {2004},
  number      =  {SAND-2189},
}</pre>

<span style="text-decoration: underline;">**Overview**</span>

Didasko, the tutorial of Trilinos, offers a quick overview of Trilinos. The reader can find a variety of examples on several Trilinos packages. Each example is documented with comments and suggestions, some in the source file itself, and some others in the PDF document. The PDF version of the tutorial can be found in the Trilinos web page, or in file TRILINOS_HOME/packages/didasko/doc/tutorial.pdf.
