---
title: Meshes, Geometry and Load Balancing
permalink: meshes_geometry_load_balancing.html
folder: capabilities
---

## Trilinos Meshes, Geometry and Load Balancing Capabilities

> [Introduction](#Intro)
> 
> [Meshes and Geometry](#Mesh)
> 
> > [PAMGEN: Inline Meshing](#PAMGEN)  
> > [phdMesh: Unstructured Mesh Database](#phdMesh)  
> > [ABMesh: Array-Based Mesh Database](#ABMesh)  
> > [TUCASA: Parallel Mesh File Interface](#TUCASA)
> 
> [Load Balancing Capabilities](#LB)
> 
> > [Isorropia: Matrix Partitioning, Ordering and Coloring](#Isorropia)  
> > [Zoltan: Dynamic load balancing, partitioning, ordering and coloring](#Zoltan)

<a name="Intro"></a>

* * *

## Introduction

The goal of the Meshes, Geometry and Load-Balancing Capability Area is to provide libraries, tools, and common interfaces for creating, accessing and manipulating mesh and matrix data within applications. This capability area was created in FY08; several related packages were released in Trilinos v9\. Geometry and mesh efforts include in-application meshing tools for simple geometries, mesh databases, and mesh I/O and redistribution libraries. Load-balancing capabilities include partitioning and repartitioning for matrices and meshes, as well as other types of data (particles, circuits, etc.). The following activities are planned for this capability area:

*   Strengthen collaboration and integration between Trilinos and SIERRA by supporting incorporation of STKMesh into Trilinos.
*   Strengthen collaboration and integration between SciDAC and Trilinos by investigating use of ITAPS mesh interfaces with Trilinos packages.
*   Identify mesh, geometry and load-balancing capabilities needed for library-based application development, supporting Sandia’s component-based application effort; areas of interest include cell insertion and shape optimization.
*   Perform research and development into advanced matrix partitioning and ordering algorithms, including 2D matrix partitioning and nonsymmetric matrix ordering.

<a name="Mesh"></a>

* * *

## Meshes and Geometry

Generation, management and manipulation of mesh-based data play key roles in many scientific simulations. Finite difference, volume, and element methods require efficient mesh generation and management. Adaptive mesh refinement methods require even more sophisticated mesh management, along with the ability to modify, manipulate, and redistribute mesh and geometry data. The effectiveness of such tools directly impacts almost every phase of an application, from the discretization (e.g., [Intrepid](http://www.sandia.gov/~pbboche/research.html)) to the solution methods to the parallel efficiency.

Trilinos’ initial efforts in geometry and meshing capabilities will address three key components of mesh use in applications. Inline meshing ([PAMGEN](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#PAMGEN)) allows simple geometries to be meshed on-the-fly within a parallel application, rather than requiring mesh generation as a file-based preprocessing step. More complex meshes stored in files must be efficiently read in parallel and initially distributed to processors ([TUCASA](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#TUCASA)). And databases to efficiently store and manage mesh data greatly simply the bookkeeping burden of parallel applications ([phdMesh](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#phdMesh)).

### <a name="PAMGEN"></a>PAMGEN: Inline Meshing Library

<a name="PAMGEN"></a><a name="PAMGEN"></a>Point of Contact: D. Hensinger (SNL)  
Status: PAMGEN was released in Trilinos 9.0 in September 2008.Serial generation of large finite-element meshes is a serious bottleneck for large parallel simulations. PAMGEN, a parallel mesh generation library, surmounts this barrier by allowing on-the-fly scalable generation of simple finite element meshes. It has been used to generate more than 1.1 billion elements on 17,576 processors. Each processor is given a complete specification of the geometry, and creates a full representation of only the elements that are local to the processor. The resulting mesh data structure can be queried through a C interface to determine local mesh geometry and topology as well as inter-processor connections. Currently, the library generates meshes of domains with cylindrical, tubular, and block shapes. Substantial control is allowed over the distribution of elements within those shapes. Boundary condition regions, as node and element face lists, can be specified on the surfaces and interior of the mesh.

<div class="row">
    <div class="col-sm-3 col-md-offset-1">
        <img border="0" alt="Trilinos Team" src="images/pamgen001.png" width="30" height="30">
    </div>
    <div class="col-sm-3 col-md-offset-2">
        <img border="0" alt="Trilinos Team" src="images/pamgen002.png" width="30" height="30">
    </div>
</div>

### <a name="phdMesh"></a>phdMesh: Unstructured Mesh Database

<a name="phdMesh"></a>Point of Contact: H.C. Edwards (SNL)  
Status: phdMesh was released in Trilinos 9.0 in September 2008.<a name="phdMesh"></a>Multiphysics parallel applications with mixed discretization schemes, adaptive unstructured meshes and parallel distributed data sets have inherent complexity that must be managed. 
phdMesh is a compact, flexible software component designed to manage parallel, heterogeneous and dynamic unstructured meshes. phdMesh was developed as part of the [Mantevo](https://mantevo.org) project as a mini-application that approximates and assesses the performance of much larger mesh-based applications. 
The formal mesh model in phdMesh accommodates problem specifications through application-defined parts and fields; heterogeneous discretizations are accommodated through application-defined entities and connections. 
Computational efficiency is achieved by partitioning data into homogeneous kernels that may be operated on through a contiguous block of memory.


### <a name="ABMesh"></a>ABMesh: Array-Based Mesh Database

<a name="ABMesh"></a>Point of Contact: R. Drake (SNL)  
Status: ABMesh will be included in Trilinos 10.0 in September 2009.<a name="ABMesh"></a>ABMesh provides a mesh database with efficient parallel array-based data structures compatible with many mesh file formats (e.g., Exodus, Nemesis). ABMesh supports a large number of element types in two and three dimensions, element blocking for multi-material simulations, and nodal and elemental boundary conditions. It will provide convenient native interfaces as well as [ITAPS](http://www.itaps.org/)-compatible iterfaces for greater interoperability within applications.


### <a name="TUCASA"></a>TUCASA: Parallel Mesh File Interface

<a name="TUCASA"></a><a name="TUCASA"></a>Point of Contact: R. Drake (SNL)  
Status: TUCASA will be included in Trilinos 10.0 in September 2009. 

<a name="LB"></a>

* * *

## Load Balancing Capabilities

Load balancing is the distribution of data (e.g., matrix rows, matrix nonzeros, mesh elements, particles) to processors. 
Its goal is to eliminate processor idle time (by assigning equal amount of work to each processor) while attempting to minimize interprocessor communication (by minimizing the amount of off-processor data each processor needs). Static partitioning provides an initial distribution of data to processors; it can be done once as a preprocessor to a simulation. Repartitioning (a.k.a. dynamic load balancing) redistributes data to adjust for changing work loads or data dependencies within a simulation. 
Repartitioning has the additional goal of minimizing the cost of moving from the old distribution to the new one (a.k.a. data migration cost).

The capabilities to be provided in Trilinos include matrix partitioning for row-based, column-based, and nonzero-based distributions of 
matrix data ([Isorropia](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#Isorropia)), 
as well as general partitioning and repartitioning capabilities for a wide variety of data, including 
mesh entities ([Zoltan](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#Zoltan)).

<div class="row">
    <div class="col-sm-4 col-md-offset-1">
        <img border="0" alt="Trilinos Team" src="images/isorropia_2d.png" width="30" height="30">
    </div>
    <div class="col-sm-4 col-md-offset-2">
        <img border="0" alt="Trilinos Team" src="images/isorropia_spy.png" width="30" height="30">
    </div>
</div>

### <a name="Isorropia"></a>Isorropia: Matrix Partitioning

<a name="Isorropia"></a>Point of Contact: [E. Boman](http://www.sandia.gov/~egboman/) (SNL)  
Isorropia Page: [http://trilinos.sandia.gov/packages/isorropia/](http://trilinos.org/packages/isorropia/)  
Status: Isorropia was enhanced and released in Trilinos v9.0.[Isorropia](http://trilinos.org/packages/isorropia/) is a 
repartitioning/rebalancing package that redistributes matrices and matrix-graphs in a parallel execution setting 
to enable more efficient matrix computations. Isorropia is the package to use for distributing EPetra data structures. 
Through an interface to the Zoltan library, it computes parallel matrix distributions that have balanced computational work and 
low interprocessor communication costs for common matrix operations. It also creates Epetra maps for redistributing matrices 
according to the computed data distributions, and migrates matrix data to the new distribution. Current development efforts include 
matrix ordering and two-dimensional matrix partitioning interfaces.

Isorropia also contains interfaces to [Zoltan’s](http://www.cs.sandia.gov/Zoltan/) parallel coloring and matrix ordering capabilities. 
Parallel matrix ordering can reduce matrix fill during direct factorizations. The interface provides access to both the 
matrix permutation vector and the separator trees used in reordering. Parallel coloring is an important capability for some preconditioners. 
Colors are assigned to matrix rows depending on the connectivity of rows through nonzero entries in the matrix. 
The interface provides both distance-one and distance-two coloring. 
See [below](http://trilinos.sandia.gov/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#zoltan_ordering) for more details on coloring and ordering.

### <a name="Zoltan"></a>Zoltan: Dynamic load balancing, partitioning, coloring and ordering

<a name="Zoltan"></a>Point of Contact: [K. Devine](http://www.cs.sandia.gov/~kddevin/) (SNL)  
[Zoltan Page: http://www.cs.sandia.gov/Zoltan](http://www.cs.sandia.gov/Zoltan/)  
Status: Zoltan is currently available for download from the [Zoltan home page](http://www.cs.sandia.gov/Zoltan/). 
It is also released in Trilinos 9.0 in September 2008.The Zoltan library includes a suite of partitioning and repartitioning algorithms 
for general applications. It can be used for distributing matrices, meshes, particles, agents, or any objects within a simulation. 
The partitioning and repartitioning algorithms include geometric methods (useful for particle- and mesh-based applications), 
and connectivity-base methods (such as graph- and hypergraph-partitioning). Three interfaces to Zoltan exist (in order of decreasing maturity): 
the [native Zoltan interface](http://www.cs.sandia.gov/Zoltan/ug_html/ug.html) the [Isorropia](http://trilinos.org/packages/isorropia/) 
Epetra matrix interface, and the [ITAPS](http://www.itaps.org) mesh interface. The native Zoltan interface is data-structure neutral, 
so an application does not have to build or use specific data structures to use Zoltan. This design allows Zoltan to be used by a 
wide range of applications. Zoltan is widely used in the ASC community, and is a key component of the SciDAC CSCAPES 
and [ITAPS](http://www.itaps.org/) projects. Current research efforts include scalable partitioning strategies for multicore architectures, 
matrix ordering algorithms, and two-dimensional matrix partitioning.

<a name="zoltan_ordering"></a>Using essentially the same interfaces, Zoltan also enables parallel matrix ordering and coloring. 
Zoltan provides consistent interfaces to the graph ordering algorithms in [PT-Scotch](http://www.labri.fr/~pelegrin/scotch) and
[ParMETIS](http://glaros.dtc.umn.edu/gkhome/metis/parmetis/overview); using the same interface, users can switch between ordering methods 
to compare their effectiveness. Zoltan also provides native parallel distance-one and distance-two graph coloring using the same 
graph-based interface. These algorithms are state-of-the-art distributed memory implementations, as described in the following JPDC article:
[_A Framework for Scalable Parallel Greedy Coloring on Distributed Memory Computers_](http://www.sandia.gov/~egboman/papers/coloring_framework.pdf)
<br>
<img alt="" src="http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/zoltan_chisels.gif" width="90%" />
<br>
<img alt="" src="http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/zoltan_slac.gif" width="100%" />