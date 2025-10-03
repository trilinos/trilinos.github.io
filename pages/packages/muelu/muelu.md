---
title: MueLu
permalink: muelu.html
folder: packages
show_sidebar: true
contact: <a href="mailto:jhu@sandia.gov">Jonathan Hu</a> (<a href="https://github.com/jhux2">@jhux2</a>), <a href="https://github.com/orgs/trilinos/teams/muelu">@muelu</a>
package: muelu
doxygen: true
---

![logo_Blue](images/logo_Blue1.png)

**Welcome to MueLu, the Trilinos multigrid framework!**

MueLu is designed to solve large sparse linear systems of equations arising from PDE discretizations. MueLu provides easy-to-use multigrid solvers and preconditioners based on smoothed aggregation algorithms. As a multigrid framework, MueLu supports the design of highly application specific multigrid preconditioners. MueLu has been used for pressure solves within a low Mach thermal fluids simulation on 524K cores of a BlueGene/Q machine, and for solving a fully-coupled MHD problem on 524K BlueGene/Q cores.

### <span style="text-decoration: underline;">Overview</span>

MueLu is a flexible, high-performance multigrid solver library. It provides a variety of multigrid algorithms for these problem classes:

*   Poisson
*   Elasticity
*   convection-diffusion
*   Maxwell’s equations (eddy current formulation)

MueLu is extensible and allows for the research and development of new multigrid preconditioning methods.

### <span style="text-decoration: underline;">Features</span>

*   **Easy-to-use interface:** MueLu has a user-friendly parameter input deck which covers most important use cases, with reasonable defaults provided for common problem types.
*   **Modern object-oriented software architecture:** MueLu is written completely in C++ as a modular object-oriented multigrid framework, which provides flexibility to combine and reuse existing components to develop novel multigrid methods.
*   **Extensibility:** Due to its flexible design, MueLu is an excellent toolkit for research on novel multigrid concepts. Experienced multigrid users have full access to the underlying framework through an advanced XML based interface. Expert users may use and extend the C++ API directly.
*   **Integration with Trilinos:** As a package of Trilinos, Muelu is well integrated into the Trilinos environment and can use either of the two main solver stacks:
    *   Epetra (32-bit) sparse linear algebra: AztecOO (Krylov solvers), Ifpack (algebraic smoothers), Amesos (sparse direct solvers), Zoltan (load rebalancing)
    *   Tpetra sparse linear algebra: Belos (Krylov solvers), Ifpack2( algebraic solvers), Amesos2 (sparse direct solvers), Zoltan2 (load rebalancing).
*   **Broad range of supported platforms:** MueLu runs on wide variety of architectures, from desktop workstations to parallel Linux clusters and supercomputers.
*   **Open source:** MueLu is freely available through a [simplified BSD license](docs/dev//muelu/index.html#muelu_copyright).

If you are interested in using MueLu for your research or want to contribute, please contact any of the [MueLu developers](muelu_team.html "MueLu Team").

### <span style="text-decoration: underline;">Helpful Links</span>

*   MueLu is governed by a [simplified BSD license](docs/dev//muelu/index.html#muelu_copyright).
*   [Documentation](muelu_documentation.html "Documentation") (User’s Guide, [Tutorial](muelu_tutorial.html), [Doxygen](docs/dev//muelu/index.html "MueLu Doxygen"))
*   The [MueLu development team](muelu_team.html "MueLu Team").
*   [How to contact](muelu_contact.html "MueLu Documentation") the MueLu team.
*   [How to cite MueLu](muelu_citation.html "MueLu citation").
*   [Summary of MueLu testing dashboard](http://testing.sandia.gov/cdash/index.php?project=Trilinos&subproject=MueLu)
