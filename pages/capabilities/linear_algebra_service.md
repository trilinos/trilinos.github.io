---
title: Linear Algebra Service
permalink: linear_algebra.html
folder: capabilities
---

## Linear algebra objects and services

Trilinos implements _linear algebra objects_. These objects include sparse graphs, sparse matrices, and dense vectors. You may create and modify these objects, use them in computations (for example, sparse matrix-vector multiplies or dot products), or give them to Trilinos’ solvers. You may also wrap your own linear algebra implementations or functions and give them to Trilinos’ solvers. We call all of these features together _linear algebra services._

## Parallelism

All of these linear algebra objects can use MPI (the Message-Passing Interface) for distributed-memory parallel computation, though we do not _require_ MPI. Some of them can combine this MPI capability with shared-memory parallelism, using OpenMP, Pthreads, or CUDA. Trilinos has a unique general-purpose parallel data redistribution facility, inspired originally by Zoltan, that you can use for your own applications. Trilinos’ linear algebra is known to scale to hundreds of thousands of parallel processes, but it is also meant to run well on a workstation or laptop. Users have even run it on a cell phone!

## Trilinos packages

Trilinos has two packages that implement scalable linear algebra: **Epetra** and **Tpetra**. (These are pronounced “EE-pe-tra” resp. “TEE-pe-tra.” E stands for “essential,” and T for “templated,” in the C++ sense of “template.”) There are two packages because Tpetra required C++ language capabilities that were not supported in all compilers around the year 2000\. Here is a comparison of their features:

*   **Parallelism**: Epetra supports MPI parallelism, with very limited use of OpenMP for some sparse matrix and dense vector kernels. Tpetra has more general “MPI+X” support, where X is any of various shared-memory parallel programming models. These include OpenMP, Pthreads (POSIX Threads), and CUDA. Tpetra implements this in a performance-portable way using the Kokkos shared-memory parallel programming model.
*   **Large problems**: Both Epetra and Tpetra have support for 64-bit global indices, which let users solve problems with over two billion entities (e.g., rows, columns, or matrix entries). Tpetra’s support for 64-bit global indices is more mature. Tpetra also has optional support for 64-bit _local_ indices, which allows that many entities within a single MPI process.
*   **Data types**: Epetra only allows real double-precision floating-point values in its matrices and vectors. Tpetra lets users fill matrices and vectors with data of other types as well, including single-precision real, complex, extended precision, and types for advanced analysis (e.g., automatic differentiation or polynomial chaos expansions for solving stochastic partial differential equations). You may create objects with different data types at run time, and perform mixed-precision computations.

Epetra and Tpetra linear algebra objects form the foundation of an entire “stack” of linear and nonlinear solvers in Trilinos. Almost every Trilinos package depends on one of these two packages. Epetra has been in use longer and has more users. However, its interface is frozen, and no new features will be added unless there is a very good reason. Tpetra is where all development work has been concentrating for at least three years, and where future development will concentrate.

Trilinos implements some linear algebra capabilities in other packages as well:

*   **Teuchos** (pronounced “TEF-hos”) wraps the standard BLAS and LAPACK libraries, and provides an abstraction over MPI communicators and some MPI operations.
*   **Kokkos** (pronounced “KO-kos”) implements a unified shared-memory parallel programming model, and also includes computational kernels for use in Tpetra and other packages.
*   **Thyra** (pronounced “THEE-ruh,” with TH as in “theta”) provides a generic interface to linear operators (e.g., matrices and preconditioners) and vectors. It can wrap Epetra or Tpetra objects. Thyra is particularly useful for constructing block vectors, matrices, and preconditioners, for example when solving saddle-point problems. Users most often encounter Thyra when using the Stratimikos package to create and use linear solvers and preconditioners.
*   **Xpetra** (pronounced “X-pe-tra”) wraps Epetra and Tpetra, and lets users switch between the two implementations at run time. It was designed for the algebraic multigrid package MueLu, but has been adopted by other packages, like Zoltan2.

## How do I get started?

You can get started by looking at [the Tpetra documentation.](https://trilinos.org/docs/dev/packages/tpetra/doc/html/index.html) This page gives an overview of Tpetra, and links to the Tpetra tutorial. We particularly recommend the Tpetra tutorial as a way to get started creating sparse matrices and dense vectors.