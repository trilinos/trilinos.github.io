---
title: Amesos2
permalink: amesos2.html
folder: packages
show_sidebar: true
contact: amesos2-developers@software.sandia.gov
package: amesos2
doxygen: true
---

## Welcome to the Amesos2 Home

Amesos2 is a package for solving sparse linear systems using direct solvers. It differs from Amesos in that it is templated on the scalar and index types.

Amesos2 provides two native solvers:

*   KLU2 (Trilinos 11.12 and higher)
*   Basker (Trilinos 11.14 and higher)

KLU2 is enabled by default (12.4 and higher releases). Basker needs to be enabled during configure time if needed. All other solvers must be installed as third-party libraries (TPLs). Currently, Amesos2 supports these TPLs:

*   SuperLU (version 4.3)
*   SuperLU-MT
*   SuperLU-Dist ( tested versions 2.5,3.3,4.0, and 4.2)
*   MUMPS (version 5.0)
*   Pardiso (MKL version 10.3 or compatible)
*   LAPACK (for testing purposes)

Note that Amesos2 can only support scalar types that are supported by the desired third-party package (typically, float, double, complex, and double complex).

## Publications

If you use Amesos2 in your applications, please cite Amesos2 using the following publication:

*   [Amesos2 and Belos: Direct and iterative solvers for large sparse linear systems](http://dx.doi.org/10.3233/SPR-2012-0352 "Download 11.10"), Eric Bavier, Mark Hoemmen, Sivasankaran Rajamanickam, Heidi Thornquist, Scientific Programming, 2012, Volume 20, Issue 3.

Amesos2 is part of the 2nd generation, templated Trilinos stack, so it is templated both on the scalar type and the index type. We are adding support for more solvers. Please contact the developers if you have a specific request.