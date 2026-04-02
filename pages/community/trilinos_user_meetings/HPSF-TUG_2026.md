---
title: HPSF / Trilinos User-Developer Group Meeting 2026
permalink: HPSF-TUG_2026.html
folder: community
---


## Dates

March 18-19, 2026

## Location

Chicago, Illinois, USA

Contact: [Curtis Ober](mailto:ccober@sandia.gov)

---

## Agenda


<p style="text-align: center;"><span style="text-decoration: underline;">Wednesday, March 18th, 2026</span></p>

<table summary="Timetable">
<tbody>

<tr><th>
<abbr>  1:45pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSFCon2026-Ober.pdf">Welcome to HPSF / TUG Meeting!</a> (Curtis Ober)  [<a href="https://www.youtube.com/watch?v=b_uykd8K-9Y">video</a>]  <br><br>
This presentation will kick off the Trilinos Users-Developers Group (TUG) meeting, highlighting key accomplishments from 2025 and outlining plans for 2026. The meeting is divided into two parts:

Wednesday, March 18, 2026: Focused on new users and developers, this session will provide an overview of Trilinos, its capabilities, and examples demonstrating its functionality. Foundational questions like "What is Trilinos?" and "What are its capabilities?" will be addressed.

Thursday, March 19, 2026: This session will feature technical talks on key Trilinos development areas:

 * DevSecOps (CI/CD): Updates on secure and efficient development practices.
 * Core Area: Foundational capabilities supporting Trilinos packages and applications.
 * Solvers Area: Advances in preconditioners, linear/nonlinear solvers, and eigen solvers.
 * Discretization & Analysis Area: Tools for discretization, solution, and analysis of PDEs.

Thursday will also include user community presentations showcasing applications and feedback, followed by open discussions and one-on-one consultations with Trilinos developers to address specific challenges.
</td> </tr>

<tr><th>
<abbr>  1:55pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF_BuildAndTestTrilinos.pdf">How to Configure, Build, and Test Trilinos</a> (Samuel Browne)  [<a href="https://www.youtube.com/watch?v=KbwqDqz5WT8">video</a>]  <br><br>
The Trilinos project is a large collection of inter-dependent scientific software computing packages aimed at HPC users, manageable within a common build framework called the Tribal Build, Integrate, and Test System (TriBITS).  Due to the breadth and depth of the configuration combinations that are inherent in a suite with the level of capability provided by Trilinos, configure/build/test can be a nontrivial exercise.  In particular, users have long experienced challenges identifying an initial configuration that can provide the capability that they want enabled within Trilinos.  This talk is aimed at software developers and researchers interested in the fundamentals of building Trilinos, and is intended to function as a “Getting Started” presentation for common needs and desires.
</td> </tr>

<tr><th>
<abbr>  2:25pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/CoreProductsOverview.pdf">An Introduction to the Trilinos Core Products</a> (Roger Pawlowski)  [<a href="https://www.youtube.com/watch?v=L8fFF8FEkCQ">video</a>]  <br><br>
The Trilinos Core area includes packages that form the basic building blocks for Trilinos capabilities. This talk will briefly introduce each package, it’s capabilities and demonstrate how the packages can be pulled together into an application. The Core area will cover the following packages. The Kokkos performance portability library provides data structures and parallel algorithms that are performant on both CPU and GPU architectures. The Kokkos-Kernels library provides performance portable BLAS and LAPACK routines. The Tpetra library provides MPI-based parallel distributed linear algebra data structures built on Kokkos. The Teuchos library provides basic utilities for a common look and feel across Trilinos packages. The Zoltan library provides parallel distributed load balancing tools. The PyTrilinos package provides python wrappers for Trilinos capabilities. The Thyra package provides abstraction layers for writing algorithms for linear algebra, linear solvers and nonlinear solvers. 
</td> </tr>

<tr><th>
<abbr>  2:55pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/2026-HPSF-Solvers-Overview.pdf">Linear Solver Capabilities in the Trilinos Project</a> (Jonathan Hu)  [<a href="https://www.youtube.com/watch?v=Ht-SNF2Rp3Q">video</a>]  <br><br>
Trilinos provides a wide variety of linear solver and preconditioner libraries that are designed to run scalably on modern CPU and GPU architectures.  In this talk, I’ll give an overview of the capabilities, which include Krylov solvers, algebraic multigrid, incomplete factorizations, domain decomposition, and classic algebraic splittings.  I’ll include some introductory examples, as well as some recent simulation results that highlight performance and scalability. 
</td> </tr>

<tr><th>
<abbr>  3:25pm </abbr></th>  <td> <strong>Coffee Break</strong>
</td> </tr>

<tr><th>
<abbr>  3:50pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF_TrilinosIntro_2026_Perego.pdf">Overview of Trilinos Discretization and Analysis Capabilities</a> (Mauro Perego)  [<a href="https://www.youtube.com/watch?v=EQutGRWpHlQ">video</a>]  <br><br>
This presentation provides an overview of the discretization and analysis tools offered by the Trilinos software suite. We show how high-order finite element discretization on unstructured grids and time integration schemes can be used to efficiently solve real-world scientific applications as examples. Furthermore, we explore the use of automatic differentiation and adjoint capabilities for addressing nonlinear problems and computing sensitivities. We also highlight the simulation-constrained optimization features available through the ROL package, demonstrating how various Trilinos tools collaborate to effectively tackle large-scale inference problems. In conclusion, we present several patterns for how applications can adopt Trilinos tools based on their specific requirements and desired levels of integration.
</td> </tr>

<tr><th>
<abbr>  4:20pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/xxxx">PyTrilinos2: Using Trilinos from Python</a> (Christian Glusa)  [<a href="https://www.youtube.com/watch?v=NfEd8H8VcNM">video</a>]  <br><br>
PyTrilinos2 is an auto-generated Python interface for several Trilinos packages. I will explain how additional C++ functionality can be exposed to Python and demonstrate existing solver capabilities.
</td> </tr>

</tbody>
</table>



<p style="text-align: center;"><span style="text-decoration: underline;">Thursday, March 19th, 2026</span></p>

<table summary="Timetable">
<tbody>

<tr><th>
<abbr>  9:00am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF_Framework_Update_2026.pdf">Trilinos DevOps/CI Updates 2026</a> (Samual Browne)  [<a href="https://www.youtube.com/watch?v=FmudBi-U_tg">video</a>]  <br><br>
The Trilinos project is one of many in the scientific software community that employs the concept of Continuous Integration and thusly has a testing process that ensures code functionality and quality as part of its contribution process. This talk is aimed at software developers and researchers interested in recent developments that have affected Trilinos’ CI practices, as well as general build/test improvements for Trilinos.  Additional topics include C++ standard requirements, compiler and MPI version support roadmaps, current and future plans for supported builds of Trilinos using Spack, and large-scale package deprecation mechanics for Epetra-based packages. By the end of the session, participants will have a clearer understanding of how to effectively contribute to Trilinos, and the direction that DevSecOps efforts in Trilinos are heading in the future.
</td> </tr>

<tr><th>
<abbr>  9:20am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/CoreProductsUpdate.pdf">An Update on the Trilinos Core Products</a> (Roger Pawlowski)  [<a href="https://www.youtube.com/watch?v=C-HiuM3fU1U">video</a>]  <br><br>
The Trilinos Core area includes packages that form the basic building blocks for Trilinos capabilities. This talk will give updates on recent code development efforts over the last year and discuss future plans for each package. We will cover the following packages. The Kokkos performance portability library provides data structures and parallel algorithms that are performant on both CPU and GPU architectures. The Kokkos-Kernels library provides performance portable BLAS and LAPACK routines. The Tpetra library provides MPI-based parallel distributed linear algebra data structures built on Kokkos. The Teuchos library provides basic utilities for a common look and feel across Trilinos packages, including a reference counted smart pointer, print utilities, timers and a parameter list for user input. The Zoltan/Zoltan2 libraries provides parallel distributed load balancing tools. The PyTrilinos2 package provides python wrappers for Trilinos capabilities. The Thyra package provides abstraction layers for writing abstract numerical algorithms for linear algebra, linear solvers and nonlinear solvers.
</td> </tr>

<tr><th>
<abbr>  9:40am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/2026-HPSF-Solvers-WhatsNew.pdf">Recent Developments in Trilinos Linear Solvers</a> (Jonathan Hu)  [<a href="https://www.youtube.com/watch?v=DoZ35oQ9b-o">video</a>]  <br><br>
In this talk, I'll describe recent developments in Trilinos linear solver packages and provide select results.
</td> </tr>

<tr><th>
<abbr> 10:00am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF_TUG_Update_Perego.pdf">An Update on Trilinos Discretization and Analysis Capabilities</a> (Mauro Perego)  [<a href="https://www.youtube.com/watch?v=91xuwA4ArD4">video</a>]  <br><br>
After briefly overviewing the tools provided by Trilinos for the discretization and analysis of partial differential equations, we present recent updates and new features. Key developments include the adoption of Kokkos 5, the archival of the legacy solver stack including the original non-portable finite element implementation, and the introduction of a Python interface for the Rapid Optimization Library (ROL). Additionally, we will discuss structure-preserving optimization techniques for finite element implementations. 
</td> </tr>

<tr><th>
<abbr> 10:20pm </abbr></th>  <td> <strong>Coffee Break</strong>
</td> </tr>

<tr><th>
<abbr> 10:45am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF_Tpetra_2026_Siefert.pdf">Tracking Trilinos Performance</a> (Chris Siefert)  [<a href="https://www.youtube.com/watch?v=5msA87djSpA">video</a>]  <br><br>
In order to keep Trilinos running performantly every night on every system of  interest, the Trilinos Tpetra/Performance team maintains nightly performance  testing of Trilinos on systems across the Department of Energy.  This talk will  highlight recent developments in machine support, testing infrastructure and lessons learned as part of this year's testing.  We'll also highlight new ideas and capabilities developed through collaborations as part of the HPSF Benchmarking Working Group.
</td> </tr>

<tr><th>
<abbr> 11:05am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/WARDEN_HPSF_Talk.pdf">WARDEN: A New Software for Visualizing Subtimer Data</a> (Dane Camacho)  [<a href="https://www.youtube.com/watch?v=7C91kmoC7SM">video</a>]  <br><br>
WARDEN (Watchful Analysis for Research and Data Evaluation of Nested structures) is a plotting software that takes in nested XML timer data from subroutines run on high performance computers, and parses them to display up-to-date graphs of each subtimer on each machine. In addition to displaying timer graphs, this software takes care of "diving-in" to subgraphs, swapping between different machines, and annotating specific dates.
</td> </tr>

<tr><th>
<abbr> 11:25am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF_TUG_2026_03_19_Frye.pdf">Lets make 40 Trilinos spack packages?</a> (Joe Frye)  [<a href="https://www.youtube.com/watch?v=hXZ7vU1QJis">video</a>]  <br><br>
Trilinos is a complex set of interdependent packages with a reputation of being difficult to configure and build especially for new users.  Spack is a build from source package manager which aims to make building complex scientific software easier.  Recently I have been working to use spack to drive trilinos builds at a (trilinos) package level.   I would like to present on my experiences in building an ecosystem of spack packages for a large complex software suite.   This effort involves interesting features that mat be relevant to other projects.  

First, he generation of spack package.py files from existing build system configuration in trilinos provides an automated way to keep the spack packages files up to date.   Additionally,  spack package acting as a base class helps to reduce generated code and to standardize important configuration between packages. Finally, figuring out how to allow contributions from the open-source community while implementing as much automation as possible allows us to reduce maintenance burden while keeping avenues of collaboration open.  
</td> </tr>

<tr><th>
<abbr> 11:40am </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/malachi-hpsf-2026.pdf">Block-based Algebraic Multigrid Preconditioners in Trilinos/Teko</a> (Malachi Phillips)  [<a href="https://www.youtube.com/watch?v=BUE4MVnLwMMy">video</a>]  <br><br>
The solution of multiphysics problems depends on the construction of robust preconditioners which significantly influence the convergence rate and computational performance of linear solvers. For tightly coupled problems, however, conventional block splitting approaches can be ineffective, leading to poor convergence. This work addresses these challenges through block-based algebraic multigrid (AMG) preconditioners tailored for multiphysics applications. The proposed preconditioners leverage the inherent coupling structure of the problem to improve solver performance and scalability.

As part of this effort, an interface has been developed within the Trilinos/Teko package to facilitate the integration of block-based AMG preconditioners into existing multiphysics preconditioning frameworks. This interface provides a flexible and extensible mechanism for specifying a wide range of multigrid configurations through the Trilinos/MueLu package. Preliminary results across a range of multiphysics applications demonstrate that the block-based AMG approach significantly outperforms traditional methods in terms of convergence rates and computational cost.  
</td> </tr>

<tr><th>
<abbr> 12:05pm </abbr></th>  <td> <strong>Lunch</strong>
</td> </tr>

<tr><th>
<abbr> 1:35pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/Empire_ElCap_Pawlowski_HPSF_UUR_2026_03.pdf">Scalability and Performance of the Empire Plasma Physics Code on the El Capitan Platform</a> (Roger Pawlowski)  [<a href="https://www.youtube.com/watch?v=qelb2RGq-3Y">video</a>]  <br><br>
Empire is an unstructured mesh finite element particle-in-cell code designed to model plasma physics environments. It is built for performance portability using the Kokkos and Trilinos libraries, enabling efficient execution on a wide range of hardware, from local workstations to the largest supercomputers. In this talk, we will discuss recent efforts to port Empire to the AMD MI300A GPUs on the El Capitan system, currently at number one on the Top 500 List. We will cover the discretization algorithms and solution methods, present strong and weak scaling studies, and provide performance comparisons with modern CPU architectures. Additionally, we will assess the effectiveness of the performance portability abstractions.  
</td> </tr>

<tr><th>
<abbr> 2:00pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/2026_HPSFcon_Xyce_Thornquist.pdf">Enabling scalable predictive circuit simulation using Trilinos</a> (Heidi Thornquist)  [<a href="https://www.youtube.com/watch?v=DYSxyyqeJQQ">video</a>]  <br><br>
Predicting effects on large integrated circuits requires a high-fidelity workflow that enlists a high-performance transistor-level circuit simulator. Even more challenging is achieving scalable predictive simulation that enables designers to quickly iterate and adapt to changing requirements. The Xyce circuit simulator has been developed at Sandia National Labs to meet this challenge and relies on performance portability provided by Trilinos. Xyce delivers unique capabilities to the national security mission, while continuing to motivate research and development of novel computational methods for assembling and solving large-scale systems of differential algebraic equations (DAEs).

This presentation will provide an overview of Xyce, including its architecture and capabilities, highlighting its unique features that facilitate the simulation of large integrated circuits.  The discussion will include an overview of the lessons learned in the recent transition of this simulation code to Tpetra and Kokkos. It will also emphasize the aspects of Trilinos that have enabled Xyce to provide robust and comprehensive simulation capabilities for transient and frequency-domain circuit analysis.
</td> </tr>

<tr><th>
<abbr> 2:25pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/TGU_slides_2026.pdf">Leveraging Trilinos scientific computing library for computational fluid dynamics applications</a> (Marco Delchini)  [<a href="https://www.youtube.com/watch?v=FBHksojTjYI">video</a>]  <br><br>
Oak Ridge National Laboratory has been developing advanced computational fluid dynamics (CFD) solvers built on the Trilinos scientific computing libraries. The objective of this effort is to create robust, scalable CFD solvers for high-performance computing (HPC) platforms that are flexible enough to incorporate new physics for fusion and fission applications. These solvers have been extensively tested against a broad suite of verification and validation problems to assess numerical accuracy. The performance of linear and nonlinear solvers has also been evaluated across a wide range of flow regimes, from low-Mach (incompressible limit) flows to supersonic conditions. This talk will additionally discuss GPU portability enabled by the Kokkos programming model and present performance results on exascale systems such as Frontier and Perlmutter. Numerical results obtained with state-of-the-art discretization and solver techniques will be presented, along with a discussion of current limitations and shortcomings within the Trilinos ecosystem.
</td> </tr>

<tr><th>
<abbr> 2:50pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF2026CommunityTrilinosdeal_II-6.pdf">Trilinos in deal.II</a> (Daniel Arndt)  [<a href="https://www.youtube.com/watch?v=6fvmGSRUKZU">video</a>]  <br><br>
deal.II has been used Trilinos for linear algebra for more than 15 years. This talk will give a brief overview over the history through that time span and highlight issues with moving from Epetra to Tpetra.
</td> </tr>

<tr><th>
<abbr>  3:15pm </abbr></th>  <td> <strong>Coffee Break</strong>
</td> </tr>

<tr><th>
<abbr> 3:40pm </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/HPSF-TUG_2026/HPSF_TUG_Maxwell_Glusa.pdf">Multigrid solvers for Maxwell's equations in Trilinos</a> (Christian Glusa)  [<a href="https://www.youtube.com/watch?v=STg5pFzVpEs">video</a>]  <br><br>
We will give an overview of the the different multigrid solver variants for Maxwell's equations in the MueLu package.
</td> </tr>

<tr><th>
<abbr> 4:05pm </abbr></th>  <td> Trilinos Open Discussion (Curtis Ober)  [<a href="https://www.youtube.com/watch?v=RDlDTSxLgR8">video</a>]  <br><br>
<strong>QR Code and Link</strong> <br>
 <a href="https://docs.google.com/document/d/11_CKxUAjBiHCRy9sLHHC5aVGJ7pNQv8SFkK2cqSwnjw/edit?tab=t.0">
    <img src="pages/community/trilinos_user_meetings/HPSF-TUG_2026/trilinosHPSF-qr.png" alt="QR code for Trilinos Open Discussion" style="width:140px;height:auto;">
  </a> <br><br>
Trilinos developers would like to engage with users on feature requests, complaints, criticisms, etc.  Bring your questions! No technical topic is off-limits (Ok, that is Trilinos related.).  Some possible discussion points are:

* Feature Requests: What feature(s) would you like to see in Trilinos?
* Challenges: What has really tripped you up and you wish someone would change it?
* Success Stories: Do you have a success story to share?
* Pain Points: What are your main pain points?
   - How can we make it easier for the wider Trilinos community to contribute to Trilinos?
   - How can we make Trilinos easier to configure and build for first-time users?
   - Are the current distribution mechanisms (source code & Spack) sufficient? If not, what is missing (e.g., containers, packages)?
* CI Coverage: Are there use cases that the Trilinos CI process currently does not cover? 
* Performance Tracking: Would you find having access to internal Sandia performance tracking data useful?
* Your ideas: Add your own discussion point!

Contribute your discussion points by emailing Curtis Ober ccober@sandia.gov with the subject line: Trilinos Open Discussion Points or contact a Trilinos developer during HPSF.

Topics that were discussed:

* Documentation and AI Readiness

Current documentation is often lacking or missing.
Need to improve AI readiness of documentation, artifacts, and metadata, including skill files.
Potential application of these improvements to build assistance.
Reference: agentskills.io for more details on skill files.

*  Kokkos and Trilinos Compatibility

Concerns were raised about Kokkos and Trilinos potentially getting out of sync.
Spack guarantees compatibility between versions.
Question raised about using an older Kokkos version than the one included in Trilinos.
CMake override exists for the "blessed" Kokkos version to allow older versions, but no guarantees on stability or support.

* Hypre Support in Tpetra Stack

Inquiry about the status of Hypre support within the Tpetra stack.
There is currently no testing for the Hypre interface.

* Trilinos Build Process Improvements

Building Trilinos has become easier recently.
Desire to better capture build environments and dependencies to simplify rebuilds, especially for vendors.
Goal: create shareable and reproducible environments for Trilinos and downstream applications.

* AMD Pull Request (PR) Testing

Nightly builds for AMD will become available soon.
No capacity for full PR testing on AMD currently.
Build-only PR testing for AMD is feasible and should be implemented.

* Xpetra and BlockedCrsMatrix Development

Plan to phase out Xpetra.
Promote BlockedCrsMatrix to a fully supported, standalone component.

* Nightly Builds Monitoring

Question if anyone is currently monitoring nightly builds.
Operational leadership will begin bi-weekly reviews of nightlies and will follow up with package owners as needed.
</td> </tr>

</tbody>
</table>
