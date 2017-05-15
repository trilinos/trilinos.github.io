---
title: Parallel Programming Environments
permalink: parralel_programming.html
folder: capabilities
---

From the very beginning of the Trilinos project, we have used lightweight abstract interfaces to access parallel computing machine information and services. The first interface was the Epetra_Comm layer, which had two basic concrete adapters, Epetra_SerialComm and Epetra_MpiComm. By writing Trilinos software on top of Epetra_Comm, the code was portable in both serial and distributed memory environments. Furthermore, nesting of the comm interfaces permitted additional flexibility.

Tpetra has a similar comm API, but it is present in the Teuchos package so that it is more widely available to users who don’t need Tpetra.

Presently, the advent of diverse multicore, manycore and accelerator processors, makes the abstraction of parallel machine details both more challenging and more important. Trilinos has a new package, Kokkos, that provides _compile time_ polymorphism via template metaprogramming techniques. Kokkos provides multidimensional array containers, and a set of execution patterns that can operate on these array containers to perform parallel_for, parallel_reduce and parallel_scan. Current work focuses on support for asynchronous task parallelism.

The Parallel Programming Environments capability area is concerned with cross-project capability in performance portability across scalable multicore, manycore, and accelerator-based systems.