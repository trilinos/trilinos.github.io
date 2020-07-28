---
title: Packages
permalink: packages.html
---

Trilinos is comprised of over 50 packages. Each Trilinos package is a self-contained, independent piece of software with its own set of requirements, its own development team and group of users. Because of this, Trilinos itself is designed to respect the autonomy of packages.  Use the Packages dropdown menu to see all packages. Below we mention some of the most important ones.

## Actively developed Trilinos packages
The following packages are undergoing active development in support of new applications and computing platforms.

### Basic Linear Algebra Libraries
- [Tpetra](tpetra.html "Tpetra") -- The primary parallel linear algebra library in Trilinos.
- [Kokkos](kokkos.html "Kokkos") -- Core kernel package.

### Preconditioners
- [Muelu](muelu.html "Muelu") -- Algebraic multigrid for emerging problems and architectures.
- [Ifpack2](ifpack2.html "Ifpack2") -- Contains preconditioners that operate on the templated linear-algebra objects provided by the Tpetra package. Intended as a templated replacement for Ifpack.

### Solvers

#### Linear Solvers

- [Teuchos](teuchos.html "Teuchos") -- Provides wrappers for select BLAS and LAPACK routines. See also description under “Basic Linear Algebra Libraries.”
- [Belos](belos.html "Belos") -- Next-generation iterative solvers written using a traits interface, meaning that it has no explicit dependence on any concrete linear algebra library. Instead, it can be used with any concrete linear algebra library that implements the Thyra abstract interfaces and even Epetra directly.
- [Amesos2](amesos2.html "Amesos2") -- Direct solver library.htmlinterface in Trilinos. Amesos2 provides interfaces to third-party direct solvers for templated matrices and vectors in Trilinos.

#### Nonlinear, Transient, and Optimization Solvers

- [NOX](nox_and_loca.html "NOX and LOCA") -- Nonlinear solver package. Abstract and concrete classes for construction and solution of nonlinear problems.
- [LOCA](nox_and_loca.html "NOX and LOCA") -- LOCA is a software library for performing bifurcation analysis of large-scale applications. When implemented with an application code, LOCA enables the tracking of solution branches as a function of system parameters and the direct tracking of bifurcation points. LOCA is designed to drive application codes that use Newton’s method to locate steady-state solutions to nonlinear problems.
- [ROL](rol "Rapid Optimization Library (ROL)") -- Rapid Optimization Library (ROL) is Trilinos’ next-generation package for large-scale optimization. It is used for the solution of optimal design, optimal control and inverse problems in large-scale engineering applications. Other uses include mesh optimization and image processing. ROL solves nonlinear nonconvex optimization problems with general equality and inequality constraints, with efficient specializations for various problem types. ROL’s matrix-free API enables direct use of application data structures and memory spaces, linear solvers, nonlinear solvers and preconditioners.
- [Tempus](tempus.html "Tempus") -- Time-integration framework for advanced transient analysis, including various time integrators and embedded sensitivity analysis.

### Eigensolvers

- [Anasazi](anasazi.html "Anasazi") -- Anasazi is an extensible and interoperable framework for large-scale eigenvalue algorithms. The motivation for this framework is to provide a generic interface to a collection of algorithms for solving large-scale eigenvalue problems. Anasazi is interoperable because both the matrix and vectors (defining the eigenspace) are considered to be opaque objects—only knowledge of the matrix and vectors via elementary operations is necessary. An implementation of Anasazi is accomplished via the use of interfaces. Current interfaces available include Epetra and so any libraries that understand Epetra matrices and vectors (such as AztecOO) may also be used in conjunction with Anasazi.

### Automatic Differentiation

- [Sacado](sacado.html "Sacado") -- Sacado is a package for automatic differentiation of C++ programs It provides simple yet fast and efficient classes for forward, revers and Taylor polynomial mode automatic differentiation using C++ template and operator overloading. The resulting derivatives can be leveraged in numerous ways including nonlinear solves with [NOX](nox_and_loca.html "NOX and LOCA") continuation and bifurcation analysis with [LOCA](nox_and_loca.html "NOX and LOCA") optimization with [MOOCHO](moocho.html "MOOCHO"), and time integration with [Rythmos](rythmos.html "Rythmos").
- [Stokhos](stokhos.html "Stokhos") -- Stokhos is a package for intrusive stochastic Galerkin uncertainty quantification methods. It provides methods for computing well-known intrusive stochastic Galerkin projections such as Polynomial Chaos and Generalized Polynomial Chaos, interfaces for forming the resulting nonlinear systems, and linear solver methods for solving block stochastic Galerkin linear systems.

### Discretization Utilities
- [Panzer](panzer.html "Panzer") -- Panzer is a package for performing finte element analysis
- [Intrepid2](intrepid2.html "Intrepid2") -- Performance portable tools for the local assembly of high-order compatible finte element discretizations.
- [Phalanx](phalanx.html "Phalanx") -- Phalanx is a DAG-based local field evaluation kernel specifically designed for general partial differential equation solvers.
- [Compadre](compadre.html "Compadre") -- Toolkit for meshless discretizations enabling solution of differential equations and data transfer.


## Supported Trilinos packages
The following packages are no longer under active development but are supported for bug fixes.

### Basic Linear Algebra Libraries
- [Epetra](epetra.html "Epetra") -- Widely used and supported linear algebra package.

### Preconditioners
- [AztecOO](aztecoo.html "AztecOO") -- ILU-type preconditioner. See also description under “Linear Solvers.”
- [IFPACK](ifpack.html "IFPACK") -- Distributed algebraic preconditioner package. Includes incomplete factorizations and relaxation-based preconditioners in domain decomposition framework. Compatible with AztecOO.
- [ML](ml.html "MueLu") -- Multilevel, distributed memory algebraic preconditioners. Provides multi-level, multigrid-like preconditioners for distributed linear systems. Compatible with AztecOO.

### Linear Solvers

- [Epetra](epetra.html "Epetra") -- Provides wrappers for select BLAS and LAPACK routines. See also description under “Basic Linear Algebra Libraries.”
- [Pliris](pliris.html "Pliris") -- An object-oriented interface to a LU solver for dense matrices on parallel platforms.
- [AztecOO](aztecoo.html "AztecOO") -- Preconditioned Krylov solver package. Supercedes Aztec 2.1\. Solves linear systems of equations via preconditioned Krylov methods. Uses Epetra objects, compatible with IFPACK, ML and Aztec.
- [Amesos](amesos.html "Amesos") -- Direct solver classes. Supports use of a growing list of third party direct solvers, including DSCPACK, SuperLU, SuperLUDist and UMFPACK. Compatible with Epetra.

### Partitioning and Load Balancing

- [Isorropia](isorropia.html "Isorropia") -- Isorropia is a partitioning and load balancing package, intended to assist with redistributing objects such as matrices and matrix-graphs in a parallel execution setting, to allow for more efficient computations. Isorropia is primarily an interface to the [Zoltan](https://cs.sandia.gov/Zoltan/) library.
- [Zoltan](zoltan.html "Zoltan") -- Zoltan is a toolkit of parallel services for dynamic, unstructured, and.htmlor adaptive simulations. Zoltan provides parallel dynamic load balancing and related services for a wide variety of applications, including finite element methods, matrix operations, particle methods, and crash simulations. Zoltan also provides parallel graph coloring, matrix ordering, unstructured communication tools, and distributed data directories.

### Abstract Interfaces and Adapters

- [Thyra](thyra.html "Thyra") -- Abstract linear solver package. Provides foundation for writing linear and nonlinear abstract numerical algorithms and interfaces to linear solvers and preconditioners (see Stratimikos).
- [PyTrilinos](pytrilinos.html "PyTrilinos") -- Python interfaces to selected Trilinos packages.
- [WebTrilinos](web_trilinos.html "Web Trilinos") -- Web interface to experiment with Trilinos through a browser.
- [Stratimikos](stratimikos.html "Stratimikos") -- The package Stratimikos contains a unified set of Thyra-based wrappers to linear solver and preconditioner capabilities in Trilinos. The Stratimikos package is also a place where unified testing of linear solvers and preconditioners can be performed.
- [TrilinosCouplings](trilinoscouplings.html "Trilinos Couplings") -- A collection of interfaces between packages.

### Discretization Utilities

- [Intrepid](intrepid.html "Intrepid") -- Intrepid is a library of interoperable tools for compatible discretizations of partial differential equations.
- [Shards](shards.html "Shards") -- topology data for mesh-based discretization of differential equations
- [MiniTensor](minitensor.html "MiniTensor") -- Tools for the manipulation and optimization of small vectors/tensors
- [FEI](fei.html "FEI") -- A general interface for assembling finite-element data into a system of linear equations.
- [STK](stk.html "STK") -- Contains capabilities intended to support massively parallel multi-physics computations on dynamically changing unstructured meshes. The primary capability in the STK package is the mesh database which supports creation and manipulation of mesh entities (nodes, elements etc) and computational field data defined on the mesh. STK also contains sub-libraries that support geometric proximity searches, assembly into linear-systems, etc.
- [Percept](percept.html "Percept") -- A collection of tools, including mesh adaptation and data tranfer, to enable solution verification.
