---
title: Trilinos Capabilities
permalink: capabilities.html
show_sidebar: true
sidebar: nav
keywords: Trilinos capabilities, Scientific computing framework, High-performance computing tools, Performance portability, Parallel computing architectures, Distributed-memory systems, Sparse matrix operations, Linear solvers, Nonlinear solvers, Optimization solvers, Eigensolvers, Preconditioners, Multigrid methods, Domain decomposition, Automatic differentiation, Uncertainty quantification, Stochastic methods, Mesh generation, Mesh manipulation, Mesh I/O, Mesh refinement and adaptivity, Mesh quality assessment, Mesh-based data transfer, Finite element assembly, Field evaluation, Meshless discretization, Partitioning and load balancing, Multiphysics simulations, Scalability, Leadership-class systems, Numerical analysis, Engineering applications, Scientific applications, Kokkos, Tpetra, Teuchos, Intrepid2, Panzer, Phalanx, Compadre, Zoltan, Zoltan2, Ifpack2, FROSch, MueLu, Teko, Belos, Amesos2, ShyLU, Adelus, Anasazi, NOX, LOCA, Tempus, ROL, Sacado, Stokhos, Stratimikos, PyTrilinos2, Thyra, Parallel execution, Memory management, Hierarchical parallelism, Graph algorithms, MPI-based communication, Halo exchange, Multidimensional arrays, PDE assembly, Jacobian computation, Sensitivity analysis, Polynomial chaos expansions, Block-structured linear systems, Ensemble-based simulations, GPU-based systems, CUDA, HIP, SYCL, Python wrappers, Unified solver interface, Abstract numerical algorithms, HPC tools
---


Trilinos is a comprehensive software framework for scientific computing, providing a wide range of capabilities for solving complex engineering and scientific problems. Below is a categorized list of Trilinos capabilities with detailed descriptions.

---

## Performance Portability

- <strong>Performance Portability</strong> <span style="float:right;"><em>Provided by: <a href="https://kokkos.org/">Kokkos</a> </em></span><br /> 
  Tools for enabling efficient computation across diverse hardware architectures, including CPUs, GPUs, and emerging HPC systems. Capabilities include abstractions for parallel execution, memory spaces, and hierarchical parallelism.  Support for expressing parallel computations at multiple levels, including thread, team, and vector levels, ensuring efficient utilization of hardware resources.  Abstractions for memory management, including multidimensional arrays with customizable memory layouts and traits for optimized data access patterns.

- <strong>Mathematical Kernels for Node-Local Computations</strong> <span style="float:right;"><em>Provided by: <a href="https://kokkos.org/">Kokkos Kernels</a> </em></span><br /> 
  Performance-portable implementations of mathematical kernels for dense and sparse linear algebra, graph algorithms, and batched computations. Capabilities include optimized sparse matrix operations, efficient BLAS routines, graph-based computations, and integration with vendor-optimized libraries. Thread-safe and asynchronous implementations ensure efficient concurrent execution and scalability.

- <strong>Distributed-Memory Linear Algebra</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/tpetra#readme">Tpetra</a> </em></span><br />
  Scalable infrastructure for distributed-memory computations, providing linear algebra objects such as sparse matrices, dense vectors, and graphs. Supports efficient parallel operations using MPI-based communication, including sparse matrix-vector multiplication, matrix-matrix multiplication, and graph-based operations. Features include data redistribution, halo exchange, and flexible templated objects for compatibility with diverse applications and architectures. Essential for large-scale simulations on leadership-class systems.

---

## Linear Solvers

- <strong>Iterative Linear Solvers</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/belos#readme">Belos</a> </em></span><br />
  Comprehensive suite of iterative solvers for linear systems, including Krylov methods such as CG, GMRES, MINRES, and BiCGStab. These solvers support block and pseudo-block methods for solving systems with multiple right-hand sides, as well as advanced techniques like flexible GMRES and pipelined CG.

- <strong>Direct Linear Solvers</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/amesos2#readme">Amesos2</a>, <a href="shylu">ShyLU</a>, <a href="https://github.com/trilinos/Trilinos/blob/master/packages/adelus/README.md">Adelus</a> </em></span><br />
  Direct solvers for sparse linear systems, including interfaces to third-party solvers and node-local solvers optimized for shared-memory architectures. These solvers are essential for problems requiring robust and accurate solutions, such as circuit simulations and mechanics applications.

- <strong>Large-Scale Eigenvalue Algorithms</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/anasazi#readme">Anasazi</a> </em></span><br />
  Framework for solving large-scale eigenvalue problems, including methods such as block Davidson, Krylov-Schur, locally optimal block preconditioned conjugate gradient (LOBPCG), and trace minimization. These algorithms are designed to handle large, sparse matrices arising in scientific and engineering applications, providing flexibility and scalability for diverse use cases.

---

## Preconditioners

- <strong>One-Level Domain Decomposition</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/ifpack2#readme">Ifpack2</a> </em></span><br />
  Overlapping additive Schwarz methods for preconditioning, with options for local subdomain solves such as incomplete LU factorizations and direct solvers. These methods accelerate iterative solvers and include classic iterative techniques like Jacobi, Gauss-Seidel, and Chebyshev iterations, optimized for shared-memory architectures.

- <strong>Multilevel Domain Decomposition</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/shylu#readme">ShyLU</a> (subpackage FROSch)</em></span><br />
  Multilevel Schwarz preconditioners that emphasize scalability and robustness across challenging problems. These preconditioners support extension-based coarse spaces and are designed for algebraic construction, relying solely on the sparsity pattern of the system matrix. They have demonstrated scalability to hundreds of thousands of cores on supercomputers.

- <strong>Multigrid Methods</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/muelu#readme">MueLu</a> </em></span><br />
  Scalable multigrid solvers for a wide range of PDEs, including Poisson-like operators, elasticity, convection-diffusion, and Maxwell’s equations. These solvers include aggregation-based algebraic multigrid methods, semi-coarsening for structured grids, and specialized solvers for multiphysics problems.

- <strong>Physics-Based Block Preconditioners</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/teko#readme">Teko</a> </em></span><br />
  Block preconditioning strategies for multiphysics problems, leveraging the block structure of matrices to create efficient solvers. Strategies include block LU factorizations, SIMPLEC, LSC, and PCD preconditioners, with flexibility for defining custom inverse approximations for Schur complements.

---

## Discretization Utilities

- <strong>Finite Element Local Assembly</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/intrepid2#readme">Intrepid2</a> </em></span><br />
  Tools for local assembly of finite element matrices and vectors, supporting high-order compatible discretizations for function spaces such as H(grad), H(curl), H(div), and L<sup>2</sup>. Capabilities include geometric operations, basis functions, orientation tools, and projection methods for efficient finite element computations.

- <strong>Finite Element Assembly for Multiphysics Systems</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/panzer#readme">Panzer</a> </em></span><br />
  Tools for efficient finite element assembly, supporting mixed bases, multiphysics systems, and high-order discretizations. Capabilities include dependency management, distributed assembly, and support for block or fully coupled systems. Integrated with automatic differentiation for Jacobians and sensitivities, enabling scalable simulations and optimization.

- <strong>Field Evaluation and Dependency Management</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/phalanx#readme">Phalanx</a> </em></span><br />
  Graph-based design for managing dependencies in PDE assembly, enabling rapid prototyping and integration of automatic differentiation tools. These capabilities support efficient evaluation of fields and derivatives, automating the computation of Jacobians, sensitivities, and other quantities required for nonlinear solvers and optimization.

- <strong>Meshless Approximation of Linear Operators</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/compadre#readme">Compadre</a> </em></span><br />
  Tools for meshless approximation of linear operators using generalized moving least squares (GMLS). These capabilities support applications such as data transfer and meshless discretization of PDEs, leveraging hierarchical parallelism for performance portability.

---

## Nonlinear, Transient, and Optimization Solvers

- <strong>Nonlinear Solvers</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/nox#readme">NOX</a> </em></span><br />
  Algorithms for solving nonlinear equations, including Newton-based methods, line search, trust region, and homotopy techniques. These solvers support Jacobian-free Newton-Krylov variants and provide robust options for handling large-scale nonlinear systems.

- <strong>Continuation and Stability Analysis</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/nox#readme">NOX</a> (subpackage LOCA)</em></span><br />
  Techniques for tracking solution families and investigating stability, including pseudo-arclength continuation, bifurcation tracking, and eigenvalue analysis. These capabilities are widely used in applications such as fluid dynamics and chemical reactor design.

- <strong>Transient Solvers</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/tempus#readme">Tempus</a> </em></span><br />
  Framework for time integration, supporting explicit and implicit methods for first- and second-order ODEs. Capabilities include error control, sensitivity analysis, and transient optimization, making them suitable for simulations ranging from small systems to exascale computing.

- <strong>Optimization Solvers</strong> <span style="float:right;"><em>Provided by: <a href="https://rol.sandia.gov/">ROL</a> </em></span><br />
  State-of-the-art algorithms for constrained and unconstrained optimization, including trust-region methods, stochastic optimization, and non-smooth optimization. These solvers support matrix-free computations and integrate seamlessly with PDE models for efficient optimization.

---

## Automatic Differentiation

- <strong>Forward and Reverse Mode AD</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/sacado#readme">Sacado</a> </em></span><br />
  Tools for automatic differentiation using operator overloading, enabling efficient computation of derivatives for complex models. These capabilities integrate with performance-portable architectures, making them suitable for GPU-based systems and large-scale applications.

---

## Uncertainty Quantification

- <strong>Uncertainty Quantification and Stochastic Methods</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/stokhos#readme">Stokhos</a> </em></span><br />
  Tools for intrusive uncertainty quantification methods, including stochastic Galerkin projections and embedded ensemble propagation. Capabilities include efficient computation of polynomial chaos expansions, block-structured linear systems, and scalable ensemble-based simulations. Optimized for performance on modern architectures, enabling uncertainty propagation in large-scale multiphysics systems.

---

## Partitioning and Load Balancing

- <strong>Partitioning and Load Balancing</strong> <span style="float:right;"><em>Provided by: <a href="https://sandialabs.github.io/Zoltan/">Zoltan</a>, <a href="https://github.com/trilinos/Trilinos/tree/master/packages/zoltan2#readme">Zoltan2</a> </em></span><br />
  Tools for efficiently partitioning and distributing data objects such as sparse matrices across processors, ensuring balanced computational loads and minimizing communication overhead. These capabilities include support for hybrid parallelism and advanced algorithms like geometric partitioning, spectral graph partitioning, graph coloring, and MPI task placement.

---

## Mesh and Geometry Tools

- <strong>Mesh Generation</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/pamgen#readme">PAMGEN</a> </em></span><br />
  Tools for generating meshes for computational simulations, including structured, unstructured, and hybrid meshes. These capabilities support the creation of meshes for complex geometries and multiphysics applications.

- <strong>Mesh Manipulation</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/sandialabs/seacas">SEACAS</a>, <a href="https://github.com/trilinos/Trilinos/tree/master/packages/stk">STK</a>, <a href="https://github.com/trilinos/Trilinos/tree/master/packages/percept#readme">Percept</a> </em></span><br />
  Utilities for modifying meshes, including operations such as mesh refinement, coarsening, and partitioning. These tools allow users to adapt meshes to specific simulation requirements or improve computational efficiency.

- <strong>Mesh I/O</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/sandialabs/seacas">SEACAS</a>, <a href="https://github.com/trilinos/Trilinos/tree/master/packages/st">STK</a> </em></span><br />
  Support for reading and writing mesh data in various formats, including Exodus, NetCDF, and other widely used formats in scientific computing. These capabilities enable interoperability with external mesh generation and visualization tools. Integration with visualization tools for inspecting and analyzing mesh structures and simulation results. These capabilities include support for exporting data to visualization software such as ParaView and VisIt.

- <strong>Cell Topology</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/shards#readme">Shards</a> </em></span><br />
  Tools for defining and querying cell topology, including support for triangles, quadrilaterals, tetrahedrons, hexahedrons, wedges, and pyramids. These capabilities are essential for finite element and finite volume discretizations.

- <strong>Level-Set Methods</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/krino">Krino</a> </em></span><br />
  Capabilities for handling level-set representations of geometries, enabling simulations involving moving boundaries, interfaces, and topological changes. These methods are particularly useful for fluid-structure interaction and multiphase flow problems.

- <strong>Mesh Refinement and Adaptivity</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/stk">STK</a> </em></span><br />
  Tools for refining and adapting meshes based on simulation results, including error indicators and solution gradients. These capabilities ensure accurate and efficient simulations by dynamically adjusting the mesh resolution.

- <strong>Mesh Quality Assessment</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/sandialabs/seacas">SEACAS</a>, <a href="https://github.com/trilinos/Trilinos/tree/master/packages/percept#readme">Percept</a> </em></span><br />
  Utilities for assessing and improving mesh quality, including metrics for element shape, size, and aspect ratio. These tools help ensure that meshes are suitable for high-fidelity simulations.

- <strong>Mesh-Based Data Transfer</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/sandialabs/seacas">SEACAS</a>, <a href="https://github.com/trilinos/Trilinos/tree/master/packages/stk">STK</a> </em></span><br />
  Support for transferring data between meshes, including interpolation and projection methods for scalar, vector, and tensor fields. These capabilities are critical for multiphysics simulations and coupling between different models.  


---

## Interfaces and Adapters

- <strong>Unified Solver Interface</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/stratimikos#readme">Stratimikos</a> </em></span><br />
  Cohesive interface to linear solvers and preconditioners, enabling runtime configuration through parameter lists. This interface simplifies solver management for complex applications and supports integration with multiple linear algebra backends.

- <strong>Python Wrappers</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/PyTrilinos2#readme">pytrilinos2</a> </em></span><br />
  Python interfaces for selected capabilities, enabling rapid prototyping and algorithm development. These wrappers provide access to linear algebra, solvers, and preconditioners for efficient experimentation and integration.

- <strong>Abstract Numerical Algorithms</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/thyra#readme">Thyra</a> </em></span><br />
  Interfaces for implementing high-level abstract numerical algorithms, enabling separation of algorithm development from linear algebra implementation. These abstractions support efficient reuse across multiple applications.

- <strong>Reduction/Transformation Operators</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/rtop#readme">RTOp</a> </em></span><br />
  Framework for defining and applying reduction and transformation operators to distributed data structures, enabling efficient parallel computations. These capabilities support flexible operations on vectors and other data types, ensuring scalability and performance.

- <strong>Simulation and Optimization Interface</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/piro#readme">Piro</a> </em></span><br />
  High-level interface for coupling simulation and optimization algorithms, supporting transient and steady-state simulations, as well as sensitivity analysis. Piro integrates with other Trilinos packages to streamline the development of multiphysics and optimization workflows.

---

## Utilities

- <strong>Utility and Helper Tools</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/teuchos#readme">Teuchos</a> </em></span><br />
  Collection of tools for memory management, parameter lists, templated wrappers for BLAS/LAPACK, and XML parsing. These utilities simplify programming tasks and ensure consistent coding practices.

- <strong>Matrix-Free Linear Algebra</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/galeri#readme">Galeri</a> </em></span><br />
  Tools for generating test problems and matrix-free linear algebra objects, including structured grids and finite difference operators. Galeri provides a lightweight and flexible framework for prototyping and testing numerical algorithms.

- <strong>Tensor Algebra Utilities</strong> <span style="float:right;"><em>Provided by: <a href="https://github.com/trilinos/Trilinos/tree/master/packages/minitensor#readme">MiniTensor</a> </em></span><br />
  Compact library for tensor algebra, supporting operations on small tensors, vectors, and matrices. MiniTensor is optimized for performance and portability, making it suitable for applications in mechanics and material modeling.

---

Trilinos continues to evolve, providing cutting-edge tools for scientific computing while maintaining performance portability across diverse hardware architectures.

## Trilinos Packages

[Trilinos Packages by Area](packages-by-area)


