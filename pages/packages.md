---
title: Packages
permalink: packages.html
---

Trilinos is comprised of over 50 packages. Each Trilinos package is a self-contained, independent piece of software with its own set of requirements, its own development team and group of users. Because of this, Trilinos itself is designed to respect the autonomy of packages.

<table>
  <tr style="background-color: lightblue;">
    <td><strong>Status*</strong></td>
    <td><strong>Package</strong></td>
    <td><strong>Description</strong></td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Core Packages</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="epetra.html" title="Epetra">Epetra</a></td>
    <td>Epetra provides the fundamental construction routines and services function that are required for serial and parallel linear algebra libraries. Epetra provides the underlying foundation for all Trilinos solvers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="epetraext.html" title="EpetraExt">EpetraExt</a></td>
    <td>Extended Epetra routines and services.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="kokkos.html" title="Kokkos">Kokkos</a></td>
    <td>Core kernel package.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="rtop.html" title="RTop">RTop</a></td>
    <td>RTOp (reduction/transformation operators) provides the basic mechanism for implementing vector operations in a flexible and efficient manner.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="https://github.com/sandialabs/seacas" title="SEACAS">SEACAS</a></td>
    <td>The Sandia Engineering Analysis Code Access System (SEACAS) is a suite of preprocessing, postprocessing, translation, and utility applications supporting finite element analysis software using the Exodus database file format.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="teuchos.html" title="Teuchos">Teuchos</a></td>
    <td>Teuchos provides a suite of common tools for Trilinos for developers to use. These tools include BLAS and LAPACK wrappers, smart pointers, parameter lists, and XML parsers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="tpetra.html" title="Tpetra">Tpetra</a></td>
    <td>Trilinos’ Tpetra package implements linear algebra objects. These include sparse graphs, sparse matrices, and dense vectors. Many Trilinos packages and applications produce, modify, or consume Tpetra’s linear algebra objects, or depend on Tpetra’s parallel data redistribution facilities.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="xpetra.html" title="Xpetra">Xpetra</a></td>
    <td>Xpetra a lightweight wrapper to both the Epetra and Tpetra linear algebra libraries. The Xpetra syntax mirrors as much as possible that of Tpetra.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Partitioning and Load Balancing</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="isorropia.html" title="Isorropia">Isorropia</a></td>
    <td>Isorropia is a package for combinatorial scientific computing, with focus on partitioning and load balancing, but also supports coloring and ordering of sparse matrices.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="zoltan.html" title="Zoltan">Zoltan</a></td>
    <td>Zoltan is a toolkit of parallel services for dynamic, unstructured, and/or adaptive simulations. Zoltan provides parallel dynamic load balancing and related services for a wide variety of applications, including finite element methods, matrix operations, particle methods, and crash simulations. Zoltan also provides parallel graph coloring, matrix ordering, unstructured communication tools, and distributed data directories.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="zoltan2.html" title="Zoltan2">Zoltan2</a></td>
    <td>Zoltan2 is a package for load balancing and combinatorial scientific computing. It may be viewed as a successor to the popular Zoltan and Isorropia packages.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Eigensolvers</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="anasazi.html" title="Anasazi">Anasazi</a></td>
    <td>Anasazi is an extensible and interoperable framework for large-scale eigenvalue algorithms.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Preconditioners</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="aztecoo.html" title="AztecOO">AztecOO</a></td>
    <td>ILU-type preconditioner. See also description under “Linear Solvers.”</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="epetra.html" title="Epetra">Epetra</a></td>
    <td>Provides wrappers for select BLAS and LAPACK routines. See also description under “Core Packages”.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="ifpack.html" title="Ifpack">Ifpack</a></td>
    <td>Distributed algebraic preconditioner package. Includes incomplete factorizations and relaxation-based preconditioners in domain decomposition framework. Compatible with AztecOO.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="ifpack2.html" title="Ifpack2">Ifpack2</a></td>
    <td>Ifpack2 provides incomplete factorizations, relaxations, and domain decomposition operators for linear algebra objects (sparse matrices, operators, and dense vectors and multivectors) provided by the Tpetra package. Intended as a templated replacement for Ifpack.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="ml.html" title="ML">ML</a></td>
    <td>Multilevel, distributed memory algebraic preconditioners. Provides multi-level, multigrid-like preconditioners for distributed linear systems. Compatible with AztecOO.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="muelu.html" title="Muelu">Muelu</a></td>
    <td>MueLu is designed to solve large sparse linear systems of equations arising from PDE discretizations. MueLu provides easy-to-use multigrid solvers and preconditioners based on smoothed aggregation algorithms.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><a href="linear_solver.html"><strong>Linear Solvers</strong></a></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="adelus.html" title="Adelus">Adelus</a></td>
    <td>Adelus performs LU factorization with partial pivoting and solves for a dense (real or complex) linear equation system on a distributed computing system using MPI for message passing. It can be considered a replacement for Pliris, which runs only on CPUs.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="amesos.html" title="Amesos">Amesos</a></td>
    <td>Direct solver classes. Supports use of a growing list of third party direct solvers, including DSCPACK, SuperLU, SuperLUDist and UMFPACK. Compatible with Epetra.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="amesos2.html" title="Amesos2">Amesos2</a></td>
    <td>Direct solver library interface in Trilinos. Amesos2 provides interfaces to third-party direct solvers for templated matrices and vectors in Trilinos.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="aztecoo.html" title="AztecOO">AztecOO</a></td>
    <td>Preconditioned Krylov solver package. Supercedes Aztec 2.1. Solves linear systems of equations via preconditioned Krylov methods. Uses Epetra objects, compatible with IFPACK, ML and Aztec.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="belos.html" title="Belos">Belos</a></td>
    <td>Next-generation iterative solvers written using a traits interface, meaning that it has no explicit dependence on any concrete linear algebra library. Instead, it can be used with any concrete linear algebra library that implements the Thyra abstract interfaces and even Epetra directly.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="pliris.html" title="Pliris">Pliris</a></td>
    <td>An object-oriented interface to a LU solver for dense matrices on parallel platforms.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="shylu.html" title="ShyLU">ShyLU</a></td>
    <td>ShyLU is a package for solving sparse linear systems using domain decomposition methods. ShyLU has two main focus areas - (1) distributed memory domain-decomposition solvers and (2) node-level solvers and kernels that support the distributed memory solvers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="teuchos.html" title="Teuchos">Teuchos</a></td>
    <td>Provides wrappers for select BLAS and LAPACK routines. See also description under “Core Packages”.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Automatic Differentiation</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="sacado.html" title="Sacado">Sacado</a></td>
    <td>Sacado is a package for automatic differentiation of C++ programs. It provides simple yet fast and efficient classes for forward, reverse and Taylor polynomial mode automatic differentiation using C++ template and operator overloading.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="stokhos.html" title="Stokhos">Stokhos</a></td>
    <td>Stokhos is a package for intrusive stochastic Galerkin uncertainty quantification methods. It provides methods for computing well-known intrusive stochastic Galerkin projections such as Polynomial Chaos and Generalized Polynomial Chaos, interfaces for forming the resulting nonlinear systems, and linear solver methods for solving block stochastic Galerkin linear systems.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Discretization Utilities</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="compadre.html" title="Compadre">Compadre</a></td>
    <td>Toolkit for meshless discretizations enabling solution of differential equations and data transfer.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="intrepid.html" title="Intrepid">Intrepid</a></td>
    <td>Intrepid is a library of interoperable tools for compatible discretizations of partial differential equations.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="intrepid2.html" title="Intrepid2">Intrepid2</a></td>
    <td>Performance portable tools for the local assembly of high-order compatible finite element discretizations. Replacement for Intrepid.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="krino.html" title="Krino">Krino</a></td>
    <td>Tools for computing and reinitializing signed distance fields and for creating unstructured stk meshes that conform to level set fields.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="minitensor.html" title="MiniTensor">MiniTensor</a></td>
    <td>Tools for the manipulation and optimization of small vectors/tensors.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="pamgen.html" title="PAMGEN">PAMGEN</a></td>
    <td>PAMGEN creates hexahedral or quadrilateral (in 2D) finite element meshes of simple shapes (cubes and cylinders) in parallel.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="panzer.html" title="Panzer">Panzer</a></td>
    <td>Panzer is a package for performing finite element analysis.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="percept.html" title="Percept">Percept</a></td>
    <td>A collection of tools, including mesh adaptation and data transfer, to enable solution verification.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="phalanx.html" title="Phalanx">Phalanx</a></td>
    <td>Phalanx is a DAG-based local field evaluation kernel specifically designed for general partial differential equation solvers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="shards.html" title="Shards">Shards</a></td>
    <td>Topology data for mesh-based discretization of differential equations.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="stk.html" title="STK">STK</a></td>
    <td>Contains capabilities intended to support massively parallel multi-physics computations on dynamically changing unstructured meshes. The primary capability in the STK package is the mesh database which supports creation and manipulation of mesh entities (nodes, elements etc) and computational field data defined on the mesh. STK also contains sub-libraries that support geometric proximity searches, assembly into linear-systems, etc.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="teko.html" title="Teko">Teko</a></td>
    <td>Teko means “fuse” in Greek. This is suggestive of what Teko does, bringing together multiple physics to form one preconditioner.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Nonlinear, Transient, and Optimization Solvers</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="nox_and_loca.html" title="NOX and LOCA">NOX</a></td>
    <td>Nonlinear solver package. Abstract and concrete classes for construction and solution of nonlinear problems.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="nox_and_loca.html" title="NOX and LOCA">LOCA</a></td>
    <td>LOCA is a software library for performing bifurcation analysis of large-scale applications. When implemented with an application code, LOCA enables the tracking of solution branches as a function of system parameters and the direct tracking of bifurcation points. LOCA is designed to drive application codes that use Newton’s method to locate steady-state solutions to nonlinear problems.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="rol.html" title="Rapid Optimization Library (ROL)">ROL</a></td>
    <td>Rapid Optimization Library (ROL) is Trilinos’ next-generation package for large-scale optimization. It is used for the solution of optimal design, optimal control and inverse problems in large-scale engineering applications. Other uses include mesh optimization and image processing. ROL solves nonlinear nonconvex optimization problems with general equality and inequality constraints, with efficient specializations for various problem types. ROL’s matrix-free API enables direct use of application data structures and memory spaces, linear solvers, nonlinear solvers and preconditioners.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="tempus.html" title="Tempus">Tempus</a></td>
    <td>Time-integration framework for advanced transient analysis, including various time integrators and embedded sensitivity analysis.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Interfaces and Adapters</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="fortrilinos.html" title="ForTrilinos">ForTrilinos</a></td>
    <td>ForTrilinos provides object-oriented Fortran interfaces to Trilinos C++ packages.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="piro.html" title="Piro">Piro</a></td>
    <td>Piro provides driver classes for the common uses of Trilinos nonlinear analysis tools.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="pytrilinos.html" title="PyTrilinos">PyTrilinos</a></td>
    <td>Python interfaces to selected Trilinos packages.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="pytrilinos2.html" title="PyTrilinos2">PyTrilinos2</a></td>
    <td>Replacement for PyTrilinos.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="stratimikos.html" title="Stratimikos">Stratimikos</a></td>
    <td>The package Stratimikos contains a unified set of Thyra-based wrappers to linear solver and preconditioner capabilities in Trilinos. The Stratimikos package is also a place where unified testing of linear solvers and preconditioners can be performed.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="thyra.html" title="Thyra">Thyra</a></td>
    <td>Abstract linear solver package. Provides foundation for writing linear and nonlinear abstract numerical algorithms and interfaces to linear solvers and preconditioners (see Stratimikos).</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="trilinoscouplings.html" title="Trilinos Couplings">TrilinosCouplings</a></td>
    <td>A collection of interfaces between packages.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⚠️</td>
    <td><a href="triutils.html" title="TriUtils">TriUtils</a></td>
    <td>TriUtils a package of utilities for other Trilinos packages.</td>
  </tr>
  <tr style="background-color: lightgray;">
    <td colspan="3"><strong>Archived Packages</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="claps.html" title="Claps">Claps</a></td>
    <td>Claps is a collection of domain decomposition preconditioners and solvers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="didasko.html" title="Didasko">Didasko</a></td>
    <td>Didasko, the tutorial of Trilinos, offers a quick introduction to several Trilinos packages.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="domi.html" title="Domi">Domi</a></td>
    <td>Domi provides multi-dimensional distributed linear algebra services.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="fei.html" title="FEI">FEI</a></td>
    <td>A general interface for assembling finite-element data into a system of linear equations.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="globipack.html" title="GlobiPack">GlobiPack</a></td>
    <td>The GlobiPack package contains a set of interfaces and implementations for 1D globalization capabilities to be used in nonlinear solvers, optimization solvers, and similar algorithms that require globalization methods (e.g. line search and trust region methods).</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="komplex.html" title="Komplex">Komplex</a></td>
    <td>Komplex is a complex linear solver package. Solves complex-valued linear systems via equivalent real formulations.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="mesquite.html" title="Mesquite">Mesquite</a></td>
    <td>MESQUITE is a linkable software library that applies a variety of node-movement algorithms to improve the quality and/or adapt a given mesh.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="moertel.html" title="Moertel">Moertel</a></td>
    <td>This package supplies capabilities for nonconforming mesh tying and contact formulations in 2 and 3 dimensions using Mortar methods.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="moocho.html" title="MOOCHO">MOOCHO</a></td>
    <td>MOOCHO (Multifunctional Object-Oriented arCHitecture for Optimization) is designed to solve large-scale, equality and inequality nonlinearly constrained, non-convex optimization problems (i.e. nonlinear programs) using reduced-space successive quadratic programming (SQP) methods.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="new_package.html" title="New Package">New Package</a></td>
    <td>New Package was a template in the early days of Trilinos, meant to help developers create their own new Trilinos package.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="optipack.html" title="Optika">Optika</a></td>
    <td>The OptiPack package contains interfaces and concrete implementations of some basic optimization algorithms based on Thyra.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="rythmos.html" title="Rythmos">Rythmos</a></td>
    <td>Rythmos is a transient integrator for ordinary differential equations and differential-algebraic equations with support for explicit, implicit, one-step and multi-step algorithms. Replaced by Tempus.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="trios.html" title="Trios">Trios</a></td>
    <td>The Trios (Trilinos I/O Support) package provides libraries to support the development of distributed data services on HPC platforms.</td>
  </tr>
  <tr>
    <td style="text-align: center;">⛔</td>
    <td><a href="web_trilinos.html" title="Web Trilinos">WebTrilinos</a></td>
    <td>WebTrilinos is a scientific portal, a web-based environment to use several Trilinos packages through the web.</td>
  </tr>
</table>

<strong>Package Status*</strong>

- 🛠️ Actively Developed 
- ✅ Supported Package 
- ⚠️  Planned Archival/Deprecation
- 📸 Snap-shotted Package
- ⛔ Archived/Deprecated Package
