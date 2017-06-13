---
title: AztecOO
permalink: aztecoo.html
folder: packages
---

## Welcome to the AztecOO Home

AztecOO provides an object-oriented interface the the well-known Aztec solver library. Furthermore, it allows flexible construction of matrix and vector arguments via Epetra matrix and vector classes. Finally, AztecOO provide additional functionality not found in Aztec and any future enhancements to the Aztec package will be available only through the AztecOO interfaces.

<span style="text-decoration: underline;">**Overview**</span>

AztecOO contains a number of classes. They are:

*   AztecOO -- Primary solver class. An AztecOO object is instantiated using and Epetra_LinearProblem object. The solver options and parameters can be set using SetAztecOption() and SetAztecParam() methods on an AztecOO object.
*   Aztec2Petra() -- Utility function to convert from Aztec date structures to Epetra objects. This function can be useful when migrating from Aztec to AztecOO. It is used internally by the AZOO_iterate function.
*   AZOO_iterate() -- Utility function that mimics the behavior and calling sequence of AZ_iterate, the primary solver call in Aztec. AZOO_iterate converts Aztec matrix, vectors, options and params into Epetra and AztecOO objects. It then calls AztecOO to solve the problem. For current Aztec users, this function should provide identical functionality to AZ_iterate, except for the extra memory used by having Epetra versions of the matrix and vectors.  
    Warning:Please note that AZOO_iterate is meant to provide a smooth transition for current Aztec users to AztecOO. We do not advocate this function as a permanent solution to switching from Aztec to AztecOO.

AztecOO and Matrix Free usage.

AztecOO supports a “matrix-free” mechanism via the pure virtual class Epetra_RowMatrix. This class is part of Epetra and is implemented by the Epetra_CrsMatrix and Epetra_VbrMatrix classes. It is possible to implement Epetra_RowMatrix using other matrix classes. AztecOO can then use this alternate implementation to provide the matrix multiply capabilities, and to obtain row value information from the matrix for constructing preconditioners. For details of Epetra, see the Epetra home page.

<span style="text-decoration: underline;">**Documents**</span>

*   [User Guide](pdfs/AztecOOUserGuide.pdf) (.pdf)

![](images/aztec.jpg)

## Aztec 2.1 Foundation for AztecOO

<div style="color: #000000;">The Aztec large-scale parallel iterative solver library software (1995, 1995, 1998, 1999) contributed source code to the development of the AztecOO effort. This includes parallel Krylov solvers, parallel preconditioning techniques, and parallel unstructured halo communication for unstructured mesh PDE solvers.</div>

<div style="color: #000000;">Aztec is embedded in the current AztecOO capability in Trilinos.</div>

Aztec 2.1 is still available at this link: [http://www.cs.sandia.gov/CRF/aztec1.html](http://www.cs.sandia.gov/CRF/aztec1.html)

## The Aztec development team:

<div style="color: #000000;">John N. Shadid [PI] (version 1.0, 1.1, 2.0, 2.1)</div>

<div style="color: #000000;">Scott Hutchinson [Co-PI] (version 1.0, 1.1, 2.0, 2.1)</div>

<div style="color: #000000;">Ray Tuminaro [Co-PI] (version 1.0, 1.1, 2.0, 2.1)</div>

<div style="color: #000000;">Lydie Prevost (version 2.0 )</div>

<div style="color: #000000;">Charles Tong (version 2.0)</div>

<div style="color: #000000;">Mike Heroux (Version 2.1)</div>