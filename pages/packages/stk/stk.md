---
title: STK
permalink: stk.html
folder: packages
show_sidebar: true
contact: <a href="mailto:STK-NGPTeam@sandia.gov">STK-NGPTeam@sandia.gov</a>, <a href="https://github.com/orgs/trilinos/teams/stk">@stk</a>
package: stk
---

Welcome to the STK Home

The Sandia Toolkit (STK) modules provide infrastructure to support the development of
computational engineering applications.

STK is composed of several modules:
* STK Util: various utilities such as parallel communication, command line parsing, etc.
* STK Topology: definitions of mesh-entity (elements, sides, etc) node orderings, side orderings.
* STK Mesh: parallel unstructured mesh
* STK IO: reading/writing of STK Mesh to/from Exodus files
* STK Coupling: support for MPMD coupling of MPI applications
* STK Search: geometric proximity bounding-box search
* STK Transfer: copy solution field values between meshes
* STK Balance: parallel load partitioning and dynamic rebalancing
* STK Middle Mesh: common refinement of two surface meshes (for conservative transfers)
* STK SIMD: a general interface to vector instructions such as SSE, AVX, etc.
* STK ExprEval: string function expression evaluation

Some STK modules depend on others, but in general it is not necessary to use all of them together.
For example, applications can use STK Search and STK Transfer without using STK Mesh. Also,
STK Util does not depend on any other STK modules.

Documentation for the STK modules is provided here:
[STK Manual 2024-07-12 PDF](pages/packages/mpi_x/stk/STKManual_2024-07-12-final.pdf "STK Manual PDF")

