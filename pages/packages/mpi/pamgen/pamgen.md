---
title: PAMGEN
permalink: pamgen.html
folder: mpi
show_sidebar: true
contact: dmhensi@sandia.gov
package: optipack
---

Welcome to the PAMGEN Home

PAMGEN creates hexahedral or quadrilateral (in 2D) finite element meshes of simple shapes (cubes and cylinders) in parallel. 
When linked to an application as a library, it allows each process of a parallel simulation to generate its finite element domain representation at execution time.

**Overview**  

Serial generation of large finite-element meshes is a serious bottleneck for large parallel simulations.PAMGEN, a parallel mesh generation library, surmounts this barrier by allowing on-the-fly scalable generation of simple finite element meshes. 
It has been used to generate more that 1.1 billion elements on 17,576 processors. The library operates on the assumption that the mesh generation process is deterministic. 
While each processor is provided with a complete specification of the mesh, it only creates a full representation of the elements that will be local to that processor. 
Since each processor has a complete specification of the mesh, no inter-processor communication is performed. The mesh generation proceeds through steps of decomposition, local element creation, and communication information generation. 
The final product of the library is a data structure that may be queried through a â€œCâ€ interface to determine local mesh geometry and topology as well as inter-processor connections. 
Currently the library is limited to generating meshes of domains with cylindrical, tubular, and block shapes. Substantial control is allowed over the distribution of elements within those shapes. Boundary condition regions, as node and element face lists, can be specified on the surfaces and interior of the mesh.
