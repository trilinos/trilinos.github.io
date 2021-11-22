---
title: krino
permalink: krino.html
folder: mpi_x
show_sidebar: true
contact: drnoble@sandia.gov
package: krino
doxygen: false
---


Krino provides interoperable tools for computing and reinitialing signed distance fields and for creating unstructured stk meshes that conform to level set fields on a non-conforming background mesh.  Krino calculates signed distance fields from multiple analytic shapes, from a faceted description including STL files, and from an existing level set field. Both scalable Euclidean nearest point methods and fast marching methods are supported for signed distance calculations. 

Krino implements the conforming decomposition in the Conformal Decomposition Finite Element Method (CDFEM). In CDFEM interface conforming h-refinement is performed where nodes are added at the intersection between one to many level set interfaces and a a background mesh. In this way the background mesh is decomposed into elements that conform to the background mesh and to the level set interfaces on that mesh. Krino supports CDFEM for an arbitrary number of static and dynamic level set interfaces. Optionally krino can also support interface conforming r-refinement in which nodes of the background mesh are moved to nearby intersections between the mesh and the level set interfaces before performing the conformal decomposition.  This snapping procedure improves the quality of the resulting conformal mesh. 

All algorithms in krino support massively parallel computation on distributed memory machines using MPI.  Migration of these capabilities to MPI+X is underway.

Overview

*   Signed distance calculations for analytical shapes including spheres, cylinders, and planes
*   Signed distance calculations for faceted surfaces and mesh surfaces
*   Signed distance reinitialization using both Euclidean nearest point and Fast Marching methods
*   Euclidean nearest point signed distance for faceted surfaces is calculated using efficient algorithm with cost O(log(M)), where M is the number of facets
*   Interface conforming h-refinement for many level set surfaces
*   Optional interface conforming r-refinement prior to the h-refinement
*   Calculation of integrated quantities such as surface area and volume for level set volumes

Supplementary materials

[The Conforming Decomposition Finite Element Method](https://doi.org/10.1002/fld.2095)

[Signed distance calculation, application of CDFEM to many intersecting level sets](https://doi.org/10.1016/j.jcp.2018.08.022)
