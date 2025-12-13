---
title: Intrepid2
permalink: intrepid2.html
folder: packages
show_sidebar: true
contact: <a href="mailto:mperego@sandia.gov">Mauro Perego</a> (<a href="https://github.com/mperego">@mperego</a>), <a href="https://github.com/orgs/trilinos/teams/intrepid2">@intrepid2</a>
package: intrepid2
doxygen: true
---


Intrepid2 provides interoperable tools for compatible discretizations of PDEs. Intrepid2 mainly focus on local assembly of continuous and discontinuous finite elements, and provides tools for finite volume discretizations as well. The present version of Intrepid2 implements compatible finite element spaces of orders up to 10 for *H(grad)*, *H(curl)*, *H(div)* and *L2* function spaces on frequently used elements such as triangles, quadrilaterals, tetrahedrons and hexahedrons. It provides both Lagrangian basis functions and Hierarchical basis functions (currently only for tensor-product topologies). For each space Intrepid2 provides generation of the relevant discrete first and second order differential operators on a single cell. Intrepid2 provides orientation tools for matching the degrees of freedom on shared edges and faces. It also provides projection tools for projecting functions in *H(grad)*, *H(curl)*, *H(div)* and *L2* to the respective discrete spaces. Intrepid2 achieves performance portability using the Kokkos(kokkos.html) programming model. Virtually all numerical data required for local assembly can be represented as a multi-dimensional arrays, implemented as <code>Kokkos::DynamicRankViews</code>. 

Overview

*   High-order (up to 10) basis functions for _H(grad)_, _H(curl)_, _H(div)_ and _L2_ spaces on select cell topologies
*   Lagrangian and Hierarchical basis functions
*   Pullbacks (transformations) from reference coordinate frame of _H(grad)_, _H(curl)_, _H(div)_ and _L2_ fields
*   Pullbacks of gradient, curl and divergence of _H(grad)_, _H(curl)_, _H(div)_ fields
*   Quadrature rules of orders up to 20 on most standard 1D, 2D and 3D cell topologies
*   Orientation tools to enforce matching of degrees of freedom on shared edges and faces
*   Projection-based Interpolations operators on _H(grad)_, _H(curl)_, _H(div)_ and _L2_ that are optimally accurate and commute with the respective differential operators

Supplementary materials

Given that Intrepid2 largely maintains the mathematical structure of Intrepid, we refer to [Solving PDEs with Intrepid](https://content.iospress.com/articles/scientific-programming/spr340) by Bochev, Edwards, Kirby, Peterson, Ridzal.

Hierachical basis functions are implemented accordingly to the paper [Orientation embedded high order shape functions for the exact sequence elements of all shapes](https://www.sciencedirect.com/science/article/pii/S0898122115002084) by Fuentes, Keith, Demkowicz and Nagaraj. However, in Intrepid2 the orientations are not embedded in the basis but enforced separately for additional flexibility.

Interpolation-based projections are described in the book [Computing with Hp-Adaptive Finite Elements, Vol. 2](https://dl.acm.org/doi/book/10.5555/1564840) by Demkowicz, Kurtz, Pardo, Paszynski, Rachowicz, Zdunek.

Slides on recent Intrepid2 capabilities:
*   [Discretization and Assembly using Intrepid2 and Tpetra](https://www.osti.gov/servlets/purl/1640745)
*   [Exploiting Tensor-Product Structure in High-Order Finite Elements on Next-Generation Architectures](https://drive.google.com/file/d/1l_GOsrl618iMC4Pf839vIhRMBluU_5uE/view?usp=sharing)
