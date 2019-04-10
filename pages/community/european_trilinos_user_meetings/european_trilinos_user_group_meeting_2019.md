---
title: European Trilinos User Group Meeting 2019
permalink: european_trilinos_user_group_meeting_2019.html
folder: community
---

**European Trilinos User Group Meeting 2019**  
**June 11, 2019**  
**Location:**
Eidgenössische Technische Hochschule Zürich (ETH Zürich)
Zürich, Switzerland

Co-sponsored by the [Swiss National Supercomputing Centre (CSCS)](https://www.cscs.ch)

The Trilinos Project team will be holding a one-day European Trilinos User Group meeting on June 11, 2019 at ETH Zürich, Switzerland.  The meeting will occur the day before the 2019 Platform for Advanced Scientific Computing Conference [PASC 2019](https://pasc19.pasc-conference.org) also held at ETH from June 12 – 14.

### Registration
- In preparation.

### Meeting Themes
- Overview of Trilinos capabilities for next-generation parallel computers.
- Use of Kokkos for efficient on-node parallel problem construction.
- Capabilities in KokkosKernels for parallel on-node mathematical kernels.
- Tools for the discretization and solution of differential equations.
- US solver efforts for Exascale platforms.

### Agenda (Select Arrow for Abstract)

#### Monday, June 10

<details>
<summary>
1900  - Informal Dinner near ETH - Contact Mike Heroux [maherou@sandia.gov](mailto:maherou@sandia.gov) if you want to join for dinner
</summary>
    Location - TBD
</details>


#### Tuesday, June 11

<details>
<summary>
0800 - Meeting Introduction and Overview - Mike Heroux, Sandia National Laboratories
</summary>
    Trilinos is a large collection of scientific libraries for high performance computing, encompassing a variety of solvers and problem construction capabilities for current and emerging platforms.  In this one-day meeting, we will provide an overview and update of Trilinos for people interested in developing capabilities for next-generation computing platforms, including GPUs, manycore and vector processors.  This first presentation will provide a brief overview of the day and also discuss the broader context of US Exascale efforts related to scientific libraries.
</details>

<details>
<summary>
0830 - Using Trilinos from Container and Interactive Environments - Tobias Wiesner
</summary>
    In this presentation, we describe Docker and Jupyter environments that support portable and interactive use of Trilinos.
</details>

<details>
<summary>
0915 - Introduction to Kokkos - Christian Trott, Sandia National Laboratories
</summary>
    Kokkos provides the node-parallel performance portability layer for Trilinos and applications.  In this presentation, we provide a brief introduction, a description of the Kokkos design and instructions for how to use Kokkos to obtain efficient portable performance on CPUs, GPUs and manycore processors.
</details>

<details>
<summary>
1030 - Break
</summary>
    Coffee, tea and small refreshments are available at the break.
</details>
<details>
<summary>
1100 - Solving Linear Systems using Trilinos and KokkosKernels - Siva Rajamanickam, Sandia National Laboratories
</summary>
Trilinos provides a rich collection of linear solver capabilities in a variety of packages.  In addition, KokkosKernels provides node-parallel solver components that can be used in combination with other Trilinos capabilities or independently.  In this presentation, we give an overview of the new capabilities that are focused on effective use of emerging scalable systems with parallel nodes.
</details>
<details>
<summary>
1200 - Lunch
</summary>
    Lunch is provided on site at the meeting as part of the registration fee.
</details>

<details>
<summary>
1315 - Fast and Robust Overlapping Schwarz: FROSch - Alexander Heinlein, University of Cologne
</summary>
    <a href="https://shylu-frosch.github.io">FROSch</a> is a Trilinos-compatible software library for parallel overlapping Schwarz preconditioning.  This presentation provides an overview of FROSch and how to use it to robustly solve large sparse linear systems.
</details>

<details>
<summary>
1400 - Using Trilinos/Muelu for Scalable Multigrid Preconditioning - Matthias Mayr, University of the Bundeswehr Munich
</summary>
    Muelu is the next-generation Trilinos algebraic multigrid preconditioner.  In this presentation we show how to effectively use Muelu for large sparse linear systems.
</details>

<details>
<summary>
1445 - Break
</summary>
        Coffee, tea and small refreshments are available at the break.
</details>

<details>
<summary>
    1515 - Discretization and Assembly using Intrepid2 and Tpetra, Mauro Perego, Sandia National Laboratories
</summary>
  Intrepid2 is a performance portable C++ toolkit for the local assembly of high-order compatible finite elements. Performance portability is achieved through the Kokkos programming model. In this talk we introduce Intrepid2 and its capabilities. We then demonstrate how to discretize partial differential equations and assemble the associated finite element matrices and right-hand sides using the Trilinos linear algebra package Tpetra. Finally, we give a brief overview of other discretization tools available in Trilinos.
</details>
<details>
<summary>
1630 - The ECP Extreme-scale Scientific Software Development Kit (xSDK) - Keita Teranishi, Sandia National Laboratories
</summary>
    The <a href="https://xsdk.info">xSDK</a> is a community effort to provide coordination and improved common experience with a growing collection of popular math libraries, including hypre, PETSc, SuperLU, Trilinos and more.  In this presentation, we give an overview of the xSDK and how it can be useful to math libraries users.
</details>

<details>
<summary>
1700 - Open Discussion
</summary>
    The remainder of the meeting will be used to conduct a guided discussion with attendees.
</details>
