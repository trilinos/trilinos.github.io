---
title: Adelus
permalink: adelus.html
folder: packages
show_sidebar: true
contact: vqdang@sandia.gov
package: adelus
doxygen: false
---

Welcome to the Adelus Home

Adelus performs LU factorization with partial pivoting and solves
for a dense (real or complex) linear equation system on a distributed
computing system using MPI for message passing. It can be considered
a replacement for Pliris, which runs only on CPUs. Adelus uses
Kokkos and Kokkos Kernels to achieve performance portability on
heterogeneous architectures equipped with CPUs and accelerated
hardware such as GPUs.

The matrix is blocked mapped onto MPI processes (either on host
memory or device memory). It is factored and solved as if it was
torus-wrapped for an optimal balance of computation and communication.
A permutation operation is performed on the results to restore the
results to their correct position so the torus-wrap distribution
is hidden to the user. Each process contains blocks of the matrix
and the right hand sides. A distribution function is used to optimally
load balance the computation and communication during the LU
factorization of the matrix. Each process handles its own workload
through the Kokkos Kernels BLAS routines optimized for multi-threaded
CPUs and massively parallel GPUs. GPU-aware MPI can be used on GPU
architectures to allows direct communication among GPU buffers.

Adelus provides three interfaces, FactorSolve (factors and solves
a dense system in which matrix and RHS are packed in Kokkos View),
Factor (factors a dense matrix for later solve), and Solve (solves
a previously factored dense matrix for provided RHS). Adelus supports
solving for multiple RHS vectors. Adelus allows applications to
concurrently launch multiple solvers each of which is associated
with a MPI sub-communicator of the MPI_COMM_WORLD.
