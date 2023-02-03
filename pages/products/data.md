---
title: Data Service
permalink: data_service.html
folder: products
---

## I/O Support
Leader – Jay Lofstead

The Trilinos I/O Support capability area provides general I/O support for applications using Trilinos libraries. In particular, this capability will include parallel I/O support to read and write selected Trilinos data structures to commonly-used file formats such as netCDF, hdf5, and Exodus. It will also include general libraries to support object serialization as well as application-directed checkpoint and restart.

* * *

## Trilinos Meshes, Geometry and Load Balancing Capabilities

### Introduction

The goal of the Meshes, Geometry and Load-Balancing Capability Area is to provide libraries, tools, and common interfaces for creating, accessing and manipulating mesh and matrix data within applications. This capability area was created in FY08; several related packages were released in Trilinos v9\. Geometry and mesh efforts include in-application meshing tools for simple geometries, mesh databases, and mesh I/O and redistribution libraries. Load-balancing capabilities include partitioning and repartitioning for matrices and meshes, as well as other types of data (particles, circuits, etc.). The following activities are planned for this capability area:

*   Strengthen collaboration and integration between Trilinos and SIERRA by supporting incorporation of STKMesh into Trilinos.
*   Strengthen collaboration and integration between SciDAC and Trilinos by investigating use of ITAPS mesh interfaces with Trilinos packages.
*   Identify mesh, geometry and load-balancing capabilities needed for library-based application development, supporting Sandia’s component-based application effort; areas of interest include cell insertion and shape optimization.
*   Perform research and development into advanced matrix partitioning and ordering algorithms, including 2D matrix partitioning and nonsymmetric matrix ordering.

### Meshes and Geometry

Generation, management and manipulation of mesh-based data play key roles in many scientific simulations. Finite difference, volume, and element methods require efficient mesh generation and management. Adaptive mesh refinement methods require even more sophisticated mesh management, along with the ability to modify, manipulate, and redistribute mesh and geometry data. The effectiveness of such tools directly impacts almost every phase of an application, from the discretization (e.g., [Intrepid](http://www.sandia.gov/~pbboche/research.html)) to the solution methods to the parallel efficiency.

Trilinos’ initial efforts in geometry and meshing capabilities will address three key components of mesh use in applications. Inline meshing ([PAMGEN](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#PAMGEN)) allows simple geometries to be meshed on-the-fly within a parallel application, rather than requiring mesh generation as a file-based preprocessing step. More complex meshes stored in files must be efficiently read in parallel and initially distributed to processors ([TUCASA](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#TUCASA)). And databases to efficiently store and manage mesh data greatly simply the bookkeeping burden of parallel applications ([phdMesh](http://trilinos.org/oldsite/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#phdMesh)).

#### PAMGEN: Inline Meshing Library

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

#### phdMesh: Unstructured Mesh Database

<a name="phdMesh"></a>Point of Contact: H.C. Edwards (SNL)  
Status: phdMesh was released in Trilinos 9.0 in September 2008.<a name="phdMesh"></a>Multiphysics parallel applications with mixed discretization schemes, adaptive unstructured meshes and parallel distributed data sets have inherent complexity that must be managed. 
phdMesh is a compact, flexible software component designed to manage parallel, heterogeneous and dynamic unstructured meshes. phdMesh was developed as part of the [Mantevo](https://mantevo.org) project as a mini-application that approximates and assesses the performance of much larger mesh-based applications. 
The formal mesh model in phdMesh accommodates problem specifications through application-defined parts and fields; heterogeneous discretizations are accommodated through application-defined entities and connections. 
Computational efficiency is achieved by partitioning data into homogeneous kernels that may be operated on through a contiguous block of memory.


#### ABMesh: Array-Based Mesh Database

<a name="ABMesh"></a>Point of Contact: R. Drake (SNL)  
Status: ABMesh will be included in Trilinos 10.0 in September 2009.<a name="ABMesh"></a>ABMesh provides a mesh database with efficient parallel array-based data structures compatible with many mesh file formats (e.g., Exodus, Nemesis). ABMesh supports a large number of element types in two and three dimensions, element blocking for multi-material simulations, and nodal and elemental boundary conditions. It will provide convenient native interfaces as well as [ITAPS](http://www.itaps.org/)-compatible iterfaces for greater interoperability within applications.


#### TUCASA: Parallel Mesh File Interface

<a name="TUCASA"></a><a name="TUCASA"></a>Point of Contact: R. Drake (SNL)  
Status: TUCASA will be included in Trilinos 10.0 in September 2009. 

### Load Balancing Capabilities

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

#### Isorropia: Matrix Partitioning

<a name="Isorropia"></a>Point of Contact: [E. Boman](http://www.sandia.gov/~egboman/) (SNL)  
Isorropia Page: [https://trilinos.org/isorropia/](isorropia.html)  
Status: Isorropia was enhanced and released in Trilinos v9.0.[Isorropia](isorropia.html) is a 
repartitioning/rebalancing package that redistributes matrices and matrix-graphs in a parallel execution setting 
to enable more efficient matrix computations. Isorropia is the package to use for distributing EPetra data structures. 
Through an interface to the Zoltan library, it computes parallel matrix distributions that have balanced computational work and 
low interprocessor communication costs for common matrix operations. It also creates Epetra maps for redistributing matrices 
according to the computed data distributions, and migrates matrix data to the new distribution. Current development efforts include 
matrix ordering and two-dimensional matrix partitioning interfaces.

Isorropia also contains interfaces to [Zoltan](https://sandialabs.github.io/Zoltan/) parallel coloring and matrix ordering capabilities. 
Parallel matrix ordering can reduce matrix fill during direct factorizations. The interface provides access to both the 
matrix permutation vector and the separator trees used in reordering. Parallel coloring is an important capability for some preconditioners. 
Colors are assigned to matrix rows depending on the connectivity of rows through nonzero entries in the matrix. 
The interface provides both distance-one and distance-two coloring. 
See [below](https://trilinos.org/CapabilityWebpages/GeomMeshLoadBal/GeomMeshBal_Capability.html#zoltan_ordering) for more details on coloring and ordering.

#### Zoltan: Dynamic load balancing, partitioning, coloring and ordering

Point of Contact: [K. Devine](http://www.cs.sandia.gov/~kddevin/) (SNL)  
[Zoltan Page: https://sandialabs.github.io/Zoltan/](https://sandialabs.github.io/Zoltan/)  
Status: Zoltan is currently available for download from the [Zoltan home page](https://sandialabs.github.io/Zoltan/). 
It is also released in Trilinos 9.0 in September 2008.The Zoltan library includes a suite of partitioning and repartitioning algorithms 
for general applications. It can be used for distributing matrices, meshes, particles, agents, or any objects within a simulation. 
The partitioning and repartitioning algorithms include geometric methods (useful for particle- and mesh-based applications), 
and connectivity-base methods (such as graph- and hypergraph-partitioning). Three interfaces to Zoltan exist (in order of decreasing maturity): 
the [native Zoltan interface](https://sandialabs.github.io/Zoltan/ug_html/ug.html) the [Isorropia](isorropia.html) 
Epetra matrix interface, and the [ITAPS](http://www.itaps.org) mesh interface. The native Zoltan interface is data-structure neutral, 
so an application does not have to build or use specific data structures to use Zoltan. This design allows Zoltan to be used by a 
wide range of applications. Zoltan is widely used in the ASC community, and is a key component of the SciDAC CSCAPES 
and [ITAPS](http://www.itaps.org/) projects. Current research efforts include scalable partitioning strategies for multicore architectures, 
matrix ordering algorithms, and two-dimensional matrix partitioning.

Using essentially the same interfaces, Zoltan also enables parallel matrix ordering and coloring. 
Zoltan provides consistent interfaces to the graph ordering algorithms in [PT-Scotch](http://www.labri.fr/~pelegrin/scotch) and
[ParMETIS](http://glaros.dtc.umn.edu/gkhome/metis/parmetis/overview); using the same interface, users can switch between ordering methods 
to compare their effectiveness. Zoltan also provides native parallel distance-one and distance-two graph coloring using the same 
graph-based interface. These algorithms are state-of-the-art distributed memory implementations, as described in the following JPDC article:
[_A Framework for Scalable Parallel Greedy Coloring on Distributed Memory Computers_](http://www.sandia.gov/~egboman/papers/coloring_framework.pdf)
<br>
<img alt="" src="/images/zoltan_chisels.gif" width="90%" />
<br>
<img alt="" src="/images/zoltan_slac.gif" width="100%" />

* * *

## Linear algebra objects and services

Trilinos offers linear algebra objects such as sparse graphs, sparse matrices, and dense vectors that can be created, modified, and utilized in various computations such as sparse matrix-vector multiplies or dot products. Additionally, one can integrate their own linear algebra implementations or functions into Trilinos and use them within the solvers in Trilinos. This collection of features is referred to as linear algebra services.

### Parallelism

All of these linear algebra objects can use MPI (the Message-Passing Interface) for distributed-memory parallel computation, though we do not _require_ MPI. Some of them can combine this MPI capability with shared-memory parallelism, using OpenMP, Pthreads, or CUDA. Trilinos has a unique general-purpose parallel data redistribution facility, inspired originally by Zoltan, that you can use for your own applications. Trilinos’ linear algebra is known to scale to hundreds of thousands of parallel processes, but it is also meant to run well on a workstation or laptop. Users have even run it on a cell phone!

### Trilinos packages

Trilinos has two packages that implement scalable linear algebra: **Epetra** and **Tpetra**. (These are pronounced “EE-pe-tra” resp. “TEE-pe-tra.” E stands for “essential,” and T for “templated,” in the C++ sense of “template.”) There are two packages because Tpetra required C++ language capabilities that were not supported in all compilers around the year 2000\. Here is a comparison of their features:

*   **Parallelism**: Epetra supports MPI parallelism, with very limited use of OpenMP for some sparse matrix and dense vector kernels. Tpetra has more general “MPI+X” support, where X is any of various shared-memory parallel programming models. These include OpenMP, Pthreads (POSIX Threads), and CUDA. Tpetra implements this in a performance-portable way using the Kokkos shared-memory parallel programming model.
*   **Large problems**: Both Epetra and Tpetra have support for 64-bit global indices, which let users solve problems with over two billion entities (e.g., rows, columns, or matrix entries). Tpetra’s support for 64-bit global indices is more mature. Tpetra also has optional support for 64-bit _local_ indices, which allows that many entities within a single MPI process.
*   **Data types**: Epetra only allows real double-precision floating-point values in its matrices and vectors. Tpetra lets users fill matrices and vectors with data of other types as well, including single-precision real, complex, extended precision, and types for advanced analysis (e.g., automatic differentiation or polynomial chaos expansions for solving stochastic partial differential equations). You may create objects with different data types at run time, and perform mixed-precision computations.

Epetra and Tpetra linear algebra objects form the foundation of an entire “stack” of linear and nonlinear solvers in Trilinos. Almost every Trilinos package depends on one of these two packages. Epetra has been in use longer and has more users. However, its interface is frozen, and no new features will be added unless there is a very good reason. Tpetra is where all development work has been concentrating for at least three years, and where future development will concentrate.

Trilinos implements some linear algebra capabilities in other packages as well:

*   **Teuchos** (pronounced “TEF-hos”) wraps the standard BLAS and LAPACK libraries, and provides an abstraction over MPI communicators and some MPI operations.
*   **Kokkos** (pronounced “KO-kos”) implements a unified shared-memory parallel programming model, and also includes computational kernels for use in Tpetra and other packages.
*   **Thyra** (pronounced “THEE-ruh,” with TH as in “theta”) provides a generic interface to linear operators (e.g., matrices and preconditioners) and vectors. It can wrap Epetra or Tpetra objects. Thyra is particularly useful for constructing block vectors, matrices, and preconditioners, for example when solving saddle-point problems. Users most often encounter Thyra when using the Stratimikos package to create and use linear solvers and preconditioners.
*   **Xpetra** (pronounced “X-pe-tra”) wraps Epetra and Tpetra, and lets users switch between the two implementations at run time. It was designed for the algebraic multigrid package MueLu, but has been adopted by other packages, like Zoltan2.

### How do I get started?

You can get started by looking at [the Tpetra documentation.](https://trilinos.org/docs/dev/packages/tpetra/doc/html/index.html) This page gives an overview of Tpetra, and links to the Tpetra tutorial. We particularly recommend the Tpetra tutorial as a way to get started creating sparse matrices and dense vectors.
