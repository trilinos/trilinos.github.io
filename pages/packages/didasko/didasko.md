---
title: Didasko
permalink: didasko.html
folder: packages
---

![Didasko Logo](http://trilinos.org/oldsite/packages/didasko/didasko_logo.jpeg) **Welcome to the Didasko Home**

Note that the primary Trilinos tutorial can now be found [here.](https://github.com/trilinos/Trilinos_tutorial/wiki "Trilinos Hands On Tutorial") Didasko may be retired in a future release.

Didasko, the tutorial of Trilinos, offers a quick introduction to several Trilinos packages. It contains a printable [PDF](http://trilinos.org/oldsite/Trilinos7.0Tutorial.pdf) document and a variety of well-commented [browsable examples](http://trilinos.sandia.gov/packages/didasko/examples.html) that illustrate how to use Trilinos. The PDF file and the examples are distributed within Trilinos; see the [download page](http://trilinos.org/download).

Didasko contains examples for the following Trilinos packages: [Teuchos](http://trilinos.org/packages/teuchos/), [Epetra](http://trilinos.org/packages/epetra/), [EpetraExt](http://trilinos.org/packages/epetraext), [TriUtils](http://trilinos.org/packages/triutils), [Amesos](http://trilinos.org/packages/amesos/), [AztecOO](http://trilinos.org/packages/aztecoo/), [IFPACK](http://trilinos.org/packages/ifpack/), [ML](http://trilinos.org/packages/ml/), [NOX](http://trilinos.org/packages/nox-and-loca/), [Anasazi](http://trilinos.org/packages/anasazi), [Belos](http://trilinos.org/packages/belos/), [TPetra](http://trilinos.org/packages/tpetra/).

With Didasko, you can quickly and effectively learn how to create and use distributed linear algebra objects, define PDE-like linear systems, solve them with direct and iterative solvers, defined a variety of preconditioners, and solve nonlinear systems. Didasko examples are short, easy to understand, and typically each example focuses on a well-defined topic.

In order to take advantage of Didasko, we suggest to compile Trilinos with the following flags:

<div>--enable-epetra --enable-aztecoo --enable-amesos --enable-anasazi \  
--enable-ifpack --enable-ml --enable-nox --enable-teuchos \  
--enable-triutils --enable-belos</div>

(The above flags refer only to the enabling/disabling of packages, and are typically completed by other flags, for example to specify the location of BLAS, LAPACK, MPI, etc.) Most of the required packages are enabled by default. No example can effectively run without Epetra, and most require AztecOO and Triutils and Galeri  
.

From this web page you can:

*   [Browse](http://trilinos.sandia.gov/packages/docs/dev/packages/didasko/doc/html/index.html) the source of all Didasko’s examples;
*   Check the FAQ page.

Have fun! Don’t hesitate to [contact us](http://trilinos.org/oldsite/packages/didasko/contact.html) for bugs, suggestions, or to help with the development!

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