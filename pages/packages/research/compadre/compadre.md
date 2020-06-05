---
title: Compadre
permalink: compadre.html
folder: research
show_sidebar: true
contact: pakuber@sandia.gov
package: compadre
doxygen: false
---
The Compadre Toolkit provides tools for the approximation of linear operators applied to a function (including point evaluation and derivatives), given samples of the function over a cloud of points. The toolkit can be used for data transfer applications as well as for meshless discretization of PDEs. Compadre currently uses Generalized Moving Least Squares (GMLS) for approximating functionals and we plan on implementing other meshless methods like radial basis functions. 

This toolkit focuses on the 'on-node' aspects of meshless PDE discretizationo and remap, namely the parallel assembly and solution of  of local system for computing the basis coefficients. What it does **not** provide is the tools for managing fields, inverting globally sparse matrices, or neighbor search that requires orchestration over many MPI processes. This toolkit is designed to be easily dropped-in to an existing MPI (or serial) based framework for PDE solution or remap, with minimal dependencies, [Kokkos](kokkos.html) and [KokkosKernels](kokkoskernels.html).

The Compadre homepage is at [https://github.com/SNLComputation/compadre/wiki](https://github.com/SNLComputation/compadre/wiki).

[Documentation](https://github.com/SNLComputation/compadre/wiki/Documentation)

[Citing Compadre](https://github.com/SNLComputation/compadre/wiki/Citation)

[Team](https://github.com/SNLComputation/compadre/wiki/Team)

[Building instructions](https://github.com/SNLComputation/compadre/wiki/Building-in-Trilinos)
