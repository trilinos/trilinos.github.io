---
title: Some of What’s New in Trilinos - Sacado, phdMesh, Intrepid, FEI
permalink: trilinos_user_group_2007_abstracts_tuesday_1h15.html
folder: community
---

    Phipps / Edwards / Ridzal / Williams  
    Tuesday, November 6th  
    1:15 - 2:15 pm  

## Sacado: Differentiation Tools for C++ Codes

Sacado is a new Trilinos package providing automatic differentiation tools for C++ codes. I will provide a quick overview of the tools in Sacado, briefly describe how to use these tools, and show some of the impacts these tools have already had in ASC simulation efforts.

## phdMesh:

The new 'phdMesh' Trilinos package supports parallel, heterogeneous, and dynamic unstructured meshes (phdMesh). It was developed under the "HPC Application Performance Analysis and Prediction" LDRD as part of a mini-application that performs parallel geometric proximity search and dynamic load balancing. A decade of experience with a variety of finite element / finite volume applications and frameworks has led to the concise concepts, object oriented design, and minimalistic application programmer interface (API) of phdMesh. In a dramatic departure from traditional mesh data structure phdMesh is completely devoid of predefined element types or topologies. As such it must be paired with an element package (e.g. Intrepid) to fulfill the traditional expectations for a mesh data structure.

## Intrepid:

Intrepid is a new Trilinos package that provides a set of interoperable tools for the rapid development of compatible spatial discretizations. At the core of Intrepid is a component for the generation of local (cell-based) discrete differential operators / fields. The innovative design allows access to finite element, finite volume, and finite difference methods using a common API, and enables hybrid discretizations on unstructured grids. Intrepid supports low- and high-order finite element reconstructions on standard cell shapes and low-order mimetic methods on arbitrary polyhedral cells. A layer of global components provides interfaces to mesh management, linear system assembly, and degree-of-freedom matching.

## FEI:

FEI (Finite Element Interface to linear solvers) is a library for assembling sparse linear systems arising from finite-element applications. This talk will give a brief introduction to the ideas behind the FEI library. FEI assists with mapping finite-element data to linear algebra data. On the finite-element side, it is natural to think in terms of node-ids, element-ids, and solution-fields (e.g. displacement vectors, temperature scalars). On the linear-algebra side, these are mapped to row-numbers, column-indices for assembling coefficients into matrices and vectors. FEI also assists with parallel communication when assembling a system in parallel, and acts as an abstraction layer.