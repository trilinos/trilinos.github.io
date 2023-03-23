---
title: MiniTensor
permalink: minitensor.html
folder: mpi_x
show_sidebar: true
contact: amota@sandia.gov
package: minitensor
doxygen: true
---

MiniTensor is a library for the use, manipulation, algebra and optimization of small vectors and tensors and problems that depend on them. It was first conceived and developed for the implementation of complex material models in Albany. Its purpose is to provide a compact representation of vector and tensor expressions. Its emphasis is on ease of use, and accurate algorithms, specifically those used for the development of constitutive models in finite deformation solid mechanics. It is smaller, but more focused than Blitz++, TVMet or Eigen. It is used in both research (Albany/LCM) and production (Sierra/SM) environments.

Features:

*    Vectors, second-order to fourth-order tensors.
*    Static (for production) and dynamic (for research) storage.
*    Basic manipulation, linear algebra, geometry and mechanics.
*    Unconstrained (native, ROL) and constrained (ROL) optimization.
*    Solution of nonlinear systems of equations.
*    Emphasis in accurate algorithms.
*    Fully templated, plays well with Sacado.
