---
title: Anasazi
permalink: anasazi.html
folder: packages
---

![Anasazi](http://trilinos.org/oldsite/packages/anasazi/anasazi.png)


<span style="text-decoration: underline;">**Overview**</span>

Anasazi is an extensible and interoperable framework for large-scale eigenvalue algorithms. The motivation for this framework is to provide a generic interface to a collection of algorithms for solving large-scale eigenvalue problems. Anasazi is interoperable because both the matrix and vectors (defining the eigenspace) are considered to be opaque objects—only knowledge of the matrix and vectors via elementary operations is necessary. One of the goals of Anasazi is to allow the user the flexibility to specify the data representation for the matrix and vectors and so leverage any existing software investment.

An implementation of Anasazi is accomplished via the use of interfaces. Current interfaces available include Epetra and Tpetra. This means any libraries that understand Epetra and Tpetra matrices and vectors (such as AztecOO and Belos) may also be used in conjunction with Anasazi.

<span style="text-decoration: underline;">**Capabilities**</span>

Anasazi supports the following solver/matrix combinations:

[![eigensolver_table](http://trilinos.org/wordpress/wp-content/uploads/2014/08/eigensolver_table.png)](http://trilinos.org/wordpress/wp-content/uploads/2014/08/eigensolver_table.png)

<span style="text-decoration: underline;">Chart notes:</span>

1.  This chart **does not** endorse the use of a particular solver for a particular eigenvalue problem.
2.  Abbreviations key
    1.  “Gen.” = generalized eigenvalue system
    2.  “Prec:” = can use a preconditioner
    3.  BKS = Block Krylov Schur
    4.  LOBPCG = Locally Optimial Block Preconditioned Conjugate Gradient
    5.  RTR = Riemannian Trust-Region method
3.  **^** denotes that these features may be implemented if there is sufficient interest.
4.  **$** denotes that the TraceMin family of solvers is currently experimental. We recommend that if a user wants to compute interior eigenpairs, she should disable the Ritz shifts. This recommendation temporary until the code leaves experimental status.

<span style="text-decoration: underline;">**Anasazi Publications**</span>

*   [Anasazi software for the numerical solution of large-scale eigenvalue problems](http://dx.doi.org/10.1145/1527286.1527287) -- Describes the design and development of the Anasazi package.
*   [Overview of Anasazi and its newest eigensolver, TraceMin](http://trilinos.org/wordpress/wp-content/uploads/2014/08/Klinvex-TUG-2014-Anasazi.pdf) -- Presentation from the Trilinos Users Group meeting, October 29th, 2014.
*   [Installing the Anasazi Eigensolver Package with Application to Some Graph Eigenvalue Problems](http://trilinos.org/wordpress/wp-content/uploads/2014/08/anasazi-ug-public.pdf "Installing the Anasazi Eigensolver Package with Application to Some Graph Eigenvalue Problems") -- Introductory installation and usage guide.

