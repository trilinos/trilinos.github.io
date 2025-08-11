---
title: Packages by Area 
permalink: packages-by-area.html
---

# Trilinos Area Leads

In the Trilinos project, **Area Leads** play a vital role in overseeing specific areas or components of the software framework. They are responsible for coordinating the needs and requirements of stakeholders, facilitating requests, and managing inter-package interactions. By actively engaging with the community, Area Leads gather valuable feedback to ensure that the packages effectively meet user needs.

Additionally, they are instrumental in creating and maintaining comprehensive documentation for their packages, as well as providing essential support to users. With significant expertise in their respective fields, Area Leads contribute to the strategic direction of the Trilinos project. Their efforts are crucial for the ongoing development, maintenance, and enhancement of Trilinos packages, ensuring that the software remains both relevant and of high quality.

The Trilinos packages are organized into four main areas: **Core**, **Solvers**, **Discretization and Analysis**, and **DevSecOps**.

## Core Area
- **Description**: This area includes packages that provide basic capabilities utilized by many applications and other packages.
- **Lead**: Roger Pawlowski  <a href="https://github.com/rppawlo">@rppawlo</a>

<table>
  <tr style="background-color: lightblue;">
    <td><strong>Status*</strong></td>
    <td><strong>Package</strong></td>
    <td><strong>Description</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="galeri.html" title="Galeri">Galeri</a></td>
    <td>A suite of utilities and classes to generate a variety of (distributed) linear systems.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="https://github.com/kokkos" title="Kokkos">Kokkos</a></td>
    <td>Performance portability library.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="pamgen.html" title="PAMGEN">PAMGEN</a></td>
    <td>Creates hexahedral or quadrilateral (in 2D) finite element meshes of simple shapes (cubes and cylinders) in parallel.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="pytrilinos2.html" title="PyTrilinos2">PyTrilinos2</a></td>
    <td>Replacement for PyTrilinos.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="rtop.html" title="RTop">RTop</a></td>
    <td>Provides the basic mechanism for implementing vector operations in a flexible and efficient manner.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="https://github.com/sandialabs/seacas" title="SEACAS">SEACAS</a></td>
    <td>A suite of preprocessing, postprocessing, translation, and utility applications supporting finite element analysis software using the Exodus database file format.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="teuchos.html" title="Teuchos">Teuchos</a></td>
    <td>Provides a suite of common tools for Trilinos developers, including BLAS and LAPACK wrappers, smart pointers, parameter lists, and XML parsers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="tpetra.html" title="Tpetra">Tpetra</a></td>
    <td>Implements linear algebra objects, including sparse graphs, sparse matrices, and dense vectors, with facilities for parallel data redistribution.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="thyra.html" title="Thyra">Thyra</a></td>
    <td>Abstract linear solver package providing a foundation for writing linear and nonlinear abstract numerical algorithms.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="zoltan.html" title="Zoltan">Zoltan</a></td>
    <td>A toolkit of parallel services for dynamic, unstructured, and/or adaptive simulations, providing load balancing and related services.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="zoltan2.html" title="Zoltan2">Zoltan2</a></td>
    <td>A package for load balancing and combinatorial scientific computing, viewed as a successor to Zoltan and Isorropia.</td>
  </tr>
</table>

## Solvers Area
- **Description**: This area includes packages that provide preconditioners, linear/nonlinear solvers, and eigen solvers.
- **Lead**: Jonathan Hu  <a href="https://github.com/jhux2">@jhux2</a>

<table>
  <tr style="background-color: lightyellow;">
    <td><strong>Status*</strong></td>
    <td><strong>Package</strong></td>
    <td><strong>Description</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="adelus.html" title="Adelus">Adelus</a></td>
    <td>Performs LU factorization with partial pivoting and solves for a dense linear equation system on a distributed computing system using MPI.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="amesos2.html" title="Amesos2">Amesos2</a></td>
    <td>Direct solver library interface in Trilinos, providing interfaces to third-party direct solvers for templated matrices and vectors.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="anasazi.html" title="Anasazi">Anasazi</a></td>
    <td>An extensible and interoperable framework for large-scale eigenvalue algorithms.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="belos.html" title="Belos">Belos</a></td>
    <td>Next-generation iterative solvers written using a traits interface, compatible with any linear algebra library implementing Thyra abstract interfaces.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="ifpack2.html" title="Ifpack2">Ifpack2</a></td>
    <td>Provides incomplete factorizations, relaxations, and domain decomposition operators for linear algebra objects provided by the Tpetra package.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="muelu.html" title="Muelu">Muelu</a></td>
    <td>Designed to solve large sparse linear systems of equations arising from PDE discretizations, providing multigrid solvers and preconditioners.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="shylu.html" title="ShyLU">ShyLU</a></td>
    <td>Package for solving sparse linear systems using domain decomposition methods, focusing on distributed memory and node-level solvers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="stratimikos.html" title="Stratimikos">Stratimikos</a></td>
    <td>Contains a unified set of Thyra-based wrappers to linear solver and preconditioner capabilities in Trilinos.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="teko.html" title="Teko">Teko</a></td>
    <td>Brings together multiple physics to form one preconditioner.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="xpetra.html" title="Xpetra">Xpetra</a></td>
    <td>A lightweight wrapper to both the Epetra and Tpetra linear algebra libraries, mirroring Tpetra's syntax.</td>
  </tr>
</table>

## Discretization and Analysis Area
- **Description**: This area includes packages that provide modular, interoperable, and extensible tools, often built on packages from the Core and Solvers Areas.  Provides modular, interoperable and extensible tools for the discretization of integral and differential equations, and includes tools for mesh-based discretizations such as finite element analysis as well as meshless discretization such as generalized moving least squares.
- **Lead**: Mauro Perego  <a href="https://github.com/mperego">@mperego</a>

<table>
  <tr style="background-color: lightgreen;">
    <td><strong>Status*</strong></td>
    <td><strong>Package</strong></td>
    <td><strong>Description</strong></td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="compadre.html" title="Compadre">Compadre</a></td>
    <td>Toolkit for meshless discretizations enabling the solution of differential equations and data transfer.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="intrepid2.html" title="Intrepid2">Intrepid2</a></td>
    <td>Performance portable tools for the local assembly of high-order compatible finite element discretizations.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="krino.html" title="Krino">Krino</a></td>
    <td>Tools for computing and reinitializing signed distance fields and creating unstructured STK meshes that conform to level set fields.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="minitensor.html" title="MiniTensor">MiniTensor</a></td>
    <td>Tools for the manipulation and optimization of small vectors/tensors.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="panzer.html" title="Panzer">Panzer</a></td>
    <td>Package for performing finite element analysis.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="percept.html" title="Percept">Percept</a></td>
    <td>A collection of tools for mesh adaptation and data transfer to enable solution verification.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="phalanx.html" title="Phalanx">Phalanx</a></td>
    <td>DAG-based local field evaluation kernel designed for general partial differential equation solvers.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="piro.html" title="Piro">Piro</a></td>
    <td>Provides driver classes for common uses of Trilinos nonlinear analysis tools.</td>
  </tr>
  <tr>
    <td style="text-align: center;">🛠️</td>
    <td><a href="rol.html" title="Rapid Optimization Library (ROL)">ROL</a></td>
    <td>Next-generation package for large-scale optimization, solving optimal design, control, and inverse problems.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="sacado.html" title="Sacado">Sacado</a></td>
    <td>Package for automatic differentiation of C++ programs, providing classes for forward, reverse, and Taylor polynomial mode.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="shards.html" title="Shards">Shards</a></td>
    <td>Topology data for mesh-based discretization of differential equations.</td>
  </tr>
  <tr>
    <td style="text-align: center;">📸</td>
    <td><a href="stk.html" title="STK">STK</a></td>
    <td>Supports massively parallel multi-physics computations on dynamically changing unstructured meshes.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="stokhos.html" title="Stokhos">Stokhos</a></td>
    <td>Package for intrusive stochastic Galerkin uncertainty quantification methods.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="tempus.html" title="Tempus">Tempus</a></td>
    <td>Time-integration framework for advanced transient analysis, including various time integrators.</td>
  </tr>
  <tr>
    <td style="text-align: center;">✅</td>
    <td><a href="trilinoscouplings.html" title="Trilinos Couplings">TrilinosCouplings</a></td>
    <td>A collection of interfaces between packages.</td>
  </tr>
</table>

## DevSecOps Team
- **Description**: Provides streamlined processes and a set of tools for the development of Trilinos packages.
- **Lead**: Sam Browne  [@sebrowne](https://github.com/sebrowne)
- **Responsibilities**:
  - Implements various development, testing, automation tools, and IT infrastructure.
  - Defines and sets development, test, release, update, and support processes.
  - Organizes and maintains the Trilinos release process.
- **Team Members**:
  - Anderson Chauphan  [@achauphan](https://github.com/achauphan)
  - Joe Frye  [@fryeguy52](https://github.com/fryeguy52)
  - Justin LaPre  [@jmlapre](https://github.com/jmlapre)


<strong>Package Status*</strong>

- 🛠️ Actively Developed 
- ✅ Supported Package 
- ⚠️  Planned Archival/Deprecation
- 📸 Snap-shotted Package
- ⛔ Archived/Deprecated Package
