---
title: Packages by Area 
permalink: packages-by-area.html
keywords: Area Leads, Core Area, Solvers Area, Discretization and Analysis Area, Performance Portability, Linear Solvers, Preconditioners, Discretization Tools, Nonlinear Solvers, Transient Solvers, Optimization, Automatic Differentiation, Uncertainty Quantification, Mesh and Geometry Tools, Partitioning and Load Balancing, Interfaces and Adapters, Utilities, Adelus, Amesos2, Anasazi, Belos, Compadre, Galeri, Ifpack2, Intrepid2, Kokkos, Kokkos Kernels, Krino, LOCA, MiniTensor, MueLu, NOX, PAMGEN, Panzer, Percept, Phalanx, Piro, PyTrilinos2, ROL, RTOp, Sacado, SEACAS, Shards, ShyLU, STK, Stokhos, Stratimikos, Teuchos, Tempus, Thyra, Teko, Tpetra, Zoltan, Zoltan2
---

## Trilinos Area Leads

In the Trilinos project, **Area Leads** play a vital role in overseeing specific areas or components of the software framework. They are responsible for coordinating the needs and requirements of stakeholders, facilitating requests, and managing inter-package interactions. By actively engaging with the community, Area Leads gather valuable feedback to ensure that the packages effectively meet user needs.

Additionally, they are instrumental in creating and maintaining comprehensive documentation for their packages, as well as providing essential support to users. With significant expertise in their respective fields, Area Leads contribute to the strategic direction of the Trilinos project. Their efforts are crucial for the ongoing development, maintenance, and enhancement of Trilinos packages, ensuring that the software remains both relevant and of high quality.

The Trilinos packages are organized into three main areas: **Core**, **Solvers**, and **Discretization and Analysis**.  
This page groups Trilinos packages according to the **capability areas** listed on the [Trilinos Capabilities](capabilities.html) page, and identifies the responsibility of the corresponding **Area Lead**.

Additionally, the <a href="download.html#devsecops-team" title="DevSecOps">**DevSecOps** team</a> handles the Continuous Integration and Continuous Deployment (CI/CD) processes for Trilinos.

---

## Core Area
- **Capabilities**: Performance Portability; Partitioning and Load Balancing; Interfaces and Adapters; and Utilities
- **Description**: This area includes capabilities that provide basic functionalities utilized by many applications and other packages.
- **Lead**: Roger Pawlowski  <a href="https://github.com/rppawlo">@rppawlo</a>

<table>
  <tr style="background-color: lightblue;">
    <th><strong>Capability Area</strong></th>
    <th><strong>Package</strong></th>
    <th><strong>Description</strong></th>
    <th><strong>Link(s)</strong></th>
  </tr>

  <!-- Performance Portability -->
  <tr>
    <td rowspan="3"><strong>Performance Portability</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/kokkos">Kokkos</a></td>
    <td>Performance portability library.<sup>&ast;</sup></td>
    <td><a href="docs/kokkos/index.html">Doxygen</a> <a href="https://github.com/kokkos/kokkos">Primary Repo</a> <a href="https://kokkos.org/kokkos-core-wiki/">Documentation</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/kokkos-kernels">Kokkos Kernels</a></td>
    <td>Mathematical kernels for node-local computations.<sup>&ast;</sup></td>
    <td><a href="https://github.com/kokkos/kokkos-kernels">Primary Repo</a> <a href="https://kokkos.org/kokkos-kernels/docs/">Documentation</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/tpetra">Tpetra</a></td>
    <td>Distributed-memory linear algebra objects and parallel data redistribution.</td>
    <td><a href="docs/tpetra/index.html">Doxygen</a></td>
  </tr>

  <!-- Partitioning and Load Balancing -->
  <tr>
    <td rowspan="2"><strong>Partitioning and Load Balancing</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/zoltan">Zoltan</a></td>
    <td>Toolkit of parallel services including load balancing.</td>
    <td><a href="https://sandialabs.github.io/Zoltan/">Documentation</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/zoltan2">Zoltan2</a></td>
    <td>Load balancing and combinatorial scientific computing.</td>
    <td><a href="docs/zoltan2/index.html">Doxygen</a></td>
  </tr>

  <!-- Interfaces and Adapters -->
  <tr>
    <td rowspan="5"><strong>Interfaces and Adapters</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/stratimikos">Stratimikos</a></td>
    <td>Unified Thyra-based wrappers to linear solver and preconditioner capabilities.</td>
    <td><a href="docs/stratimikos/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/PyTrilinos2">PyTrilinos2</a></td>
    <td>Python interfaces to several Trilinos packages.</td>
    <td>N/A</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/thyra">Thyra</a></td>
    <td>Abstract numerical algorithm interfaces and foundations for solvers.</td>
    <td><a href="docs/thyra/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/rtop">RTOp</a></td>
    <td>Reduction/transformation operators for vector operations.</td>
    <td><a href="docs/rtop/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/piro">Piro</a></td>
    <td>Driver classes for common uses of Trilinos nonlinear analysis tools.</td>
    <td><a href="docs/piro/index.html">Doxygen</a></td>
  </tr>

  <!-- Utilities -->
  <tr>
    <td rowspan="3"><strong>Utilities</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/teuchos">Teuchos</a></td>
    <td>Common tools: smart pointers, parameter lists, XML, BLAS/LAPACK wrappers, etc.</td>
    <td><a href="docs/teuchos/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/galeri">Galeri</a></td>
    <td>Utilities to generate a variety of (distributed) linear systems.</td>
    <td><a href="docs/galeri/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/minitensor">MiniTensor</a></td>
    <td>Tools for the manipulation and optimization of small vectors/tensors.</td>
    <td>N/A</td>
  </tr>
</table>

---

## Solvers Area
- **Capabilities**: Linear Solvers; and Preconditioners
- **Description**: This area includes packages that provide preconditioners, linear/nonlinear solvers, and eigen solvers.
- **Lead**: Jonathan Hu <a href="https://github.com/jhux2">@jhux2</a>

<table>
  <tr style="background-color: lightyellow;">
    <th><strong>Capability Area</strong></th>
    <th><strong>Package</strong></th>
    <th><strong>Description</strong></th>
    <th><strong>Link(s)</strong></th>
  </tr>

  <!-- Linear Solvers -->
  <tr>
    <td rowspan="5"><strong>Linear Solvers</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/belos">Belos</a></td>
    <td>Iterative linear solvers framework.</td>
    <td><a href="docs/belos/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/amesos2">Amesos2</a></td>
    <td>Direct solver library interface to third-party solvers.</td>
    <td><a href="docs/amesos2/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/shylu">ShyLU</a></td>
    <td>Sparse direct solvers and domain decomposition methods (includes FROSch).</td>
    <td><a href="docs/shylu/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/adelus">Adelus</a></td>
    <td>Dense LU factorization and solve on distributed systems (MPI).</td>
    <td><a href="docs/adelus/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/anasazi">Anasazi</a></td>
    <td>Framework for large-scale eigenvalue algorithms.</td>
    <td><a href="docs/anasazi/index.html">Doxygen</a></td>
  </tr>

  <!-- Preconditioners -->
  <tr>
    <td rowspan="3"><strong>Preconditioners</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/ifpack2">Ifpack2</a></td>
    <td>Incomplete factorizations, relaxations, and domain decomposition for Tpetra objects.</td>
    <td><a href="docs/ifpack2/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/muelu">MueLu</a></td>
    <td>Multigrid solvers and preconditioners for PDE-based sparse systems.</td>
    <td><a href="docs/muelu/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/teko">Teko</a></td>
    <td>Physics-based block preconditioners for multiphysics systems.</td>
    <td><a href="docs/teko/index.html">Doxygen</a></td>
  </tr>
</table>


---

## Discretization and Analysis Area
- **Capabilities**: Discretization Tools; Nonlinear, Transient, and Optimization Solvers; Automatic Differentiation; Uncertainty Quantification; and Mesh and Geometry Tools
- **Description**: This area features packages that offer modular, interoperable, and extensible tools, often build upon the capabilities provided by the Core and Solvers areas. These tools support the discretization of integral and differential equations, including both mesh-based approaches (e.g., finite element analysis), and meshless methods (e.g., generalized moving least squares).
- **Lead**: Mauro Perego <a href="https://github.com/mperego">@mperego</a>

<table>
  <tr style="background-color: lightgreen;">
    <th><strong>Capability Area</strong></th>
    <th><strong>Package</strong></th>
    <th><strong>Description</strong></th>
    <th><strong>Link(s)</strong></th>
  </tr>

  <!-- Discretization Tools -->
  <tr>
    <td rowspan="4"><strong>Discretization Tools</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/intrepid2">Intrepid2</a></td>
    <td>Performance portable tools for local assembly of high-order finite element discretizations.</td>
    <td><a href="docs/intrepid2/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/panzer">Panzer</a></td>
    <td>Finite element assembly for multiphysics systems.</td>
    <td><a href="docs/panzer/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/phalanx">Phalanx</a></td>
    <td>DAG-based local field evaluation and dependency management.</td>
    <td><a href="docs/phalanx/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/compadre">Compadre</a></td>
    <td>Toolkit for meshless discretizations and data transfer.<sup>&ast;</sup></td>
    <td><a href="https://github.com/sandialabs/compadre">Primary Repo</a> <a href="docs/compadre/index.html">Doxygen</a></td>
  </tr>

  <!-- Nonlinear, Transient, and Optimization Solvers -->
  <tr>
    <td rowspan="4"><strong>Nonlinear, Transient, and Optimization Solvers</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/nox">NOX</a></td>
    <td>Nonlinear solvers (Newton-based methods, globalization, JFNK, etc.).</td>
    <td><a href="docs/nox/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/nox">LOCA</a></td>
    <td>Continuation and stability analysis (subpackage of NOX).</td>
    <td><a href="docs/nox/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/tempus">Tempus</a></td>
    <td>Time-integration framework for transient analysis.</td>
    <td><a href="docs/tempus/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/rol">ROL</a></td>
    <td>Rapid Optimization Library for large-scale optimization.<sup>&ast;</sup></td>
    <td><a href="https://github.com/sandialabs/rol">Primary Repo</a> <a href="docs/rol/index.html">Doxygen</a></td>
  </tr>

  <!-- Automatic Differentiation -->
  <tr>
    <td><strong>Automatic Differentiation</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/sacado">Sacado</a></td>
    <td>Automatic differentiation tools (forward, reverse, Taylor polynomial modes).</td>
    <td><a href="docs/sacado/index.html">Doxygen</a></td>
  </tr>

  <!-- Uncertainty Quantification -->
  <tr>
    <td><strong>Uncertainty Quantification</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/stokhos">Stokhos</a></td>
    <td>Intrusive stochastic Galerkin uncertainty quantification methods.</td>
    <td><a href="docs/stokhos/index.html">Doxygen</a></td>
  </tr>

  <!-- Mesh and Geometry Tools -->
  <tr>
    <td rowspan="6"><strong>Mesh and Geometry Tools</strong></td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/pamgen">PAMGEN</a></td>
    <td>Creates hexahedral or quadrilateral finite element meshes of simple shapes in parallel.</td>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/pamgen/doc/sand_report">Report</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/seacas">SEACAS</a></td>
    <td>Pre/post-processing tools supporting Exodus database file format.<sup>&ast;</sup></td>
    <td><a href="https://github.com/sandialabs/seacas">Primary Repo</a> <a href="https://sandialabs.github.io/seacas-docs/sphinx/html/index.html">Documentation</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/stk">STK</a></td>
    <td>Massively parallel multiphysics on dynamically changing unstructured meshes.<sup>&ast;</sup></td>
    <td><a href="pages/packages/stk/STKManual_2024-07-12-final.pdf">Manual</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/percept">Percept</a></td>
    <td>Tools for mesh adaptation and data transfer to enable solution verification.<sup>&ast;</sup></td>
    <td><a href="https://github.com/sandialabs/percept">Primary Repo</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/shards">Shards</a></td>
    <td>Topology data for mesh-based discretization of differential equations.</td>
    <td><a href="docs/shards/index.html">Doxygen</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/krino">Krino</a></td>
    <td>Signed distance fields and STK meshes conforming to level set fields.<sup>&ast;</sup></td>
    <td>N/A</td>
  </tr>
</table>

<sup>&ast;</sup> Snapshotted package: this code is maintained in its upstream repository and periodically merged (snapshotted) into Trilinos.
