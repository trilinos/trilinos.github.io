---
title: FEI
permalink: fei.html
folder: mpi
show_sidebar: true
contact: william@sandia.gov
package: fei
---

**Welcome to the FEI Home**

The Finite Element Interface to Linear Solvers (FEI) is a general interface for assembling finite-element data into a linear system of equations. 
It is an abstraction layer that insulates finite-element application codes from linear-algebra issues such as sparse matrix storage formats and mappings from nodes and solution fields to distributed equation spaces. 
It puts a common face on various linear solvers, allowing finite-element applications to switch from one solver library to another with minimal changes to application code. 
FEI provides natural mechanisms for assembling finite-element data such as element-wise stiffness arrays and load vectors, boundary-condition specifications and constraint relations. 
It accepts data from multi-physics problems, allowing arbitrarily complicated elements with multiple solution fields per node, and cell centered fields. 
It is designed for use in distributed-memory parallel finite-element applications, to assemble and solve distributed linear systems using scalable underlying solver libraries.

FEI is still maintained but no longer deveoped.

