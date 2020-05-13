---
title: MPI-only Packages
permalink: mpi.html
folder: mpi
---

MPI-only packages within Trilinos are robust, production software used in hundreds of applications through the world.  Developed primarily in the early 2000s, these packages perform well in in distributed memory computing environments where MPI is used for parallelism on top of sequential microprocessors.  The Trilinos development team provides support for critical bug fixes but otherwise engages the user community for peer-level support.

The MPI-only collection of packages is sometime referred to as the <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.epetra_stack}}">Epetra</a> stack.  This collection can be relied upon for robust scalable MPI computation on CPU-only clusters at any scale.  At the same time, the High Performance Computing (HPC) community has shifted its focus to highly concurrent node architectures, requiring parallel execution underneath MPI.  In Trilinos, this [MPI+X](mpi_x.html) stack is sometimes called the <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.tpetra_stack}}">Tpetra</a> stack.
