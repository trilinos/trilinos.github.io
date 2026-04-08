---
title: Documentation
permalink: documentation.html
show_sidebar: true
sidebar: nav
keywords: Trilinos documentation, Getting started with Trilinos, High-performance computing (HPC), Installation guide, CMake configuration, Parallel computing, Modular architecture, Trilinos packages, Optimization solvers, Uncertainty quantification, Computational simulations, Integration with Python, Community support, Tutorials, Videos, Reference material, Developer resources, Trilinos GitHub repository, Trilinos capabilities, Trilinos license, BSD 3-Clause License, LGPL License, NTESS copyright statement, Open-source software, TriBITS users guide, Third-party libraries, Trilinos build instructions, Example projects, Smart pointers, Teuchos::RefCountPtr, Scalability, Interoperability, Developer contributions, GitHub issues, GitHub pull requests, Scientific computing framework
---

Find out more about Trilinos: how to use it, install it, configure it, and even cite it.

---

## General Information

- [Trilinos: Enabling Scientific Computing Across Diverse Hardware Architectures at Scale](https://dl.acm.org/doi/10.1145/3802822)
    - An overview of the Trilinos framework, highlighting its design principles, modular architecture, and scalability for scientific computing on modern hardware platforms.
    - ACM Transactions on Mathematical Software, accepted.
- [An Overview of the Trilinos Project](pdfs/TrilinosACMTOMS2004.pdf) 
    - ACM Transactions on Mathematical Software, Vol. 31, Issue 3, September 2005, Pages 397-423.
- [An Overview of Trilinos](pdfs/TrilinosOverview.pdf)
    - A broad overview of Trilinos from 2003.
    - Heroux, M., Bartlett, R., Howle, V., Hoekstra, R., Hu, J., Kolda, T., Lehoucq, R., Long, K., Pawlowski, R., Phipps, E., Salinger, A., Thornquist, H., Tuminaro, R., Willenbring, J., & Williams, A. (2003, August). *An Overview of Trilinos* (SAND2003-2927). Sandia National Laboratories, Albuquerque, NM. Unlimited Release. Approved for public release; further dissemination unlimited.

---

## Configure, Build, and Install

- [Quick Configure, Build, and Install Hints](https://github.com/trilinos/Trilinos/blob/master/INSTALL.rst)
    - Basic instructions for setting up Trilinos.
- [Trilinos Configure, Build, Test, and Install Reference Guide](pdfs/TrilinosBuildReference.pdf)
    - Instructions for building Trilinos 10.0 and later.
    - [Partial version](https://github.com/trilinos/Trilinos/blob/master/doc/build_ref/TrilinosBuildReferenceTemplate.rst)
- [Simple Example of Building Against Installed Trilinos with CMake](https://github.com/trilinos/Trilinos/tree/master/demos/simpleBuildAgainstTrilinos)
    - A functional example for applications using `find_package(Trilinos)`.
- [TriBITS Users Guide and Reference](https://tribitspub.github.io/TriBITS/users_guide/index.html)
    - Developer guide for TriBITS, covering topics like adding new packages or third-party libraries.
- [Third-Party Libraries](pdfs/third_party_libraries.txt)
    - Overview of libraries commonly used with Trilinos.
- [find_package(Trilinos) Documentation](pdfs/Finding_Trilinos.txt)
    - Instructions for building CMake-aware projects compatible with Trilinos.

---

## Citing Trilinos

If you are using Trilinos, please cite us in your publications:

**Mayr, M., et al. (2026). Trilinos: Enabling Scientific Computing Across Diverse Hardware Architectures at Scale. ACM Transactions on Mathematical Software. https://doi.org/10.1145/3802822**

```bibtex
@article{10.1145/3802822,
  author    = {Mayr, Matthias and Heinlein, Alexander and Glusa, Christian and Rajamanickam, Sivasankaran and Arnst, Maarten and Bartlett, Roscoe A. and Berger-Vergiat, Luc and Boman, Erik G. and Devine, Karen and Harper, Graham and Heroux, Michael and Hoemmen, Mark and Hu, Jonathan and Kelley, Brian and Kim, Kyungjoo and Kouri, Drew P. and Kuberry, Paul and Liegeois, Kim and Ober, Curtis C. and Pawlowski, Roger and Pearson, Carl and Perego, Mauro and Phipps, Eric and Ridzal, Denis and Roberts, Nathan V. and Siefert, Christopher M. and Thornquist, Heidi K. and Tomasetti, Romin and Trott, Christian R. and Tuminaro, Raymond S. and Willenbring, James M. and Wolf, Michael M. and Yamazaki, Ichitaro},
  title     = {Trilinos: Enabling Scientific Computing Across Diverse Hardware Architectures at Scale},
  year      = {2026},
  publisher = {Association for Computing Machinery},
  address   = {New York, NY, USA},
  issn      = {0098-3500},
  url       = {https://doi.org/10.1145/3802822},
  doi       = {10.1145/3802822},
  abstract  = {Trilinos is a community-developed, open-source software framework that facilitates building large-scale, complex, multiscale, multiphysics simulation code bases for scientific and engineering problems. Since the Trilinos framework has undergone substantial changes to support new applications and new hardware architectures, this document is an update to “An Overview of the Trilinos project” by Heroux et al. (ACM Transactions on Mathematical Software, 31(3):397–423, 2005). It describes the design of Trilinos, introduces its new organization in product areas, and highlights established and new features available in Trilinos. Particular focus is put on the modernized software stack based on the Kokkos ecosystem to deliver performance portability across heterogeneous hardware architectures. This paper also outlines the organization of the Trilinos community and the contribution model to help onboard interested users and contributors.},
  journal   = {ACM Transactions on Mathematical Software},
  month     = March,
  keywords  = {Heterogeneous Hardware Architectures, High-Performance Computing, Performance Portability, Scientific Software Frameworks}
  }
```

Below is a BibTeX entry for the Trilinos GitHub repository:

```bibtex
@Manual{trilinos,
  title        = {The {T}rilinos {P}roject},
  author       = {The Trilinos Project Team},
  organization = {Linux Foundation / High Performance Software Foundation},
  year         = {2026},
  url          = {https://trilinos.github.io},
  note         = {Accessed: January 8, 2026},
}
```

---

## Tutorials and Videos

- [Trilinos Hands-on Tutorial](https://github.com/trilinos/Trilinos_tutorial/wiki/TrilinosHandsOnTutorial)
    - Introductory material and examples used in live tutorials.
- [Trilinos Official YouTube Channel](https://www.youtube.com/channel/UCXUzjWRBdpPVBbJn8vFRc7w)
    - Recorded talks and tutorials ranging from beginner to expert level.

---

## Developer Information

- [Trilinos Developers Site](https://github.com/trilinos/Trilinos/wiki)
    - Additional information focused towards Trilinos developers and contributors.
- [Teuchos::RCP Beginner’s Guide](https://www.osti.gov/servlets/purl/919177)
    - Introduction to Trilinos' smart reference-counted pointer class for dynamic memory management in C++.
    - Bartlett, Roscoe. _Teuchos::RCP Beginner’s Guide (An Introduction to the Trilinos Smart Reference-Counted Pointer Class for (Almost) Automatic Dynamic Memory Management in C++)_. SAND2004-3268, Sandia National Laboratories, 2007 (Updated December 2007) [[PDF](https://bartlettroscoe.github.io/publications/RefCountPtrBeginnersGuideSAND.pdf)]
- [Teuchos C++ Memory Management Classes, Idioms, and Related Topics](https://bartlettroscoe.github.io/publications/TeuchosMemoryManagementSAND.pdf)
    - Bartlett, Roscoe. _Teuchos C++ Memory Management Classes, Idioms, and Related Topics: The Complete Reference (A Comprehensive Strategy for Safe and Efficient Memory Management in C++ for High Performance Computing)._ SAND2010-2234, Sandia National Laboratories. May 2010.
- [Teuchos::RCP: An Introduction](https://bartlettroscoe.github.io/publications/rabartl_TUG_RCP_Talk.pdf)
    - Bartlett, Roscoe. _Teuchos::RCP: An Introduction to the Trilinos Smart Reference-Counted Pointer Class for (Almost) Automatic Dynamic Memory Management in C++._ SAND2005-4855P, Sandia National Laboratories, 2005 (Updated February 2008) [[PPT](https://bartlettroscoe.github.io/publications/rabartl_TUG_RCP_Talk.ppt), [PDF](https://bartlettroscoe.github.io/publications/rabartl_TUG_RCP_Talk.pdf)]
- [Teuchos Memory Management](pdfs/TUG2007_Teuchos_MemoryManagement.pdf)
    - Bartlett, Roscoe. _New Teuchos Utility Classes for Safer Memory Management in C++._ SAND2007-7237C, 2007 Trilinos User~s Group Meeting, Sandia National Laboratories, November 2007 [[PPT](https://bartlettroscoe.github.io/publications/TUG2007_Teuchos_MemoryManagement.ppt), [PDF](https://bartlettroscoe.github.io/publications/TUG2007_Teuchos_MemoryManagement.pdf)]
- Additional documentation, tutorials and examples are available through the [individual capabilities](capabilities.html).

---

## Other Trilinos Repositories

Beyond the [main Trilinos repository](https://github.com/trilinos/Trilinos), the Trilinos organization hosts additional [repositories](https://github.com/orgs/trilinos/repositories) that provide extra capabilities and archived packages.


