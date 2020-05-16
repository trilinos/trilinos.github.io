---
title: About the Trilinos Project
permalink: about.html
---

A core requirement of many engineering and scientific applications is the need to solve linear and non-linear systems of equations, eigensystems and other related problems. Thus it is no surprise that any part of the application that solves these problems is called a “solver.” The exact definition of what specifically constitutes a solver depends on many factors. However, a good working definition of a solver is the following: _any piece of software that finds unknown values for some set of discrete governing equations in an application._ Another characteristic of solvers is that we can often implement them in such a way that they are “general-purpose”, so that the details of how the discrete problem was formed are not specifically needed for the solver to work (although information about problem characteristics can often be vital to robust solutions.) Advanced solution techniques increasingly require more than “just a matrix” since a the matrix alone discards so much information about the origin of the problem and how it might best be solved. As a result solvers need compatible tools in differentiation, discretization and data partitioning. These tools are also essential for robust solutions in scalable computing environments.

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
