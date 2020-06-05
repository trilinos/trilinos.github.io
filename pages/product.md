---
title: Product
permalink: product.html
---

Because of the broad scope of Trilinos, and a continued project emphasis on developing production quality code, we have the following defined Products within Trilinos:

Data Services - [[overview](#data-services)] [[webpage](products/data.md)]  
Linear Solvers - [[overview](#linear-solvers)] [[webpage](products/linear.md)]      
Nonlinear Solvers - [[overview](#nonlinear-solvers)] [[webpage](products/nonlinear.md)]    
Discretizations - [[overview](#discretizations)] [[webpage](products/discretizations.md)]    
Framework - [[overview](#framework)] [[webpage](products/framework.md)]  

A brief summary of each capability area is provided below, as well as a link to the capability area homepage. Each capability area is assigned to a capability leader. The capability leaders are listed below and on the capability area homepages.

## Data Services
Leader - Karen Devine

Trilinos solvers, partitioners and discretization tools are built upon a collection of data containers and functions that support effecient parallel execution.  These packages support MPI, threading and vectorization and execution on distributed memory machines, multicore CPUs, and GPUS.
Packages include Kokkos, Tpetra and Epetra.

### Linear Solvers
Leader - Siva Rajamanickam

Trilinos provides a wide-variety of solution methods for linear and eigen systems. The Linear & Eigen Solvers Capability Area provides iterative and direct solvers, preconditioners, high-level interfaces, and eigen-solvers. Wide-variety of  preconditioners such as incomplete factorizations, domain decomposition preconditioners, and multigrid methods are supported. <a name="NonlinearSolvers"></a>

### Nonlinear Solvers
Leader - Roger Pawlowski

The Trilinos Embedded Nonlinear Analysis Tools Capability Area collects the top level algorithms (outermost loops) in a computational simulation or design study. These include: the solution of nonlinear equations, time integration, bifurcation tracking, parameter continuation, optimization, and uncertainty quantification. A common theme of our algorithm R&D efforts is the philosophy of Analysis beyond Simulation, which aims to automate many computational tasks that are often performed by application code users by trial-and-error or repeated simulation. The tasks that can be automated include performing parameter studies, sensitivity analysis, calibration, optimization, time step size control, and locating instabilities. Also included in this capability area is the automatic differentiation technology that can be used in an application code to provide the derivatives critical to the analysis algorithms.  
The packages represented in this area include Piro, NOX, LOCA, Rythmos, MOOCHO, Aristos, Sacado, Stokhos, and TriKota.

### Discretizations
Leader - Mauro Perego

The objective of the Discretizations product is to provide modular, interoperable and extensible tools for the discretization of integral and differential equations. Adopting state-of-the-art numerics and HPC programming models, the discretization tools target both research and production applications. The Discretizations product includes tools for mesh-based discretizations such as finite element analysis as well as meshless discretization such as generalized moving least squares. 

### Framework
Leader - Jim Willenbring

The Framework and Tools Capability Area provides resources for both users and developers. Like User Experience, this capability area is different from most of the other capability areas in that the resources provided extend beyond packages and focus on tools that aid in building, maintaining and documenting Trilinos.<a name="SoftwareEngineering"></a>
