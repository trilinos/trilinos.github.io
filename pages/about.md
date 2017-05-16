---
title: About the Trilinos Project
permalink: about.html
---

The Trilinos Project is an effort to develop and implement robust algorithms and enabling technologies using modern object-oriented software design, while still leveraging the value of established libraries such as [PETSc](http://www.mcs.anl.gov/petsc), [Metis/ParMetis](http://glaros.dtc.umn.edu/gkhome/views/metis/), [SuperLU](http://crd-legacy.lbl.gov/~xiaoye/SuperLU/), [Aztec](http://www.cs.sandia.gov/CRF/aztec1.html), the BLAS and [LAPACK](http://www.netlib.org/lapack). It emphasizes abstract interfaces for maximum flexibility of component interchanging, and provides a full-featured set of concrete classes that implement all abstract interfaces.

A core requirement of many engineering and scientific applications is the need to solve linear and non-linear systems of equations, eigensystems and other related problems. Thus it is no surprise that any part of the application that solves these problems is called a “solver.” The exact definition of what specifically constitutes a solver depends on many factors. However, a good working definition of a solver is the following: _any piece of software that finds unknown values for some set of discrete governing equations in an application._Another characteristic of solvers is that we can often implement them in such a way that they are “general-purpose”, so that the details of how the discrete problem was formed are not specifically needed for the solver to work (although information about problem characteristics can often be vital to robust solutions.) Advanced solution techniques increasingly require more than “just a matrix” since a the matrix alone discards so much information about the origin of the problem and how it might best be solved. As a result solvers need compatible tools in differentiation, discretization and data partitioning. These tools are also essential for robust solutions in scalable computing environments.

General-purpose linear and eigensolvers have been successfully used across a broad set of applications and computer systems. [EISPACK](http://www.netlib.org/eispack/), [LINPACK](http://www.netlib.org/linpack/) and [LAPACK](http://www.netlib.org/lapack) are just a few of the many packages that have made a tremendous impact, providing robust portable solvers to a broad set of applications. More recently packages such as [PETSc](http://www.mcs.anl.gov/petsc) and [Aztec](http://www.cs.sandia.gov/CRF/aztec1.html) have provided a large benefit to applications by giving users access to parallel distributed memory solvers that are easy-to-use and robust.

Sandia has historically had a variety of efforts to develop algorithms and enabling technologies for solving large-scale scientific and engineering problems. Often this development has been done within the context of a specific application code, providing a good robust solver that specifically meets the needs of that application. Even Aztec, one of the most important general-purpose solvers developed at Sandia, was developed specifically for [MPSalsa](http://www.cs.sandia.gov/CRF/MPSalsa/) and only later extracted for use with other applications. Unfortunately, even though application-focused software packages tend to be very robust and can often be made into very effective general-purpose software, the opportunity to re-use the basic set of tools developed for one application in the development of another application becomes very difficult.

The Trilinos Project grew out of a group of established algorithms efforts at Sandia, motivated by a recognition that a modest degree of coordination among these efforts could have a large positive impact on the quality and usability of the software we produce and therefore enhance the research, development and integration of new algorithms and enabling technologies into applications. Because of the tools and infrastructure that Trilinos provides, the degree of effort required to develop new algorithms and enabling technologies has been substantially reduced because our common base provides an excellent starting point. Furthermore, many applications are standardizing on the Trilinos APIs. As a result, these applications have access to all Trilinos solver components without any unnecessary interface modifications.

## Robust Implementation of Advanced Parallel Algorithms

Numerical methods are effective at solving a variety of problems on parallel computers. At the same time, there are many problems that cannot be solved by numerical methods, and there are good serial algorithms which have undesirable properties for parallel computing. An over-riding emphasis of the Trilinos Project is to develop robust algorithms for scientific and engineering applications on parallel computers, and make these algorithms accessible to application developers in the most effective way. All other Trilinos objectives are in some way derived from this primary goal.

Robust parallel numerical algorithms have long been an area of focus at Sandia and elsewhere, and will be in the future. Presently we are focused on the following algorithmic areas:

*   Automatic differentiation
*   Data partitioning for load balance and robustness
*   Multi-level preconditioners
*   Block iterative methods (linear and eigen solvers)
*   Incomplete factorizations
*   Solution of linear systems with successive and simultaneous right-hand-sides
*   Nonlinear methods including continuation
*   Large-scale optimization, e.g., SAND
*   Time integration methods

The software requirements to implement these algorithms, plus the additional requirement of easy integration of these packages into applications drive the remainder of the Trilinos objectives, as listed below.

## Use of Established Software in Trilinos

In recognition of the tremendous investment made in existing mathematical software, Trilinos makes use of LAPACK and the BLAS, as well as provides interfaces for Aztec, SuperLU, Mumps, Umfpack, etc., and soon PETSc.

## Distributed Memory Support in Trilinos

Trilinos is designed from the bottom up for use on a distributed memory parallel architectures. Many classes and interfaces are the same for both serial and distributed matrices, and explicit reference to parallel distributed memory details is confined to the necessary classes. At the same time, Trilinos provides powerful data distribution and redistribution capabilities, primarily as part of the Petra libraries.

## Trilinos Documentation and Downloads

Documentation for Trilinos packages is available on each [packages](packages.html) home page. Visit the [download](download.html) page to download Trilinos.

## Trilinos Featured in RCE HPC Podcast

Trilinos was featured in a February 2011 Research, Computing, & Engineering (RCE) High Performance Computing (HPC) podcast hosted by Brock Palen and Jeff Squyres. The podcast includes a very high-level summary of Trilinos and touches on other interesting topics like the origin of the name “Trilinos”. Visit the [RCE-cast website](http://www.rce-cast.com/Podcast/rce-49-trilinos.html) for more details and to download the podcast.