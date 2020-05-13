---
title: Didasko Getting Started
permalink: didasko_getting_started.html
folder: archive
---

**What are the prerequisites for Didasko?**

The only prerequisites assumed in this tutorial are some familiarities with numerical methods for PDEs, and with iterative linear and nonlinear solvers. Although not strictly necessary, the reader is assumed to have some familiarity with distributed memory computing and, to a lesser extent, with MPI. Although almost no explicit MPI instructions are required in a Trilinos code, the reader should be aware of the basic concepts of message passing, like the definition of a communicator.

**What is the difference between Didasko’s examples and each Trilinos package’s examples?**

Didasko is not a substitute for individual packages’ documentation. Ideally, you’d like to use Didasko to start with Trilinos, get familiar with its basic capabilities, and understand what each package can offer you. Once you have clear in mind what part of Trilinos is needed, you should check the documentation of the specific packages you are planning to use.  
Clearly, a full understanding all the functionalities of the Trilinos packages requires time. Each package offers sophisticated features, difficult to “unleash” at a first sight. Besides that, a detailed description of each Trilinos package is beyond the scope of this document. For these reasons, the goal of this tutorial is to ensure that users have the background to make good use of the extensive documentation contained in each package. The [Trilinos documentation page](documentation.html) contains several other documents that should be consulted as well, including an overview of the Trilinos project, a guide for developers, and much more.

**Can I use Didasko without Epetra?**

No. Epetra is the “common language” or Trilinos, and almost all Didasko examples use Epetra.
