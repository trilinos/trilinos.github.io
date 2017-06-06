---
title: ShyLU
permalink: shylu.html
folder: packages
---

## Welcome to the ShyLU Home

ShyLU stands for either “Scalable Hybrid LU” or “Sparse Hybrid LU”. It is also an Indian name.

ShyLU is a package for solving sparse linear systems. It can be used either as a preconditioner, or as a solver. Currently, we recommend using it as an Ifpack preconditioner.

ShyLU uses a hybrid direct/iterative approach based on Schur complements. The goal is to provide robustness similar to sparse direct solvers, but memory usage more similar to preconditioned iterative solvers.

ShyLU was designed as a node-level solver. It can use both MPI and threads in several ways. 
ShyLU was designed (a) to solve difficult but medium-size problems, and (b) to be used as a subdomain solver or smoother for very large problems within an iterative scheme. 
It is a purely algebraic method so can be used as a black-box solver. ShyLU has been particularly successful in electrical circuit simulation (Xyce).

ShyLU is highly configurable and supports a number of parameters to control how the Schur complement is approximated (dropping or probing) and how the inner-outer iteration works. These features are not yet documented.

ShyLU is currently experimental code. It works, but it is pretty rough. The examples is a good starting point. Interfaces may change in the future.