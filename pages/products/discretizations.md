---
title: Discretizations
permalink: discretizations.html
folder: products
contact: mperego@sandia.gov
---

The objective of the Discretizations product is to provide modular, interoperable and extensible tools for the discretization of integral and differential equations. Adopting state-of-the-art numerics and HPC programming models, the discretization tools target both research and production applications. The Discretizations product includes tools for mesh-based discretizations such as finite element analysis as well as meshless discretization such as generalized moving least squares. 

Discretizations Product Lead: Mauro Perego (mperego@sandia.gov)

<div class="row">
    <div class="col-sm-2">
     <img border="0" alt="Trilinos Team" src="images/tet1.png">
    </div>
    <div class="col-sm-2">
        <img border="0" alt="Trilinos Team" src="images/tet2.png">
    </div>
    <div class="col-sm-2">
        <img border="0" alt="Trilinos Team" src="images/tet3.png">
    </div>
    <div class="col-sm-2">
        <img border="0" alt="Trilinos Team" src="images/tet4.png">
    </div>
        <div class="col-sm-4">
        <img border="0" alt="Trilinos Team" src="images/slab-mesh-particles.png">
    </div>
</div>

* * *

## Brief summary of available tools.

**Global tools:**

[Panzer](panzer.html)  
The package provides global tools for finite element analysis. It handles continuous and discontinuous high-order compatible finite elements, as implemented in [Intrepid2](intrepid2.html) on unstructured meshes. Panzer relies on [Phalanx](phalanx.html) to manage with efficiency and flexibility the assembly of complex problems. Panzer also enables the solution of nonlinear problems, by interfacing with several Trlinos linear and nonlinear solvers. It computes derivatives and sensitivities through automatic differentiation ([Sacado](sacado.html)). It supports both [Epetra](epetra.html) and [Tpetra](tpetra.html) data structures and achieves performance portability through the [Kokkos](kokkos.html) programming model.

[FEI](fei.html)  
The Finite Element Interface to Linear Solvers (FEI) is a general interface for assembling finite-element data into a linear system of equations. It is an abstraction layer that insulates finite-element application codes from linear-algebra issues such as sparse matrix storage formats and mappings from nodes and solution fields to distributed equation spaces. It puts a common face on various linear solvers, allowing finite-element applications to switch from one solver library to another with minimal changes to application code. FEI provides natural mechanisms for assembling finite-element data such as element-wise stiffness arrays and load vectors, boundary-condition specifications and constraint relations. It accepts data from multi-physics problems, allowing arbitrarily complicated elements with multiple solution fields per node, and cell centered fields. It is designed for use in distributed-memory parallel finite-element applications, to assemble and solve distributed linear systems using scalable underlying solver libraries.

**Model building tools:** 

[Phalanx](phalanx.html)  
The package is a local field evaluation kernel specifically designed for general partial differential equation solvers. The main goal of Phalanx is to decompose a complex problem into a number of simpler problems with managed dependencies to support rapid development and extensibility of the PDE code. Through the use of template metaprogramming concepts, Phalanx supports arbitrary user defined data types and evaluation types. This allows for unprecedented flexibility for direct integration with user applications and provides extensive support for embedded technology such as automatic differentiation for sensitivity analysis and uncertainty quantification.

**Local tools:** 

[Intrepid2](intrepid2.html)  
Intrepid2 provides interoperable tools for compatible discretizations of PDEs. Intrepid2 mainly focus on local assembly of continuous and discontinuous finite elements, and provides tools for finite volume discretizations as well. The present version of Intrepid2 implements compatible finite element spaces of orders up to 10 for *H(grad)*, *H(curl)*, *H(div)* and *L2* function spaces on frequently used elements such as triangles, quadrilaterals, tetrahedrons and hexahedrons. It provides both Lagrangian basis functions and Hierarchical basis functions (currently only for tensor-product topologies). For each space Intrepid2 provides generation of the relevant discrete first and second order differential operators on a single cell. Intrepid2 provides orientation tools for matching the degrees of freedom on shared edges and faces. It also provides projection tools for projecting functions in *H(grad)*, *H(curl)*, *H(div)* and *L2* to the respective discrete spaces. Intrepid2 achieves performance portability using the [Kokkos](kokkos.html) programming model.

[Compadre](compadre.html)  
Compadre toolkit provides tools for the approximation of linear operators applied to a function (including point evaluation and derivatives), given samples of the function over a cloud of points. The toolkit can be used for data transfer applications as well as for meshless discretization of PDEs. The package uses generalized moving least squares for approximating functionals and we plan on implementing other meshless methods like radial basis functions. It achieves performance portability by using [Kokkos](kokkos.html) programming model.

[MiniTensor](minitensor.html)  
The package is a library for the use, manipulation, algebra and optimization of small vectors and tensors and problems that depend on them. It was first conceived and developed for the implementation of complex material models in Albany. Its purpose is to provide a compact representation of vector and tensor expressions. Its emphasis is on ease of use, and accurate algorithms, specifically those used for the development of constitutive models in finite deformation solid mechanics. It is smaller, but more focused than Blitz++, TVMet or Eigen. It is used in both research (Albany/LCM) and production (Sierra/SM) environments.

[Krino](krino.html)  
Krino provides interoperable tools for computing and reinitializing signed distance fields and for creating unstructured stk meshes that conform to level set fields on a non-conforming background mesh. Both scalable Euclidean nearest point methods and fast marching methods are supported for signed distance calculations.

[Intrepid](intrepid.html)  
The package provides interoperable tools for compatible discretizations of PDEs. [Intrepid2](intrepid2.html) is a performance portable implementation of Intrepid. They share most of the functionalities, however Intrepid, while still maintained, is no longer developed.

**Shared tools:** 

[Shards](shards.html)  
The purpose of Shards is to provide a suite of common tools for numerical and topological data that facilitate interoperability between typical software modules used to solve Partial Differential Equations (PDEs) by finite element, finite volume and finite difference methods. Shards comprises of two categories of tools: methods to manage and access information about cell topologies used in mesh-based methods for PDEs, and methods to work with multi-dimensional arrays used to store numerical data in corresponding computer codes. The basic cell topology functionality of Shards includes methods to query adjacencies of subcells, find subcell permutation with respect to a global cell and create user-defined custom cell topologies. Multi-dimensional array part of the package provides specialized compile-time dimension tags, multi-index access methods, rank and dimension queries.

[Percept](percept.html)  
The package is a collection of tools to enable solution verification. The main emphasis is on spatial mesh modification, including capabilities for uniform and local mesh adaptation. Additionally, we provide separate tools for transfer of field data, verification of modal eigenvalue problems, and scripts for solution verification studies. Advanced capabilities for refinement include support for conformal meshes using transition element elements, conversion to all-tet meshes, enrichment to higher order elements, and special boundary layer refinement on hybrid tet/wedge meshes. The most commonly used capability is uniform mesh refinement (UMR).
