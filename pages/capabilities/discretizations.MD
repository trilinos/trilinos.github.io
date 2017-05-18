---
title: Discretizations
permalink: discretizations.html
folder: capabilities
---

The discretization capability area was first introduced in Trilinos 9.0\. The objective is to provide, over time, a collection of libraries and interfaces that enable rapid development of application codes for applications that require numerical solution of Partial Differential Equations (PDE). The tools included in this capability area are designed to work with the rest of [Trilinos](http://trilinos.github.io/ "Trilinos Home Page") packages or to be used as interoperable components in existing user environments. The tools included in discretization capability area can be broadly divided into three related categories that correspond to the key steps in the numerical solution of PDEs by mesh-based methods.

<div class="row">
    <div class="col-sm-4">
        <img border="0" alt="Trilinos Team" src="images/Ninja_Hcurl_40_approx.jpg" width="30" height="30">
    </div>
    <div class="col-sm-4">
        <img border="0" alt="Trilinos Team" src="images/hcurl_approx_y.jpg" width="30" height="30">
    </div>
    <div class="col-sm-4">
        <img border="0" alt="Trilinos Team" src="hdiv_approx_x.jpg" width="30" height="30">
    </div>
</div>

* * *

*   **Global tools:**  
    Interfaces for assembling local (cell-wise) data into global representations of discrete differential operators by matrices. Global tools are used to generate discrete (algebraic) models of PDES on a given partition of the computational domain into cells (elements)

*   **Model building tools**  
    These tools manage discrete representations of physical fields entering the PDE model to enable computation of global operators such as residuals, Jacobians, or stiffness and mass matrices, corresponding to a given PDE model. Among other things, this capability enables users to quickly update and modify their physics kernels without significant code rewrite.

*   **Local tools**  
    Local tools provide the basic building blocks for numerical solution of PDEs by mesh-based methods such as reconstruction operators (bases) for finite element, finite volume and finite difference discretization methods on a single cell, as well as interfaces for fundamental vector calculus operators on cells.

*   **Shared tools**  
    These tools are intended to facilitate interoperability between software modules typically used in the numerical solution of PDEs.

* * *

**Brief summary of available tools.**

The discretization capability area of [Trilinos 10.0](http://trilinos.github.io/ "Trilinos Home Page") includes the following packages:

**Global tools:** [FEI](http://trilinos.org/packages/fei/)  
The Finite Element Interface to Linear Solvers (FEI) is a general interface for assembling finite-element data into a linear system of equations. It is an abstraction layer that insulates finite-element application codes from linear-algebra issues such as sparse matrix storage formats and mappings from nodes and solution fields to distributed equation spaces. It puts a common face on various linear solvers, allowing finite-element applications to switch from one solver library to another with minimal changes to application code. FEI provides natural mechanisms for assembling finite-element data such as element-wise stiffness arrays and load vectors, boundary-condition specifications and constraint relations. It accepts data from multi-physics problems, allowing arbitrarily complicated elements with multiple solution fields per node, and cell centered fields. It is designed for use in distributed-memory parallel finite-element applications, to assemble and solve distributed linear systems using scalable underlying solver libraries.

**Model building tools:** [Phalanx](http://trilinos.org/packages/phalanx/)  
Phalanx is a local field evaluation kernel specifically designed for general partial differential equation solvers. The main goal of Phalanx is to decompose a complex problem into a number of simpler problems with managed dependencies to support rapid development and extensibility of the PDE code. Through the use of template metaprogramming concepts, Phalanx supports arbitrary user defined data types and evaluation types. This allows for unprecedented flexibility for direct integration with user applications and provides extensive support for embedded technology such as automatic differentiation for sensitivity analysis and uncertainty quantification.

**Local tools:** [Intrepid](http://trilinos.org/packages/intrepid/)  
This package provides interoperable tools for compatible discretizations of PDEs. The API of Intrepid is designed to enable a standardized access to basic discretization approaches such as finite element, finite volume and finite difference methods on a wide range of cell topologies. The present version of Intrepid implements compatible finite element spaces of orders up to 10 for _H(grad)_, _H(curl)_, _H(div)_ and _L2_ function spaces on frequently used elements such as triangles, quadrilaterals, tetrahedrons and hexahedrons using Lagrangian and modal basis definitions. The former promotes simple visualization of various discrete fields by virtue of their degrees of freedom. For each space Intrepid provides generation of the relevant discrete first and second order differential operators on a single cell.

**Shared tools:** [Shards](http://trilinos.org/packages/shards/)

The purpose of Shards is to provide a suite of common tools for numerical and topological data that facilitate interoperability between typical software modules used to solve Partial Differential Equations (PDEs) by finite element, finite volume and finite difference methods. Shards comprises of two categories of tools: methods to manage and access information about cell topologies used in mesh-based methods for PDEs, and methods to work with multi-dimensional arrays used to store numerical data in corresponding computer codes. The basic cell topology functionality of Shards includes methods to query adjacencies of subcells, find subcell permutation with respect to a global cell and create user-defined custom cell topologies. Multi-dimensional array part of the package provides specialized compile-time dimension tags, multi-index access methods, rank and dimension queries.