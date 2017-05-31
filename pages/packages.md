---
title: Packages
permalink: packages.html
---

Trilinos is comprised of over 50 packages. Each Trilinos package is a self-contained, independent piece of software with its own set of requirements, its own development team and group of users. Because of this, Trilinos itself is designed to respect the autonomy of packages. Trilinos offers a variety of ways for a particular package to interact with other Trilinos packages. It also offers a set of tools that can assist package developers with builds across multiple platforms, generating documentation and regression testing across a set of target platforms. At the same time, what a package must do to be called a Trilinos package is minimal, and varies with each package.

Basic Linear Algebra Libraries

*   [Epetra](epetra.html "Epetra") -- Core linear algebra package. Facilitates construction and manipulation of distributed and serial graphs, sparse and dense matrices, vectors and multivectors.
*   [EpetraExt](epetraext.html "EpetraExt") -- Extensions to the core linear algebra package, Epetra.
*   [Tpetra](tpetra.html "Tpetra") -- Next-generation, templated version of Petra, taking advantage of the newer advanced features of C++.
*   Jpetra -- Experimental Java version of the Petra library. Not included in Trilinos release distributions.
*   [Kokkos](kokkos.html "Kokkos") -- Core kernel package.

## Preconditioners

*   [AztecOO](aztecoo.html "AztecOO") -- ILU-type preconditioner. See also description under “Linear Solvers.”
*   [IFPACK](ifpack.html "IFPACK") -- Distributed algebraic preconditioner package. Includes incomplete factorizations and relaxation-based preconditioners in domain decomposition framework. Compatible with AztecOO.
*   [Ifpack2](ifpack2.html "Ifpack2") -- Contains preconditioners that operate on the templated linear-algebra objects provided by the Tpetra package. Intended as a templated replacement for Ifpack.
*   [ML](ml.html "MueLu") -- Multilevel, distributed memory algebraic preconditioners. Provides multi-level, multigrid-like preconditioners for distributed linear systems. Compatible with AztecOO.
*   [Teko](teko.html "Teko") -- Blocked and segregated preconditioning package. Includes a high level interface for manipulating block operators and creating inverse operators using solver and preconditioning capabilities in Trilinos. Utilities are provided that decompose large Epetra_CrsMatrix objects into physically meaningful sub blocks.

## Solvers

### Linear Solvers

*   [Epetra](epetra.html "Epetra") -- Provides wrappers for select BLAS and LAPACK routines. See also description under “Basic Linear Algebra Libraries.”
*   [Teuchos](teuchos.html "Teuchos") -- Provides wrappers for select BLAS and LAPACK routines. See also description under “Basic Linear Algebra Libraries.”
*   [Pliris](pliris.html "Pliris") -- An object-oriented interface to a LU solver for dense matrices on parallel platforms.
*   [AztecOO](aztecoo.html "AztecOO") -- Preconditioned Krylov solver package. Supercedes Aztec 2.1\. Solves linear systems of equations via preconditioned Krylov methods. Uses Epetra objects, compatible with IFPACK, ML and Aztec.
*   [Belos](belos.html "Belos") -- Next-generation iterative solvers written using a traits interface, meaning that it has no explicit dependence on any concrete linear algebra library. Instead, it can be used with any concrete linear algebra library that implements the Thyra abstract interfaces and even Epetra directly.
*   [Komplex](komplex.html "Komplex") -- Complex linear solver package. Solves complex-valued linear systems via equivalent real formulations.
*   [Amesos](amesos.html "Amesos") -- Direct solver classes. Supports use of a growing list of third party direct solvers, including DSCPACK, SuperLU, SuperLUDist and UMFPACK. Compatible with Epetra.
*   [Amesos2](amesos2.html "Amesos2") -- Direct solver library.htmlinterface in Trilinos. Amesos2 provides interfaces to third-party direct solvers for templated matrices and vectors in Trilinos.

### Nonlinear, Transient, and Optimization Solvers

*   [NOX](nox_and_loca.html "NOX and LOCA") -- Nonlinear solver package. Abstract and concrete classes for construction and solution of nonlinear problems.
*   [LOCA](nox_and_loca.html "NOX and LOCA") -- LOCA is a software library for performing bifurcation analysis of large-scale applications. When implemented with an application code, LOCA enables the tracking of solution branches as a function of system parameters and the direct tracking of bifurcation points. LOCA is designed to drive application codes that use Newton’s method to locate steady-state solutions to nonlinear problems.
*   [ROL](rol "Rapid Optimization Library (ROL)") -- Rapid Optimization Library (ROL) is Trilinos’ next-generation package for large-scale optimization. It is used for the solution of optimal design, optimal control and inverse problems in large-scale engineering applications. Other uses include mesh optimization and image processing. ROL solves nonlinear nonconvex optimization problems with general equality and inequality constraints, with efficient specializations for various problem types. ROL’s matrix-free API enables direct use of application data structures and memory spaces, linear solvers, nonlinear solvers and preconditioners.
*   [MOOCHO](moocho.html "MOOCHO") -- MOOCHO (Multifunctional Object-Oriented arCHitecture for Optimization) is designed to solve large-scale, equality and inequality nonlinearly constrained, non-convex optimization problems (i.e. nonlinear programs) using reduced-space successive quadratic programming (SQP) methods.
*   [Piro](piro.html "Piro") -- Piro is striving to be the single unifying layer above all nonlinear solver, time integration, optimization, and UQ packages.
*   [Rythmos](rythmos.html "Rythmos") -- Rythmos is a transient integrator for ordinary differential equations and differential-algebraic equations with support for explicit, implicit, one-step and multi-step algorithms. The fundamental design of Rythmos is aimed at supporting operator-split algorithms, multi-physics applications, block linear algebra, and adjoint integration.
*   [TriKota](trikota.html "TriKota") -- TriKota is a convenience package that builds the [Dakota](https:.html.htmldakota.sandia.gov) framework underneath Trilinos as if it were a Trilinos package. Dakota contains a wide array of algorithms for optimization and UQ.
*   [GlobiPack](globipack.html "GlobiPack") -- The GlobiPack package contains a set of interfaces and implementations for 1D globalization capabilities to be used in nonlinear solvers, optimization solvers, and similar algorithms that require globalization methods (e.g. line search and trust region methods).
*   [OptiPack](optipack.html "OptiPack") -- The OptiPack package contains interfaces and concrete implementations of some basic optimization algorithms based on [Thyra](thyra.html "Thyra"). The globalization methods used are implemented in [GlobiPack](globipack.html "GlobiPack").

### Eigensolvers

*   [Anasazi](anasazi.html "Anasazi") -- Anasazi is an extensible and interoperable framework for large-scale eigenvalue algorithms. The motivation for this framework is to provide a generic interface to a collection of algorithms for solving large-scale eigenvalue problems. Anasazi is interoperable because both the matrix and vectors (defining the eigenspace) are considered to be opaque objects—only knowledge of the matrix and vectors via elementary operations is necessary. An implementation of Anasazi is accomplished via the use of interfaces. Current interfaces available include Epetra and so any libraries that understand Epetra matrices and vectors (such as AztecOO) may also be used in conjunction with Anasazi.

## Automatic Differentiation

*   [Sacado](sacado.html "Sacado") -- Sacado is a package for automatic differentiation of C++ programs It provides simple yet fast and efficient classes for forward, revers and Taylor polynomial mode automatic differentiation using C++ template and operator overloading. The resulting derivatives can be leveraged in numerous ways including nonlinear solves with [NOX](nox_and_loca.html "NOX and LOCA") continuation and bifurcation analysis with [LOCA](nox_and_loca.html "NOX and LOCA") optimization with [MOOCHO](moocho.html "MOOCHO"), and time integration wit [Rythmos](rythmos.html "Rythmos").
*   [Stokhos](stokhos.html "Stokhos") -- Stokhos is a package for intrusive stochastic Galerkin uncertainty quantification methods. It provides methods for computing well-known intrusive stochastic Galerkin projections such as Polynomial Chaos and Generalized Polynomial Chaos, interfaces for forming the resulting nonlinear systems, and linear solver methods for solving block stochastic Galerkin linear systems.

## Domain Decomposition

### Domain Decomposition

*   [Claps](claps.html "Claps") -- Claps is a collection of domain decomposition preconditioners and solvers. Claps has not been externally released with Trilinos.

### Mortar Methods

*   [Moertel](moertel.html "Moertel") -- Mortar methods that can be used in a large class of nonconforming situations such as the surface coupling of different physical models, discretization schemes or non-matching triangulations along interior interfaces of a domain.

## Partitioning .html Load Balancing

*   [Isorropia](isorropia.html "Isorropia") -- Isorropia is a partitioning and load balancing package, intended to assist with redistributing objects such as matrices and matrix-graphs in a parallel execution setting, to allow for more efficient computations. Isorropia is primarily an interface to the [Zoltan](http:.html.htmlwww.cs.sandia.gov.htmlZoltan.html) library.

*   [Zoltan](zoltan.html "Zoltan") -- Zoltan is a toolkit of parallel services for dynamic, unstructured, and.htmlor adaptive simulations. Zoltan provides parallel dynamic load balancing and related services for a wide variety of applications, including finite element methods, matrix operations, particle methods, and crash simulations. Zoltan also provides parallel graph coloring, matrix ordering, unstructured communication tools, and distributed data directories.

## Abstract Interfaces and Adapters

*   [Thyra](thyra.html "Thyra") -- Abstract linear solver package. Provides foundation for writing linear and nonlinear abstract numerical algorithms and interfaces to linear solvers and preconditioners (see Stratimikos).
*   [PyTrilinos](pytrilinos.html "PyTrilinos") -- Python interfaces to selected Trilinos packages.
*   CTrilinos -- C interfaces to selected Trilinos packages.
*   [ForTrilinos](fortrilinos.html "ForTrilinos") -- ForTrilinos provides a set of standards-conforming, potrable Fortran interfaces to Trilinos packages. ForTrilinos is intended to minimal in its implementation, Relative to direct interaction with Trilinos from C++, call Trilinos from Fortran via ForTrilinos adds no overhead beyond that associated with a single additional function call. The development of ForTrilinos is primarily user-driven, so new interfaces are developed at the request of Trilinos users.
*   [WebTrilinos](web_trilinos.html "Web Trilinos") -- Web interface to experiment with Trilinos through a browser.
*   [Stratimikos](stratimikos.html "Stratimikos") -- The package Stratimikos contains a unified set of Thyra-based wrappers to linear solver and preconditioner capabilities in Trilinos. The Stratimikos package is also a place where unified testing of linear solvers and preconditioners can be performed.
*   [FEI](fei.html "Fei") -- A general interface for assembling finite-element data into a system of linear equations.
*   [TrilinosCouplings](trilinoscouplings.html "Trilinos Couplings") -- A collection of interfaces between packages.

## Mesh Generation, Improvement, and Adaptivity

*   [Mesquite](mesquite.html "Mesquite") -- Applies a variety of node-movement algorithms to improve the quality and.htmlor adapt a given mesh.
*   [PAMGEN](pamgen.html "PAMGEN") -- PAMGEN creates hexahedral or quadrilateral (in 2D) finite element meshes of simple shapes (cubes and cylinders) in parallel. When linked to an application as a library, it allows each process of a parallel simulation to generate its finite element domain representation at execution time.

## Discretization Utilities

*   [Intrepid](intrepid.html "Intrepid") -- Intrepid is a library of interoperable tools for compatible discretizations of Partial Differential Equations (PDEs). Included with the Trilinos 10.0 release is the “expert version” of Intrepid. This version is intended primarily for application developers who want to reuse large parts of their existing code frameworks such as I.htmlO, data structures, assembly routines, etc. while gaining access to advanced discretization capabilities provided by Intrepid.
*   phdMesh -- (retired) The Parallel Heterogeneous Dynamic unstructured Mesh (phdMesh) data structure library is intended to be component used within a finite element or finite volume library or code. The phdMesh data structure supports arbitrary unstructured mesh connectivity, application-defined groupings of mesh entities, and application-defined computational field data. The included parallel-performance test application performs dynamic load balancing and parallel geometric proximity searching on the contrived “gears” test problem.
*   [STK](stk.html "STK") -- Contains capabilities intended to support massively parallel multi-physics computations on dynamically changing unstructured meshes. The primary capability in the STK package is the mesh database which supports creation and manipulation of mesh entities (nodes, elements etc) and computational field data defined on the mesh. STK also contains sub-libraries that support geometric proximity searches, assembly into linear-systems, etc.

## Utilities

*   [Teuchos](teuchos.html "Teuchos") -- Common tools package.
*   [TriUtils](triutils.html "TriUtils") -- TriUtils is a package of utilites used by many of the Trilinos packages.
*   [EpetraExt](epetraext.html "EpetraExt") -- Matrix.htmlVector read.htmlwrite utilities. See also description under “Basic Linear Algebra Libraries.”
*   [RTOp](rtop.html "RTOp") -- RTOp (reduction.htmltransformation operators) provides the basic mechanism for implementing vector operations in a flexible and efficient manner.
*   [Galeri](galeri.html "Galeri") -- Galeri is a package for generating linear systems used by many of the Trilinos packages for examples and tests.
*   ThreadPool -- A minimalistic interface for orchestrating the thread-parallel execution of functions within a pool of threads.
*   [Optika](optika.html "Optika") -- The Optika package provides trilinos developers with easy access to GUI input methods for their programs.
*   SEACAS -- The Sandia Engineering Analysis Code Access System (SEACAS) is a collection of applications for manipulating Exodus databases. The Exodus database is a model developed to facilitate pre- and post-processing and code-to-code exchange of finite element analysis data. The Exodus database is a random access, machine independent binary format that is accessed via a C, C++, or Fortran API. SEACAS applications include Exodus database manipulation, query, translation, parallel decomposition and composition, comparison, parameterization, and mapping utilities.

## PDE discretization tools

*   [Phalanx](phalanx.html "Phalanx") -- Phalanx is a local field evaluation kernel specifically designed for general partial differential equation solvers.

*   [Intrepid](intrepid.html "Intrepid") -- Intrepid is a library of interoperable tools for compatible discretizations of Partial Differential Equations (PDEs). The current version is intended primarily for application developers who want to reuse large parts of their existing code frameworks such as I.htmlO, data structures, assembly routines, etc. while gaining access to advanced discretization capabilities provided by Intrepid.

*   [Shards](shards.html "Shards") -- Shards is a suite of common tools for numerical and topological data that facilitate interoperability between typical software modules used to solve Partial Differential Equations (PDEs) by finite element, finite volume and finite difference methods. Shards provides two categories of tools: templated multi-dimensional array implementation and templated cell topologies.

## Instructional

*   [Didasko](didasko.html "Didasko") -- Didasko is the Trilinos tutorial, and contains several examples, detailed descriptions, tips, and suggestions for most Trilinos packages.
*   [New_Package](new-package.html "New Package") -- A sample Trilinos package containing all of the infrastructure to install a new package into the Trilinos framework. Contains the basic directory structure, a collection of sample configuration and build files and a sample “Hello World” package. New_package is no longer part of the Trilinos release distribution.

## Other

*   Sundance -- Sundance is a system for rapid development of high-performance finite-element solutions of partial differential equations.
