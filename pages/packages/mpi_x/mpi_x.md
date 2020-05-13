---
title: MPI+X Packages
permalink: mpi_x.html
folder: mpi_x
---

MPI+X packages within Trilinos are under very active development in support of today's systems based on highly-concurrent node architectures and in preparation  for upcoming Exascale systems and beyond.  Trilinos MPI+X packages are robust, production software used in the growing set of next-generation applications.  In addition to targeting next generation vectorizing manycore CPUs (e.g., Arm SVE) and accelerators (GPUs) from Nvidia, AMD and Intel, Trilinos MPI+X packages provide:
- **Performance portability:** Using the [Kokkos and KokkosKernels](https://github.com/kokkos) libraries that are available independently from Trilinos but also snapshotted into Trilinos.  Kokkos was originally part of Trilinos, then split out to be independently available to users who want performance portability without solvers.
- **Polymorphic scalar data types:** Tpetra (and Kokkos) data objects support any legal data type for vectors and matrices, including low-precision types found on accelerators, or extended precision such as double-double and quad precision.
- **2D sparse graph and matrix decompositions:** Useful for data science applications such as scale-free graphs.

The MPI+X collection of packages is sometime referred to as the <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.epetra_stack}}">Tpetra</a> stack. Tpetra is a refresh of the original<a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.tpetra_stack}}">Epetra</a> stack.  [Epetra and its related packages](mpi.html) were the original collection of production Trilinos capabilities.  Tpetra and the packages built on top of it provide the next generation of scalable solvers in Trilinos.
