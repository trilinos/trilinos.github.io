---
title: Belos
permalink: belos.html
folder: packages
show_sidebar: true
contact: <a href="mailto:hkthorn@sandia.gov">Heidi Thornquist</a> (<a href="https://github.com/hkthorn">@hkthorn</a>), <a href="https://github.com/orgs/trilinos/teams/belos">@belos</a>
package: belos
doxygen: true
---

Welcome to the Belos Home

<span style="text-decoration: underline;">**Overview**</span>

Belos provides next-generation iterative linear solvers and a powerful linear solver developer framework. This framework includes the following abstract interfaces and implementations:

*   Abstract interfaces to linear algebra using traits mechanisms. This allows the user to leverage any existing investment in their description of matrices and vectors. The provided concrete linear algebra adapters enable Belos to be used anywhere Epetra and Thyra are employed for linear algebra services.
*   Abstract interfaces to orthogonalization; implementations of iterated classical Gram-Schmidt (ICGS), classical Gram-Schmidt with a DGKS correction step, and iterated modified Gram-Schmidt (IMGS) are included.
*   Abstract interfaces to iteration kernels; implementations of conjugate gradient (CG), block CG, block GMRES, pseudo-block GMRES, block flexible GMRES, and GCRO-DR iterations are included.
*   Powerful solver managers are provided for solving a linear system using CG or block CG, GMRES or block GMRES with restarting, pseudo-block GMRES for performing single-vector GMRES simultaneously on multiple right-hand sides, and a single-vector recycled Krylov method (GCRO-DR).
*   Basic linear problem class is provided for the user to define a unpreconditioned or preconditioned (left, right, two-sided) linear system for Belos to solve.

<span style="text-decoration: underline;">**Publications**</span>

If you use Belos in your applications, please cite Belos using the following publication:

*   Amesos2 and Belos: Direct and iterative solvers for large sparse linear systems, Eric Bavier, Mark Hoemmen, Sivasankaran Rajamanickam, Heidi Thornquist, Scientific Programming, 2012, Volume 20, Issue 3.

Other Publications:

*   “[Amesos2 and Belos: Direct and iterative solvers for large sparse linear systems.](http://dx.doi.org/10.3233/SPR-2012-0352)” Eric Bavier, Mark Hoemmen, Sivasankaran Rajamanickam, and Heidi Thornquist. Scientific Programming, 2012.
*   [A Communication-Avoiding, Hybrid-Parallel, Rank-Revealing Orthogonalization Method](http://dx.doi.org/10.1109/IPDPS.2011.93) Mark Hoemmen. IEEE International Parallel and Distributed Processing Symposium, May 2011.
*   [Cooperative Application/OS DRAM fault recovery](http://dx.doi.org/10.1007/978-3-642-29740-3_28) Patrick G. Bridges, Michael A. Heroux, Mark Hoemmen, Kurt Ferreira, Philip Soltero, and Ronald B. Brightwell. Workshop on Resiliency in High-Performance Computing (Resilience 2011) in conjunction with the 17th International European Conference on Parallel and Distributed Computing (Euro-Par 2011), Bordeaux, France, 29 August -- 02 September 2011.
