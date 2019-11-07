---
title: ShyLU
permalink: shylu.html
folder: packages
show_sidebar: true
contact: shylu-developers@software.sandia.gov
package: shards
---

## Welcome to the ShyLU Home

ShyLU is a package for solving sparse linear systems using domain decomposition methods. ShyLU has two main focus areas - 
(1) distributed memory domain-decomposition solvers and (2) node-level solvers and kernels that support the distributed memory solvers. The approaches in ShyLU are algebraic and so can be used as a black-box solvers.

The node level solvers include sparse LU factorization (basker), sparse Cholesky factorization (Tacho), multithreaded triangular solver (HTS) and a fast iterative ILU algorithm (FastILU).

## Domain Decomposition Solvers

The Domain Decomposition methods in ShyLU are a one-level hybrid direct/iterative approach based on Schur complements, two-level balancing domain decomposition method (bddc) and Overlapping Schwarz methods (FROSch). 

The one-level hybrid direct/iterative approach based on Schur complements was developed to provide robustness similar to sparse direct solvers with less memory use. This has been particulary effective for circuit simulation problems.

FROSch can be used for both one-level overlapping Schwarz and two-level Generalized Dryja Smith Widlund preconditioner. FROSch has been shown to be effectve in several applications including land-ice simulations.

BDDC is an experimental code for the solver that implements the Balancing Domain Decomposition solver.

## Node Level Direct Solvers

Basker is a shared-memory parallel LU factorization based direct solver that uses the BTF ordering.

Tacho is a shared-memory parallel Cholesky factorization based direct solver that uses Kokkos based tasking.

HTS is a sparse triangular solver that uses OpenMP for triangular solves on the host.

FastILU is an iterative ILU and traingular solve implementaion using Kokkos.


