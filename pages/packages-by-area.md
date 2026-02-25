---
title: Packages by Area 
permalink: packages-by-area.html
keywords: Area Leads, Core Area, Solvers Area, Discretization and Analysis Area, Linear Systems, Performance Portability, Finite Element Analysis, Preconditioners, Eigen Solvers, Optimization, Mesh Adaptation, Stochastic Methods, Adelus, Amesos2, Anasazi, Belos, Compadre, Galeri, Ifpack2, Intrepid2, Kokkos, Krino, MiniTensor, MueLu, PAMGEN, Panzer, Percept, Phalanx, Piro, PyTrilinos2, ROL, RTop, Rapid Optimization Library, SEACAS, STK, Sacado, Shards, ShyLU, Stokhos, Stratimikos, Teko, Tempus, Teuchos, Thyra, Tpetra, TrilinosCouplings, Xpetra, Zoltan, Zoltan2, Trilinos package descriptions, Trilinos package documentation, Trilinos Doxygen, Trilinos GitHub repository, Trilinos continuous integration (CI), Trilinos continuous deployment (CD), Trilinos package teams, Trilinos package leads, Trilinos modular framework, Trilinos interoperability, Trilinos scalability, Trilinos finite element analysis, Trilinos mesh adaptation, Trilinos stochastic methods, Trilinos optimization, Trilinos linear solvers, Trilinos nonlinear solvers, Trilinos eigen solvers, Trilinos preconditioners, Trilinos time integration, Trilinos transient analysis, Trilinos data transfer, Trilinos DAG-based field evaluation, Trilinos meshless discretization, Trilinos high-order finite element discretizations, Trilinos signed distance fields, Trilinos unstructured meshes, Trilinos parallel services, Trilinos load balancing, Trilinos combinatorial scientific computing, Trilinos smart pointers, Trilinos BLAS and LAPACK wrappers, Trilinos XML parsers, Trilinos vector operations, Trilinos parallel data redistribution, Trilinos abstract numerical algorithms, Trilinos linear algebra libraries, Trilinos unified solver interface, Trilinos automatic differentiation, Trilinos stochastic Galerkin methods, Trilinos uncertainty quantification, Trilinos PDE discretizations, Trilinos multigrid solvers, Trilinos domain decomposition methods, Trilinos distributed computing, Trilinos MPI support, Trilinos CUDA support, Trilinos Kokkos ecosystem, Trilinos performance portability, Trilinos massively parallel computations, Trilinos multi-physics computations, Trilinos interfaces between packages, Trilinos Couplings, Trilinos legacy packages, Trilinos experimental tools, Trilinos utilities
---

## Trilinos Area Leads

In the Trilinos project, **Area Leads** play a vital role in overseeing specific areas or components of the software framework. They are responsible for coordinating the needs and requirements of stakeholders, facilitating requests, and managing inter-package interactions. By actively engaging with the community, Area Leads gather valuable feedback to ensure that the packages effectively meet user needs.

Additionally, they are instrumental in creating and maintaining comprehensive documentation for their packages, as well as providing essential support to users. With significant expertise in their respective fields, Area Leads contribute to the strategic direction of the Trilinos project. Their efforts are crucial for the ongoing development, maintenance, and enhancement of Trilinos packages, ensuring that the software remains both relevant and of high quality.

The Trilinos packages are organized into three main areas: **Core**, **Solvers**, and **Discretization and Analysis**.  Additionally, the <a href="download.html#devsecops-team" title="DevSecOps">**DevSecOps** team</a>  handles the Continuous Integration and Continuous Deployment (CI/CD) processes for Trilinos.

## Core Area
- **Description**: This area includes packages that provide basic capabilities utilized by many applications and other packages.
- **Lead**: Roger Pawlowski  <a href="https://github.com/rppawlo">@rppawlo</a>

<table>
  <tr style="background-color: lightblue;">
    <th><strong>GitHub</strong></th>
    <th><strong>Description</strong></th>
    <th><strong>Team</strong></th>
    <th><strong>Team Lead</strong></th>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/galeri">Galeri</a></td>
    <td><div>A suite of utilities and classes to generate a variety of (distributed) linear systems.</div><div style="margin-left: 1.5em;"><a href="docs/galeri/index.html">Galeri Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/galeri">@galeri</a></td>
    <td><a href="mailto:jhu@sandia.gov">Jonathan Hu</a> (<a href="https://github.com/jhux2">@jhux2</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/kokkos">Kokkos</a></td>
    <td><div>Performance portability library.</div><div style="margin-left: 1.5em;"><a href="https://kokkos.org/kokkos-core-wiki/">Kokkos documentation</a></div></td>
    <td><a href="https://kokkos.org/community/team/">Kokkos team</a></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/kokkos-kernels">Kokkos Kernels</a></td>
    <td><div>Mathematical Kernels for Node-Local Computations</div><div style="margin-left: 1.5em;"><a href="https://kokkos.org/kokkos-kernels/docs/">Kokkos Kernels documentation</a></div></td>
    <td><a href="https://kokkos.org/community/team/">Kokkos team</a></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/pamgen">PAMGEN</a></td>
    <td><div>Creates hexahedral or quadrilateral (in 2D) finite element meshes of simple shapes (cubes and cylinders) in parallel.</div><div style="margin-left: 1.5em;"><a href="https://github.com/trilinos/Trilinos/tree/master/packages/pamgen/doc/sand_report">PAMGEN documentation</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/pamgen">@pamgen</a></td>
    <td><a href="mailto:rppawlo@sandia.gov">Roger Pawlowski</a> (<a href="https://github.com/rppawlo">@rppawlo</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/PyTrilinos2">PyTrilinos2</a></td>
    <td><div>Python interfaces to several Trilinos packages.</div><div style="margin-left: 1.5em;">N/A</div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/pytrilinos2">@pytrilinos2</a></td>
    <td><a href="mailto:caglusa@sandia.gov">Christian Glusa</a> (<a href="https://github.com/cgcgcg">@cgcgcg</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/rtop">RTOp</a></td>
    <td><div>Provides the basic mechanism for implementing vector operations in a flexible and efficient manner.</div><div style="margin-left: 1.5em;"><a href="docs/rtop/index.html">RTOp Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/rtop">@rtop</a></td>
    <td><a href="mailto:rabartl@sandia.gov">Roscoe A. Bartlett</a> (<a href="https://github.com/bartlettroscoe">@bartlettroscoe</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/seacas">SEACAS</a></td>
    <td><div>A suite of preprocessing, postprocessing, translation, and utility applications supporting finite element analysis software using the Exodus database file format.</div><div style="margin-left: 1.5em;"><a href="https://sandialabs.github.io/seacas-docs/sphinx/html/index.html">SEACAS Documentation</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/seacas">@seacas</a></td>
    <td><a href="mailto:tookusa@sandia.gov">Tolu Okusanya</a> (<a href="https://github.com/tokusanya">@tokusanya</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/teuchos">Teuchos</a></td>
    <td><div>Provides a suite of common tools for Trilinos developers, including BLAS and LAPACK wrappers, smart pointers, parameter lists, and XML parsers.</div><div style="margin-left: 1.5em;"><a href="docs/teuchos/index.html">Teuchos Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/teuchos">@teuchos</a></td>
    <td><a href="mailto:rppawlo@sandia.gov">Roger Pawlowski</a> (<a href="https://github.com/rppawlo">@rppawlo</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/tpetra">Tpetra</a></td>
    <td><div>Implements linear algebra objects, including sparse graphs, sparse matrices, and dense vectors, with facilities for parallel data redistribution.</div><div style="margin-left: 1.5em;"><a href="docs/tpetra/index.html">Tpetra Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/teuchos">@teuchos</a></td>
    <td><a href="mailto:csiefer@sandia.gov">Chris Siefert</a> (<a href="https://github.com/csiefer2">@csiefer2</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/thyra">Thyra</a></td>
    <td><div>Abstract linear solver package providing a foundation for writing linear and nonlinear abstract numerical algorithms.</div><div style="margin-left: 1.5em;"><a href="docs/thyra/index.html">Thyra Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/thyra">@thyra</a></td>
    <td><a href="mailto:rabartl@sandia.gov">Roscoe A. Bartlett</a> (<a href="https://github.com/bartlettroscoe">@bartlettroscoe</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/zoltan">Zoltan</a></td>
    <td><div>A toolkit of parallel services for dynamic, unstructured, and/or adaptive simulations, providing load balancing and related services.</div><div style="margin-left: 1.5em;"><a href="https://github.com/trilinos/Trilinos/tree/master/packages/zoltan/doc">Zoltan documentation</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/zoltan">@zoltan</a></td>
    <td><a href="mailto:egboman@sandia.gov">Erik Boman</a> (<a href="https://github.com/egboman">@egboman</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/zoltan2">Zoltan2</a></td>
    <td><div>A package for load balancing and combinatorial scientific computing, viewed as a successor to Zoltan and Isorropia.</div><div style="margin-left: 1.5em;"><a href="docs/zoltan2/index.html">Zoltan2 Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/zoltan2">@zoltan2</a></td>
    <td><a href="mailto:egboman@sandia.gov">Erik Boman</a> (<a href="https://github.com/egboman">@egboman</a>)</td>
  </tr>
</table>

## Solvers Area
- **Description**: This area includes packages that provide preconditioners, linear/nonlinear solvers, and eigen solvers.
- **Lead**: Jonathan Hu  <a href="https://github.com/jhux2">@jhux2</a>

<table>
  <tr style="background-color: lightyellow;">
    <td><strong>GitHub</strong></td>
    <td><strong>Description</strong></td>
    <td><strong>Team</strong></td>
    <td><strong>Team Lead</strong></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/adelus">Adelus</a></td>
    <td><div>Performs LU factorization with partial pivoting and solves for a dense linear equation system on a distributed computing system using MPI.</div><div style="margin-left: 1.5em;"><a href="docs/adelus/index.html">Adelus Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/adelus">@adelus</a></td>
    <td><a href="mailto:vqdang@sandia.gov">Vinh Dang</a> (<a href="https://github.com/vqd8a">@vqd8a</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/amesos2">Amesos2</a></td>
    <td><div>Direct solver library interface in Trilinos, providing interfaces to third-party direct solvers for templated matrices and vectors.</div><div style="margin-left: 1.5em;"><a href="docs/amesos2/index.html">Amesos2 Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/amesos2">@amesos2</a></td>
    <td><a href="mailto:iyamaza@sandia.gov">Ichi Yamazaki</a> (<a href="https://github.com/iyamazaki">@iyamazaki</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/anasazi">Anasazi</a></td>
    <td><div>An extensible and interoperable framework for large-scale eigenvalue algorithms.</div><div style="margin-left: 1.5em;"><a href="docs/anasazi/index.html">Anasazi Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/anasazi">@anasazi</a></td>
    <td><a href="mailto:hkthorn@sandia.gov">Heidi Thornquist</a> (<a href="https://github.com/hkthorn">@hkthorn</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/belos">Belos</a></td>
    <td><div>Next-generation iterative solvers written using a traits interface, compatible with any linear algebra library implementing Thyra abstract interfaces.</div><div style="margin-left: 1.5em;"><a href="docs/belos/index.html">Belos Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/belos">@belos</a></td>
    <td><a href="mailto:hkthorn@sandia.gov">Heidi Thornquist</a> (<a href="https://github.com/hkthorn">@hkthorn</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/ifpack2">Ifpack2</a></td>
    <td><div>Provides incomplete factorizations, relaxations, and domain decomposition operators for linear algebra objects provided by the Tpetra package.</div><div style="margin-left: 1.5em;"><a href="docs/ifpack2/index.html">Ifpack2 Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/ifpack2">@ifpack2</a></td>
    <td><a href="mailto:csiefer@sandia.gov">Chris Siefert</a> (<a href="https://github.com/csiefer2">@csiefer2</a>), <a href="mailto:jhu@sandia.gov">Jonathan Hu</a> (<a href="https://github.com/jhux2">@jhux2</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/muelu">MueLu</a></td>
    <td><div>Designed to solve large sparse linear systems of equations arising from PDE discretizations, providing multigrid solvers and preconditioners.</div><div style="margin-left: 1.5em;"><a href="docs/muelu/index.html">MueLu Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/muelu">@muelu</a></td>
    <td><a href="mailto:jhu@sandia.gov">Jonathan Hu</a> (<a href="https://github.com/jhux2">@jhux2</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/nox">NOX</a></td>
    <td><div>Implements a variety of Newton-based globalization techniques including Line Search and Trust Region algorithms. Provides higher and lower order models using Broyden and Tensor algorithms. Special algorithms for use with inexact linear solvers such as Krylov subspace techniques.</div><div style="margin-left: 1.5em;"><a href="docs/nox/index.html">NOX Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/nox">@nox</a></td>
    <td><a href="mailto:rppawlo@sandia.gov">Roger Pawlowski</a> (<a href="https://github.com/rppawlo">@rppawlo</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/shylu">ShyLU</a></td>
    <td><div>Package for solving sparse linear systems using domain decomposition methods, focusing on distributed memory and node-level solvers.</div><div style="margin-left: 1.5em;"><a href="docs/shylu/index.html">ShyLU Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/shylu">@shylu</a></td>
    <td><a href="mailto:iyamaza@sandia.gov">Ichi Yamazaki</a> (<a href="https://github.com/iyamazaki">@iyamazaki</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/stratimikos">Stratimikos</a></td>
    <td><div>Contains a unified set of Thyra-based wrappers to linear solver and preconditioner capabilities in Trilinos.</div><div style="margin-left: 1.5em;"><a href="docs/stratimikos/index.html">Stratimikos Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/stratimikos">@stratimikos</a></td>
    <td><a href="mailto:rabartl@sandia.gov">Roscoe A. Bartlett</a> (<a href="https://github.com/bartlettroscoe">@bartlettroscoe</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/teko">Teko</a></td>
    <td><div>Brings together multiple physics to form one preconditioner.</div><div style="margin-left: 1.5em;"><a href="docs/teko/index.html">Teko Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/teko">@teko</a></td>
    <td><a href="mailto:malphil@sandia.gov">Malachi Phillips</a> (<a href="https://github.com/MalachiTimothyPhillips">@MalachiTimothyPhillips</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/xpetra">Xpetra</a></td>
    <td><div>A lightweight wrapper to both the Epetra and Tpetra linear algebra libraries, mirroring Tpetra's syntax.</div><div style="margin-left: 1.5em;"><a href="docs/xpetra/index.html">Xpetra Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/xpetra">@xpetra</a></td>
    <td><a href="mailto:jhu@sandia.gov">Jonathan Hu</a> (<a href="https://github.com/jhux2">@jhux2</a>)</td>
  </tr>
</table>

## Discretization and Analysis Area
- **Description**: This area features packages that offer modular, interoperable, and extensible tools, often build upon the capabilities provided by the Core and Solvers areas. These tools support the discretization of integral and differential equations, including both mesh-based approaches (e.g., finite element analysis), and meshless methods (e.g., generalized moving least squares).
- **Lead**: Mauro Perego  <a href="https://github.com/mperego">@mperego</a>

<table>
  <tr style="background-color: lightgreen;">
    <td><strong>GitHub</strong></td>
    <td><strong>Description</strong></td>
    <td><strong>Team</strong></td>
    <td><strong>Team Lead</strong></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/compadre">Compadre</a></td>
    <td><div>Toolkit for meshless discretizations enabling the solution of differential equations and data transfer.</div><div style="margin-left: 1.5em;"><a href="docs/compadre/index.html">Compadre Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/compadre">@compadre</a></td>
    <td><a href="mailto:pakuber@sandia.gov">Paul Kuberry</a> (<a href="https://github.com/kuberry">@kuberry</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/intrepid2">Intrepid2</a></td>
    <td><div>Performance portable tools for the local assembly of high-order compatible finite element discretizations.</div><div style="margin-left: 1.5em;"><a href="docs/intrepid2/index.html">Intrepid2 Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/intrepid2">@intrepid2</a></td>
    <td><a href="mailto:mperego@sandia.gov">Mauro Perego</a> (<a href="https://github.com/mperego">@mperego</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/krino">Krino</a></td>
    <td><div>Tools for computing and reinitializing signed distance fields and creating unstructured STK meshes that conform to level set fields.</div><div style="margin-left: 1.5em;">N/A</div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/krino">@krino</a></td>
    <td><a href="mailto:drnoble@sandia.gov">David Noble</a> (<a href="https://github.com/drnobleabq">@drnobleabq</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/minitensor">MiniTensor</a></td>
    <td><div>Tools for the manipulation and optimization of small vectors/tensors.</div><div style="margin-left: 1.5em;">N/A</div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/minitensor">@minitensor</a></td>
    <td><a href="mailto:amota@sandia.gov">Alejandro Mota</a> (<a href="https://github.com/lxmota">@lxmota</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/panzer">Panzer</a></td>
    <td><div>Package for performing finite element analysis.</div><div style="margin-left: 1.5em;"><a href="docs/panzer/index.html">Panzer Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/panzer">@panzer</a></td>
    <td><a href="mailto:rppawlo@sandia.gov">Roger Pawlowski</a> (<a href="https://github.com/rppawlo">@rppawlo</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/percept">Percept</a></td>
    <td><div>A collection of tools for mesh adaptation and data transfer to enable solution verification.</div><div style="margin-left: 1.5em;">N/A</div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/percept">@percept</a></td>
    <td><a href="mailto:rppawlo@sandia.gov">Roger Pawlowski</a> (<a href="https://github.com/rppawlo">@rppawlo</a>), <a href="mailto:bcarnes@sandia.gov">Brian Carnes</a></td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/phalanx">Phalanx</a></td>
    <td><div>DAG-based local field evaluation kernel designed for general partial differential equation solvers.</div><div style="margin-left: 1.5em;"><a href="docs/phalanx/index.html">Phalanx Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/phalanx">@phalanx</a></td>
    <td><a href="mailto:rppawlo@sandia.gov">Roger Pawlowski</a> (<a href="https://github.com/rppawlo">@rppawlo</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/piro">Piro</a></td>
    <td><div>Provides driver classes for common uses of Trilinos nonlinear analysis tools.</div><div style="margin-left: 1.5em;"><a href="docs/piro/index.html">Piro Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/piro">@piro</a></td>
    <td><a href="mailto:mperego@sandia.gov">Mauro Perego</a> (<a href="https://github.com/mperego">@mperego</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/rol">ROL</a></td>
    <td><div>Next-generation package for large-scale optimization, solving optimal design, control, and inverse problems.</div><div style="margin-left: 1.5em;"><a href="docs/rol/index.html">ROL Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/rol">@rol</a></td>
    <td><a href="mailto:dridzal@sandia.gov">Denis Ridzal</a> (<a href="https://github.com/dridzal">@dridzal</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/sacado">Sacado</a></td>
    <td><div>Package for automatic differentiation of C++ programs, providing classes for forward, reverse, and Taylor polynomial mode.</div><div style="margin-left: 1.5em;"><a href="docs/sacado/index.html">Sacado Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/sacado">@sacado</a></td>
    <td><a href="mailto:etphipp@sandia.gov">Eric Phipps</a> (<a href="https://github.com/etphipp">@etphipp</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/shards">Shards</a></td>
    <td><div>Topology data for mesh-based discretization of differential equations.</div><div style="margin-left: 1.5em;"><a href="docs/shards/index.html">Shards Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/shards">@shards</a></td>
    <td><a href="mailto:mperego@sandia.gov">Mauro Perego</a> (<a href="https://github.com/mperego">@mperego</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/stk">STK</a></td>
    <td><div>Supports massively parallel multi-physics computations on dynamically changing unstructured meshes.</div><div style="margin-left: 1.5em;"><a href="pages/packages/stk/STKManual_2024-07-12-final.pdf">STK Manual</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/stk">@stk</a></td>
    <td><a href="mailto:STK-NGPTeam@sandia.gov">STK Team</a> (<a href="https://github.com/orgs/trilinos/teams/stk">@stk</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/stokhos">Stokhos</a></td>
    <td><div>Package for intrusive stochastic Galerkin uncertainty quantification methods.</div><div style="margin-left: 1.5em;"><a href="docs/stokhos/index.html">Stokhos Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/stokhos">@stokhos</a></td>
    <td><a href="mailto:etphipp@sandia.gov">Eric Phipps</a> (<a href="https://github.com/etphipp">@etphipp</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/tempus">Tempus</a></td>
    <td><div>Time-integration framework for advanced transient analysis, including various time integrators.</div><div style="margin-left: 1.5em;"><a href="docs/tempus/index.html">Tempus Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/tempus">@tempus</a></td>
    <td><a href="mailto:ccober@sandia.gov">Curtis Ober</a> (<a href="https://github.com/ccober6">@ccober6</a>)</td>
  </tr>
  <tr>
    <td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/trilinoscouplings">Trilinos Couplings</a></td>
    <td><div>A collection of interfaces between packages.</div><div style="margin-left: 1.5em;"><a href="docs/trilinoscouplings/index.html">Trilinos Couplings Doxygen</a></div></td>
    <td><a href="https://github.com/orgs/trilinos/teams/trilinoscouplings">@trilinoscouplings</a></td>
    <td><a href="mailto:mperego@sandia.gov">Mauro Perego</a> (<a href="https://github.com/mperego">@mperego</a>)</td>
  </tr>
</table>
