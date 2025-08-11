---
title: Panzer
permalink: panzer.html
folder: packages
show_sidebar: true
contact: <a href="mailto:rppawlo@sandia.gov">Roger Pawlowski</a> (<a href="https://github.com/rppawlo">@rppawlo</a>), <a href="https://github.com/orgs/trilinos/teams/panzer">@panzer</a>
package: panzer
doxygen: true
---

Panzer provides global tools for finite element analysis. It handles continuous and discontinuous high-order compatible finite elements, as implemented in [Intrepid2](intrepid2.html) on unstructured meshes. Panzer relies on [Phalanx](phalanx.html) to manage with efficiency and flexibility the assembly of complex problems. Panzer also enables the solution of nonlinear problems, by interfacing with several Trlinos linear and nonlinear solvers. It computes derivatives and sensitivities through automatic differentiation ([Sacado](sacado.html)). It supports both [Epetra](epetra.html) and [Tpetra](tpetra.html) data structures and achieves performance portability through the [Kokkos](kokkos.html) programming model.

For an introductory tutorial to what Panzer is, how it works, and how you use it, check out this 
[presentation](pdfs/siamCseTalk.pdf). 
You can examine the associated code by [cloning Trilinos](https://github.com/trilinos/trilinos "git clone git@github.com:trilinos/Trilinos") 
and then poking around in `Trilinos/packages/panzer/adapters-stk/tutorial/siamCse17/`.
