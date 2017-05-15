---
title: Capabilities
permalink: capability-areas.html
---

# Capabilities

<span style="text-decoration: underline;">Because of the broad scope of Trilinos, we have defined capability areas within Trilinos:</span>

User Experience -- [[overview](#UX)] [[webpage](http://trilinos.org/capability-areas/user-experience/ "User Experience")]  
Parallel Programming Environments [[overview](#PPE)][[webpage](http://trilinos.org/capability-areas/parallel-programming-environments/ "Parallel Programming Environments")]  
Framework & Tools -- [[overview](#FrameworkTools)] [[webpage](http://trilinos.org/capability-areas/framework-and-tools/ "Framework and Tools")]  
Software Engineering Technologies and Integration -- [[overview](#SoftwareEngineering)] [[webpage](http://trilinos.org/capability-areas/software-engineering-technologies-and-integration/ "Software Engineering Technologies and Integration")]  
I/O Support -- [[overview](#IOSupport)]  
Meshes, Geometry, & Load Balancing -- [[overview](#GeometryMeshingLoadBlancing)] [[webpage](http://trilinos.org/capability-areas/meshes-geometry-and-load-balancing/ "Meshes, Geometry and Load Balancing")]  
Discretizations -- [[overview](#Discretizations)] [[webpage](http://trilinos.org/capability-areas/discretizations/ "Discretizations")]  
Scalable Linear Algebra -- [[overview](#ScalableLinearAlgebra)] [[webpage](http://trilinos.org/capability-areas/scalable-linear-algebra/ "Scalable Linear Algebra")]  
Linear & Eigen Solvers -- [[overview](#LinearEigenSolvers)] [[webpage](http://trilinos.org/capability-areas/linear-and-eigen-solvers/ "Linear and Eigen Solvers")]  
Embedded Nonlinear Analysis Tools -- [[overview](#NonlinearSolvers)] [[webpage](http://trilinos.org/capability-areas/embedded-nonlinear-analysis-tools/ "Embedded Nonlinear Analysis Tools")]

A brief summary of each capability area is provided below, as well as a link to the capability area homepage (note that some of the webpages are under construction). Each capability area is assigned to a capability leader. The capability leaders are listed below and on the capability area homepages.

## User Experience

Leader -- Bill Spotz

The User Experience capability area aims to help Trilinos users make effective and efficient use of Trilinos. We strive to make documentation, examples, and tutorials clear, accurate and easy to find; to improve interfaces; and to foster relationships between Trilinos and application developers.<a name="FrameworkTools"></a>

## Parallel Programming Environments

Leader -- H. Carter Edwards

In order to provide portability across current and emerging architectures, Trilinos packages rely on lightweight abstraction layers in order to access basic, architecture-dependent system capabilities. Epetra access the distributed memory machine capabilities via its Epetra_Comm abstraction. Tpetra uses similar features from Teuchos, and also relies on the recently-developed Kokkos package for multicore, manycore and GPU portability for multi-dimensional arrays and parallel execution patterns such as parallel_for, parallel_reduce and parallel_scan (and in the future asynchronous tasking). The Parallel Programming Environments Capability area is concerned with this thin layer that provides performance portability.

## Framework & Tools

Leader -- Jim Willenbring

The Framework and Tools Capability Area provides resources for both users and developers. Like User Experience, this capability area is different from most of the other capability areas in that the resources provided extend beyond packages and focus on tools that aid in building, maintaining and documenting Trilinos.<a name="SoftwareEngineering"></a>

## Software Engineering Technologies and Integration

Leader -- Roscoe Bartlett

The Trilinos “Software Engineering Technologies and Integration” capabilities area spans all of Trilinos relating to aspects of scalability, interoperability, integration, and any other critical Trilinos software engineering issue. For abstract numerical algorithms, the Thyra package plays a critical role in defining the standard interfaces to allow the scalable, interoperable, composeable vertical integration of basic linear operators and vectors, preconditioners and linear solvers, nonlinear solvers, bifurcation and stability analysis, transient solvers, optimization, and more. At the lower end of the spectrum, tools in Teuchos package for memory management (e.g. RCP), object configuration (e.g. ParameterList), and other areas also play a critical role in the composition and interoperability of software. Finally, principles and practices from the modern Lean & Agile software engineering community are refined and adapted to the numerical computational computing area to support the various missions of Trilinos.<a name="IOSupport"></a>

## I/O Support

Leader -- Jay Lofstead

The Trilinos I/O Support capability area provides general I/O support for applications using Trilinos libraries. In particular, this capability will include parallel I/O support to read and write selected Trilinos data structures to commonly-used file formats such as netCDF, hdf5, and Exodus. It will also include general libraries to support object serialization as well as application-directed checkpoint and restart.<a name="GeometryMeshingLoadBlancing"></a>

## Meshes, Geometry, & Load Balancing

Leader -- Karen Devine

The goal of the Geometry, Meshing and Load-Balancing Capability Area is to provide libraries, tools, and common interfaces for creating, accessing and manipulating mesh and matrix data within applications. This capability area is new in FY08 and will be released in Trilinos v9\. Geometry and meshing efforts include in-application meshing tools for simple geometries, mesh databases, and mesh I/O and redistribution libraries. Load-balancing capabilities include partitioning and repartitioning for matrices and meshes, as well as other types of data (particles, circuits, etc.).<a name="Discretizations"></a>

## Discretizations

Leader -- Mauro Perego

The discretization capability area is new to Trilinos 9.0\. The objective is to provide, over time, a collection of libraries and interfaces that enable rapid development of application codes for applications that require numerical solution of Partial Differential Equations (PDE). The tools included in this capability area are designed to work with the rest of Trilinos packages or to be used as interoperable components in existing user environments.  
The tools included in discretization capability area can be broadly divided into three related categories that correspond to the key steps in the numerical solution of PDEs by mesh-based methods.<a name="ScalableLinearAlgebra"></a>

## Linear Algebra Services

Leader -- Mark Hoemmen

Trilinos provides state-of-the art capabilities in scalable linear algebra computations. It focuses in particular on sparse graphs and matrices. Trilinos provides shared- and distributed-memory parallel data objects and computational kernels in several libraries. The packages in this capability area with which most users want to interact are Epetra and Tpetra. Other packages represented by this area include Thyra, Xpetra, Kokkos, EpetraExt, and Teuchos. Please see the [above link](http://trilinos.org/capability-areas/scalable-linear-algebra/ "Scalable Linear Algebra") for full details.<a name="LinearEigenSolvers"></a>

## Linear & Eigen Solvers

Leader -- Jonathan Hu

Trilinos provides a wide-variety of solution methods for linear and eigen systems. The Linear & Eigen Solvers Capability Area provides iterative and direct solvers, preconditioners, high-level interfaces, and eigen-solvers.<a name="NonlinearSolvers"></a>

## Embedded Nonlinear Analysis Tools

Leader -- Andy Salinger

The Trilinos Embedded Nonlinear Analysis Tools Capability Area collects the top level algorithms (outermost loops) in a computational simulation or design study. These include: the solution of nonlinear equations, time integration, bifurcation tracking, parameter continuation, optimization, and uncertainty quantification. A common theme of our algorithm R&D efforts is the philosophy of Analysis beyond Simulation, which aims to automate many computational tasks that are often performed by application code users by trial-and-error or repeated simulation. The tasks that can be automated include performing parameter studies, sensitivity analysis, calibration, optimization, time step size control, and locating instabilities. Also included in this capability area is the automatic differentiation technology that can be used in an application code to provide the derivatives critical to the analysis algorithms.  
The packages represented in this area include Piro, NOX, LOCA, Rythmos, MOOCHO, Aristos, Sacado, Stokhos, and TriKota.