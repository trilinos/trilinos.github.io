---
title: ML
permalink: ml.html
folder: archive
show_sidebar: true
contact: Ray Tuminaro (rstumin@sandia.gov), Chris Siefert (csiefer@sandia.gov), and Jonathan Hu (jhu@sandia.gov)
package: ml
doxygen: true
---

![ML](images/ml.jpg)

Welcome to the homepages for ML, Sandia’s main multigrid preconditioning package. ML is designed to solve large sparse linear systems of equations arising primarily from elliptic PDE discretizations. ML is used to define and build multigrid solvers and preconditioners, and it contains black-box classes to construct highly-scalable smoothed aggregation preconditioners. ML preconditioners have been used on thousands of processors for a variety of problems, including the incompressible Navier-Stokes equations with heat and mass transfer, linear and nonlinear elasticity equations, the Maxwell equations, semiconductor equations, and more.

Please use the links below to navigate the ML documentation:

*   An [overview](#ml-overview) of ML.
*   [Documentation](docs//ml/index.html) generated directly from ML’s source code by Doxygen.
*   [User Guides](ml-publications.html#ml-user-guides "ML Publications").
*   The [ML API](ml_api.html).
*   [Mail lists](http://trilinos.org/oldsite/packages/ml/mail_lists.html) for users and developers.
*   Relevant [papers](ml-publications.html "ML Publications") and [citations](ml_citations.html "ML Citations").
*   [Who are the ML developers?](http://trilinos.org/oldsite/packages/ml/team.html)
*   [How to cite ML](ml_citations.html).

ML documentation is created and maintained using Doxygen. Click [here](https://trilinos.org/ml/doxygen/development/inline/index.html) to access the latest Doxygen documentation, containing details about ML and its classes, examples of usage, how to interface with other Trilinos packages, and more.
 
If you use ML for your applications, please let us know by writing an e-mail to the ml developers. Please also cite ML using the following bibtex entry:

@TechReport{ml-guide,
    author      =  {M.W. Gee and C.M. Siefert and J.J. Hu and R.S. Tuminaro and M.G. Sala},
    title       =  {ML 5.0 Smoothed Aggregation User's Guide},
    institution =  {Sandia National Laboratories},
    year        =  {2006},
    number      =  {SAND2006-2649},
}

<a name="ml-overview"></a><span style="text-decoration: underline;">**Overview**</span>

ML is Sandia’s main multigrid preconditioning package. ML is designed to solve large sparse linear systems of equations arising primarily from elliptic PDE discretizations.

ML contains a variety of parallel multigrid schemes:

*   smoothed aggregation
*   FAS nonlinear multigrid
*   a special algebraic multigrid for the eddy current approximations to Maxwell’s equations. This eddy current solver is a unique capability of ML and utilizes the discrete nullspace of the operator in building the smoothers and grid hierarchy.

Within each of these methods there are several different algorithms to guide the type of coarsening and the inter-grid transfers (including the ability to drop weak coupling within the operator during inter-transfer construction).

**Extensibility**

ML can also be used as a framework to generate new multigrid methods. Using ML’s internal aggregation routines and Galerkin products, it is possible to focus on new types of inter-grid transfer operators without having to address the cumbersome aspects of generating an entirely new parallel algebraic multigrid code. We have used this flexibility to produce special multilevel methods using coarse grid finite element functions to serve as inter-grid transfers.

Our primary goal has been to provide state-of-the-art iterative methods that perform well on parallel computers (applications on over 3000 processors have been run) and that at the same time are easy to use for application engineers. In addition to providing algebraic multilevel methods to engineers, the ML library is also used in our research on preconditioners. At present, we are working closely with several specific Sandia applications in further extending our capabilities.

**Capabilities**

*   Parallel: MPI-based
*   Supported platforms: Linux clusters, Sun, SGI, Sandia’s ASCI red machine (a.k.a. Janus), Sandia’s RedStorm, IBM SP2, …
*   Data-Neutral Interface: Matrices are accessed via getrow() and matvec() functions. Wrappers for Aztec/MSR, Aztec/VBR and Epetra_RowMatrix matrices are furnished within the package.
*   Primary Multilevel Schemes
    *   Smoothed aggregation
    *   Edge element eddy current AMG
    *   Smoothed aggregation domain decomposition preconditioners (additive, hybrid)
    *   Finite element based two-level schemes
    *   Refinement-based multigrid
    *   Classical AMG
*   Parallel Smoother Methods

    *   Processor-based Gauss-Seidel type methods
    *   Processor-based block Jacobi, Gauss-Seidel and symmetric Gauss-Seidel
    *   Polynomial-based smoothers
    *   One step CG smoothing
    *   Two-stage distributed relaxation hybrid for eddy current equations
    *   Any [AztecOO](aztecoo.html) preconditioner
    *   Any [IFPACK](ifpack.html) preconditioner
    *   Any [Amesos](amesos.html) solver

    as coarse solver

    *   Sparse approximate inverse interface
*   A set of efficient and user-friendly, MATLAB-like interface, called [MLAPI](ml_api.html).

**Interoperability**

ML is designed to interoperate with other Trilinos packages, and in particular with the [AztecOO](aztecoo.html) linear solver package, also developed at Sandia. However, ML can be run stand-alone. Alternatively, the user can call ML from his own application by supplying matrix-getrow functions and matrix-vector multiply functions. The user can optionally supply application-specific smoothers, or use ML’s internal smoothers.

ML is used within several applications at Sandia and a few applications outside of Sandia. ML is released for external distribution and can be obtained as part of the Trilinos development environment.

[Read More](docs//ml/index.html) about ML, its project goals, functionalities, commented examples, more documentation.
