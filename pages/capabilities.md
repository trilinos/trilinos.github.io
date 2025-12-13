---
title: Trilinos Capabilities
permalink: capabilities.html
show_sidebar: true
sidebar: nav
keywords: Trilinos capabilities, Scientific computing framework, High-performance computing tools, Performance portability, Parallel computing architectures, Distributed-memory systems, Sparse matrix operations, Linear solvers, Nonlinear solvers, Optimization solvers, Eigensolvers, Preconditioners, Multigrid methods, Domain decomposition, Automatic differentiation, Uncertainty quantification, Stochastic methods, Mesh generation, Mesh manipulation, Mesh I/O, Mesh refinement and adaptivity, Mesh quality assessment, Mesh-based data transfer, Finite element assembly, Field evaluation, Meshless discretization, Partitioning and load balancing, Multiphysics simulations, Scalability, Leadership-class systems, Numerical analysis, Engineering applications, Scientific applications, Kokkos, Tpetra, Teuchos, Intrepid2, Panzer, Phalanx, Compadre, Zoltan, Zoltan2, Ifpack2, FROSch, MueLu, Teko, Belos, Amesos2, ShyLU, Adelus, Anasazi, NOX, LOCA, Tempus, ROL, Sacado, Stokhos, Stratimikos, PyTrilinos2, Thyra, Parallel execution, Memory management, Hierarchical parallelism, Graph algorithms, MPI-based communication, Halo exchange, Multidimensional arrays, PDE assembly, Jacobian computation, Sensitivity analysis, Polynomial chaos expansions, Block-structured linear systems, Ensemble-based simulations, GPU-based systems, CUDA, HIP, SYCL, Python wrappers, Unified solver interface, Abstract numerical algorithms, HPC tools
---


Trilinos is a comprehensive software framework for scientific computing, providing a wide range of capabilities for solving complex engineering and scientific problems. Below is a categorized list of Trilinos capabilities with detailed descriptions.

---

## Performance Portability and Core Utilities

- **Performance Portability**  
  Tools for enabling efficient computation across diverse hardware architectures, including CPUs, GPUs, and emerging HPC systems. Capabilities include abstractions for parallel execution, memory spaces, and hierarchical parallelism.  Support for expressing parallel computations at multiple levels, including thread, team, and vector levels, ensuring efficient utilization of hardware resources.  Abstractions for memory management, including multidimensional arrays with customizable memory layouts and traits for optimized data access patterns.  _Provided by: <a href="https://kokkos.org/" title="Kokkos">Kokkos</a>_

- **Mathematical Kernels for Node-Local Computations**  
  Performance-portable implementations of mathematical kernels for dense and sparse linear algebra, graph algorithms, and batched computations. Capabilities include optimized sparse matrix operations, efficient BLAS routines, graph-based computations, and integration with vendor-optimized libraries. Thread-safe and asynchronous implementations ensure efficient concurrent execution and scalability.  _Provided by: <a href="https://kokkos.org/" title="Kokkos Kernels">Kokkos Kernels</a>_

- **Distributed-Memory Linear Algebra**  
  Scalable infrastructure for distributed-memory computations, providing linear algebra objects such as sparse matrices, dense vectors, and graphs. Supports efficient parallel operations using MPI-based communication, including sparse matrix-vector multiplication, matrix-matrix multiplication, and graph-based operations. Features include data redistribution, halo exchange, and flexible templated objects for compatibility with diverse applications and architectures. Essential for large-scale simulations on leadership-class systems.  _Provided by: <a href="tpetra.html" title="Tpetra">Tpetra</a>_

- **Utility and Helper Tools**  
  Collection of tools for memory management, parameter lists, templated wrappers for BLAS/LAPACK, and XML parsing. These utilities simplify programming tasks and ensure consistent coding practices.  _Provided by: <a href="teuchos.html" title="Teuchos">Teuchos</a>_

---

## Linear Solvers

- **Iterative Linear Solvers**  
  Comprehensive suite of iterative solvers for linear systems, including Krylov methods such as CG, GMRES, MINRES, and BiCGStab. These solvers support block and pseudo-block methods for solving systems with multiple right-hand sides, as well as advanced techniques like flexible GMRES and pipelined CG.  _Provided by: <a href="belos.html" title="Belos">Belos</a>_

- **Direct Linear Solvers**  
  Direct solvers for sparse linear systems, including interfaces to third-party solvers and node-local solvers optimized for shared-memory architectures. These solvers are essential for problems requiring robust and accurate solutions, such as circuit simulations and mechanics applications.  _Provided by: <a href="amesos2.html" title="Amesos2">Amesos2</a>, <a href="shylu.html" title="ShyLU">ShyLU</a>, <a href="adelus.html" title="Adelus">Adelus</a>_

- **Large-Scale Eigenvalue Algorithms**  
  Framework for solving large-scale eigenvalue problems, including methods such as block Davidson, Krylov-Schur, locally optimal block preconditioned conjugate gradient (LOBPCG), and trace minimization. These algorithms are designed to handle large, sparse matrices arising in scientific and engineering applications, providing flexibility and scalability for diverse use cases.  _Provided by: <a href="anasazi.html" title="Anasazi">Anasazi</a>_

---

## Preconditioners

- **One-Level Domain Decomposition**  
  Overlapping additive Schwarz methods for preconditioning, with options for local subdomain solves such as incomplete LU factorizations and direct solvers. These methods accelerate iterative solvers and include classic iterative techniques like Jacobi, Gauss-Seidel, and Chebyshev iterations, optimized for shared-memory architectures.  _Provided by: <a href="ifpack2.html" title="Ifpack2">Ifpack2</a>_

- **Multilevel Domain Decomposition**  
  Multilevel Schwarz preconditioners that emphasize scalability and robustness across challenging problems. These preconditioners support extension-based coarse spaces and are designed for algebraic construction, relying solely on the sparsity pattern of the system matrix. They have demonstrated scalability to hundreds of thousands of cores on supercomputers.  _Provided by: <a href="https://shylu-frosch.github.io/" title="FROSch">FROSch</a>_

- **Multigrid Methods**  
  Scalable multigrid solvers for a wide range of PDEs, including Poisson-like operators, elasticity, convection-diffusion, and Maxwell’s equations. These solvers include aggregation-based algebraic multigrid methods, semi-coarsening for structured grids, and specialized solvers for multiphysics problems.  _Provided by: <a href="muelu.html" title="MueLu">MueLu</a>_

- **Physics-Based Block Preconditioners**  
  Block preconditioning strategies for multiphysics problems, leveraging the block structure of matrices to create efficient solvers. Strategies include block LU factorizations, SIMPLEC, LSC, and PCD preconditioners, with flexibility for defining custom inverse approximations for Schur complements.  _Provided by: <a href="teko.html" title="Teko">Teko</a>_

---

## Discretization Utilities

- **Finite Element Local Assembly**  
  Tools for local assembly of finite element matrices and vectors, supporting high-order compatible discretizations for function spaces such as H(grad), H(curl), H(div), and L<sup>2</sup>. Capabilities include geometric operations, basis functions, orientation tools, and projection methods for efficient finite element computations.  _Provided by: <a href="intrepid2.html" title="Intrepid2">Intrepid2</a>_

- **Finite Element Assembly for Multiphysics Systems**  
  Tools for efficient finite element assembly, supporting mixed bases, multiphysics systems, and high-order discretizations. Capabilities include dependency management, distributed assembly, and support for block or fully coupled systems. Integrated with automatic differentiation for Jacobians and sensitivities, enabling scalable simulations and optimization.  _Provided by: <a href="panzer.html" title="Panzer">Panzer</a>_

- **Field Evaluation and Dependency Management**  
  Graph-based design for managing dependencies in PDE assembly, enabling rapid prototyping and integration of automatic differentiation tools. These capabilities support efficient evaluation of fields and derivatives, automating the computation of Jacobians, sensitivities, and other quantities required for nonlinear solvers and optimization.  _Provided by: <a href="phalanx.html" title="Phalanx">Phalanx</a>_

- **Meshless Approximation of Linear Operators**  
  Tools for meshless approximation of linear operators using generalized moving least squares (GMLS). These capabilities support applications such as data transfer and meshless discretization of PDEs, leveraging hierarchical parallelism for performance portability.  _Provided by: <a href="compadre.html" title="Compadre">Compadre</a>_

---

## Nonlinear, Transient, and Optimization Solvers

- **Nonlinear Solvers**  
  Algorithms for solving nonlinear equations, including Newton-based methods, line search, trust region, and homotopy techniques. These solvers support Jacobian-free Newton-Krylov variants and provide robust options for handling large-scale nonlinear systems.  _Provided by: <a href="nox_and_loca.html" title="NOX">NOX</a>_

- **Continuation and Stability Analysis**  
  Techniques for tracking solution families and investigating stability, including pseudo-arclength continuation, bifurcation tracking, and eigenvalue analysis. These capabilities are widely used in applications such as fluid dynamics and chemical reactor design.  _Provided by: <a href="nox_and_loca.html" title="LOCA">LOCA</a>_

- **Transient Solvers**  
  Framework for time integration, supporting explicit and implicit methods for first- and second-order ODEs. Capabilities include error control, sensitivity analysis, and transient optimization, making them suitable for simulations ranging from small systems to exascale computing.  _Provided by: <a href="tempus.html" title="Tempus">Tempus</a>_

- **Optimization Solvers**  
  State-of-the-art algorithms for constrained and unconstrained optimization, including trust-region methods, stochastic optimization, and nonsmooth optimization. These solvers support matrix-free computations and integrate seamlessly with PDE models for efficient optimization.  _Provided by: <a href="rol.html" title="ROL">ROL</a>_

---

## Automatic Differentiation

- **Forward and Reverse Mode AD**  
  Tools for automatic differentiation using operator overloading, enabling efficient computation of derivatives for complex models. These capabilities integrate with performance-portable architectures, making them suitable for GPU-based systems and large-scale applications.  _Provided by: <a href="sacado.html" title="Sacado">Sacado</a>_

---

## Uncertainty Quantification

- **Uncertainty Quantification and Stochastic Methods**  
  Tools for intrusive uncertainty quantification methods, including stochastic Galerkin projections and embedded ensemble propagation. Capabilities include efficient computation of polynomial chaos expansions, block-structured linear systems, and scalable ensemble-based simulations. Optimized for performance on modern architectures, enabling uncertainty propagation in large-scale multiphysics systems.  _Provided by: <a href="stokhos.html" title="Stokhos">Stokhos</a>_

---

## Partitioning and Load Balancing

- **Partitioning and Load Balancing**  
  Tools for efficiently partitioning and distributing data objects such as sparse matrices across processors, ensuring balanced computational loads and minimizing communication overhead. These capabilities include support for hybrid parallelism and advanced algorithms like geometric partitioning, spectral graph partitioning, graph coloring, and MPI task placement.  _Provided by: <a href="zoltan.html" title="Zoltan">Zoltan</a>, <a href="zoltan2.html" title="Zoltan">Zoltan2</a>_

---

## Mesh and Geometry Tools

- **Mesh Generation**  
  Tools for generating meshes for computational simulations, including structured, unstructured, and hybrid meshes. These capabilities support the creation of meshes for complex geometries and multiphysics applications.  _Provided by: <a href="pamgen.html" title="PAMGEN">PAMGEN</a>_

- **Mesh Manipulation**  
  Utilities for modifying meshes, including operations such as mesh refinement, coarsening, and partitioning. These tools allow users to adapt meshes to specific simulation requirements or improve computational efficiency.  _Provided by: <a href="https://github.com/sandialabs/seacas" title="SEACAS">SEACAS</a>, <a href="stk.html" title="STK">STK</a>, <a href="percept.html" title="Percept">Percept</a>_

- **Mesh I/O**  
  Support for reading and writing mesh data in various formats, including Exodus, NetCDF, and other widely used formats in scientific computing. These capabilities enable interoperability with external mesh generation and visualization tools. Integration with visualization tools for inspecting and analyzing mesh structures and simulation results. These capabilities include support for exporting data to visualization software such as ParaView and VisIt. _Provided by: <a href="https://github.com/sandialabs/seacas" title="SEACAS">SEACAS</a>, <a href="stk.html" title="STK">STK</a>_

- **Cell Topology**  
  Tools for defining and querying cell topology, including support for triangles, quadrilaterals, tetrahedrons, hexahedrons, wedges, and pyramids. These capabilities are essential for finite element and finite volume discretizations.  _Provided by: <a href="shards.html" title="Shards">Shards</a>_

- **Level-Set Methods**  
  Capabilities for handling level-set representations of geometries, enabling simulations involving moving boundaries, interfaces, and topological changes. These methods are particularly useful for fluid-structure interaction and multiphase flow problems.  _Provided by: <a href="krino.html" title="Krino">Krino</a>_

- **Mesh Refinement and Adaptivity**  
  Tools for refining and adapting meshes based on simulation results, including error indicators and solution gradients. These capabilities ensure accurate and efficient simulations by dynamically adjusting the mesh resolution.  _Provided by: <a href="stk.html" title="STK">STK</a>_

- **Mesh Quality Assessment**  
  Utilities for assessing and improving mesh quality, including metrics for element shape, size, and aspect ratio. These tools help ensure that meshes are suitable for high-fidelity simulations.  _Provided by: <a href="https://github.com/sandialabs/seacas" title="SEACAS">SEACAS</a>, <a href="percept.html" title="Percept">Percept</a>_

- **Mesh-Based Data Transfer**  
  Support for transferring data between meshes, including interpolation and projection methods for scalar, vector, and tensor fields. These capabilities are critical for multiphysics simulations and coupling between different models.  
  _Provided by: <a href="https://github.com/sandialabs/seacas" title="SEACAS">SEACAS</a>, <a href="stk.html" title="STK">STK</a>_

---

## Interfaces and Adapters

- **Unified Solver Interface**  
  Cohesive interface to linear solvers and preconditioners, enabling runtime configuration through parameter lists. This interface simplifies solver management for complex applications and supports integration with multiple linear algebra backends.  _Provided by: <a href="stratimikos.html" title="Stratimikos">Stratimikos</a>_

- **Python Wrappers**  
  Python interfaces for selected capabilities, enabling rapid prototyping and algorithm development. These wrappers provide access to linear algebra, solvers, and preconditioners for efficient experimentation and integration.  _Provided by: <a href="pytrilinos2.html" title="PyTrilinos2">PyTrilinos2</a>_

- **Abstract Numerical Algorithms**  
  Interfaces for implementing high-level abstract numerical algorithms, enabling separation of algorithm development from linear algebra implementation. These abstractions support efficient reuse across multiple applications.  _Provided by: <a href="thyra.html" title="Thyra">Thyra</a>_

---

Trilinos continues to evolve, providing cutting-edge tools for scientific computing while maintaining performance portability across diverse hardware architectures.

## Trilinos Packages

<a href="packages-by-area.html" title="Trilinos Packages by Area">Trilinos Packages by Area.</a>


