---
title: Thyra
permalink: thyra.html
folder: packages
show_sidebar: true
contact: <a href="mailto:rabartl@sandia.gov">Ross Bartlett</a> (<a href="https://github.com/bartlettroscoe">@bartlettroscoe</a>), <a href="https://github.com/orgs/trilinos/teams/thyra">@thyra</a>
package: thyra
doxygen: true
---

Welcome to the Thyra Home

The [Thyra](thyra.html) package contains a set of interfaces and supporting code that defines basic interoperability mechanisms between different types of abstract numerical algorithm (ANA) software. The foundations for all Thyra interfaces are the mathematical concepts of vectors, vector spaces, and linear operators. All other ANA interfaces and support software are built on these fundamental operator/vector interfaces.

 The following document describes the basic ideas behind Thyra and provides an overview of the operator/vector interfaces:

 *   Bartlett, Roscoe. _Thyra Linear Operators and Vectors: Overview of Interfaces and Support Software for the Development and Interoperability of Abstract Numerical Algorithms._ SAND2007-5984, Sandia National Laboratories, 2007 [[PDF](http://web.ornl.gov/~8vt/ThyraOverview2007.pdf)]

 The primary [Thyra](thyra.html) ANA interfaces are broadly layered as followed:

 *   **Operator/vector interfaces**
     *   [Thyra::VectorBase](docs//thyra/classThyra_1_1VectorBase.html)
     *   [Thyra::VectorSpaceBase](docs//thyra/classThyra_1_1VectorSpaceBase.html)
     *   [Thyra::LinearOpBase](docs//thyra/classThyra_1_1LinearOpBase.html)
     *   [Thyra::MultiVectorBase](docs//thyra/classThyra_1_1MultiVectorBase.html)
 *   **Operator solve interfaces**
     *   [Thyra::PreconditionerBase](docs//thyra/classThyra_1_1PreconditionerBase.html)
     *   [Thyra::PreconditionerFactoryBase](docs//thyra/classThyra_1_1PreconditionerFactoryBase.html)
     *   [Thyra::LinearOpWithSolveBase](docs//thyra/classThyra_1_1LinearOpWithSolveBase.html)
     *   [Thyra::LinearOpWithSolveFactoryBase](docs//thyra/classThyra_1_1LinearOpWithSolveFactoryBase.html)
 *   **Nonlinear Interfaces**
     *   [Thyra::ModelEvaluator](docs//thyra/classThyra_1_1ModelEvaluator.html)
     *   [Thyra::NonlinearSolverBase](docs//thyra/classThyra_1_1NonlinearSolverBase.html)

 A few important points about Thyra interfaces are:

 *   All interfaces are expressed as abstract C++ base classes (i.e. object-oriented)
 *   All interfaces are templated on a Scalar data type (i.e. generic)
 *   All memory management is performed using [Teuchos](docs//teuchos/namespaceTeuchos.html) memory management classes involving no raw C++ pointers (see below)

 For each of these sets of interfaces, the Thyra package also a set of general adapter and general support software. See the Thyra package documentation for more details.

 There are several Trilinos packages that implement ANAs, and/or can accept input as ANA object, and/or can provide implementations of ANA objects for other ANAs to use. Information related to Thyra and ANAs can be found below:

 *   **[Thyra](thyra.html)**
     *   Adapters
         *   [Thyra/{Epetra, Tpetra} Adapters](docs//thyra/adapters/epetra/index.html):
             *   Utility classes and functions for mapping between Thyra wrapper objects, and Epetra or Tpetra linear algebra objects
         *   [Thyra/EpetraExt Adatpers](docs//thyra/adapters/epetraext/index.html):
             *   [Thyra::EpetraModelEvaluator](docs//thyra/classThyra_1_1EpetraModelEvaluator.html): Implements [Thyra::ModelEvaluator](docs//thyra/classThyra_1_1ModelEvaluator.html) in terms of an [EpetraExt::ModelEvaluator](docs//epetraext/classEpetraExt_1_1ModelEvaluator.html) object

Thyra Coding and Documentation Guidelines

*   Bartlett, Roscoe. _Thyra Coding and Documentation Guidelines (TCDG)._ Sandia National Laboratories [[PDF](http://www.ornl.gov/~8vt/ThyraCodingGuideLines.pdf)]
