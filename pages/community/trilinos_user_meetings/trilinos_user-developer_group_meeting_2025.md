---
title: Trilinos User-Developer Group Meeting 2025
permalink: trilinos_user-developer_group_meeting_2025.html
folder: community
---

## Dates

May 7, 2025

## Location

Chicago, Illinois, USA

Contact: [Curtis Ober](mailto:ccober@sandia.gov)

## Agenda


<p style="text-align: center;"><span style="text-decoration: underline;">Wednesday, May 7th</span></p>

<table summary="Timetable">
<tbody>
<tr><th>
<abbr>  1:35 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/UUR_HPSFCon_2025_Trilinos-Overview-v4.pdf">Trilinos Introduction and Overview</a> (Curtis Ober)  [<a href="https://www.youtube.com/watch?v=-I3m_ssdWpU">video</a>]  <br><br>
In this presentation, we will offer a concise introduction and overview of the Trilinos project. Established in 2001, Trilinos is a collaborative initiative focused on developing algorithms and technologies to address complex multi-physics engineering and scientific challenges on high-performance computing (HPC) architectures. This includes a range of capabilities such as linear and nonlinear solvers, optimization techniques, and sensitivity analysis. A key mission of Trilinos is to cultivate a vibrant community of developers and users who contribute to a modular software framework comprised of diverse computational packages. This collaborative environment facilitates resource sharing among library developers, enhancing software compatibility and overall efficiency amortization of costs.
</td> </tr>
<tr><th>
<abbr>  1:55 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/UUR_HPSF_Annual_Meeting_2025_TrilinosCore_Pawlowski1.pdf">An Overview of the Trilinos Core Products</a> (Roger Pawlowski)  [<a href="https://www.youtube.com/watch?v=0jmSebUO9tg">video</a>]  <br><br>
The Trilinos core area includes packages that form the basic building blocks for Trilinos capabilities. This talk will briefly introduce each package and demonstrate how these can be pulled together into an application. We will cover the following packages. The Kokkos performance portability library provides data structures and parallel algorithms that are performant on both CPU and GPU architectures. The Kokkos-Kernels library provides performance portable BLAS and LAPACK routines. The Tpetra library provides MPI-based parallel distributed linear algebra data structures built on Kokkos. The Teuchos library provides utilities for a common look and feel across Trilinos packages, including a reference counted smart pointer, print utilities, timers and a parameter list for user input. The Zoltan library provides parallel distributed load balancing tools. The PyTrilinos package provides python wrappers for Trilinos capabilities. The Thyra package provides abstraction layers for writing linear algebra, linear solvers and nonlinear solvers. The talk will conclude with examples of Trilinos capabilities integrated into the Empire electromagnetic particle-in-cell code.
</td> </tr>
<tr><th>
<abbr>  2:15 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/2025-HPSF-Trilinos-Solvers-final-local.pdf">Why Your Science Application Should Be Using Trilinos Linear Solvers</a> (Jonathan Hu)  [<a href="https://www.youtube.com/watch?v=2VJxbf9WFkw">video</a>]  <br><br>
Trilinos provides a variety of high-performance sparse iterative and direct linear solvers that are portable across CPU and GPU architectures. In this talk, I will provide motivation for why scientists and engineers developing a high-performance application should consider using Trilinos solvers. I'll give an overview of current solver capabilities across a spectrum of science applications, and discuss ongoing research as well as future directions.
</td> </tr>
<tr><th>
<abbr>  2:35 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/HPSF_Trilinos_2025.pdf">Introduction to Trilinos Discretization and Analysis Capabilities</a> (Mauro Perego)  [<a href="https://www.youtube.com/watch?v=CJUgwkMcxqM">video</a>]  <br><br>
In this presentation, we introduce the discretization and analysis tools available in the Trilinos software suite. Using real-world scientific applications as exemplars, we briefly explain how to efficiently implement portable high-order finite element discretizations on unstructured grids for a wide variety of problems, including leveraging time integration schemes for transient problems. Additionally, we describe how to utilize the automatic differentiation and adjoint capabilities for solving nonlinear problems and computing sensitivities. Finally, we present the simulation-constrained optimization capabilities available through the ROL package, highlighting how different Trilinos tools work together to efficiently solve large-scale inference problems.
</td> </tr>
<tr><th>
<abbr>  2:55 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/HPSF_Framework.pdf">Trilinos CI Testing/Contribution Overview</a> (Sam Browne)  [<a href="https://www.youtube.com/watch?v=tNhvFmZrOFE">video</a>]  <br><br>
The Trilinos project is one of many in the scientific software community that employs the concept of Continuous Integration and thusly has a testing process that ensures code functionality and quality as part of its contribution process. This talk is aimed at software developers and researchers interested in enhancing their understanding of Trilinos’ CI practices. We will examine the current processes that contributors must navigate, alongside emerging paradigms shaping the evolution of these practices. Key topics will include the implementation of containerized software testing environments, requirements for running tests on Trilinos compute resources, and objective standards that contributions must meet to guarantee software quality. Attendees will also gain insights into the challenges of providing a highly configurable set of software packages while maintaining user-friendly build processes. By the end of the session, participants will have a clearer understanding of how to effectively contribute to Trilinos, and the direction that DevSecOps efforts in Trilinos are heading in the future.
</td> </tr>
<tr><th>
<abbr>  3:40 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/mayr_hpsf_2025.pdf">The Role of Trilinos in 4C: Advancing Coupled Multiphysics Simulations</a> (Matthias Mayr)  [<a href="https://www.youtube.com/watch?v=L0y-XtxEhyw">video</a>]  <br><br>
The 4C (Comprehensive Computational Community Code) multiphysics simulation framework has been developed to address complex physical phenomena across various scientific and engineering domains. From its inception, 4C has relied on the Trilinos project, an open-source software library for scalable numerical computations, as its backbone for sparse linear algebra and MPI-parallel computing. This integration enhances 4C's computational capabilities and, more importantly, allows the 4C developers to focus on their core research interest: the numerical modeling of multiphysics systems. The synergy between 4C's physics models and Trilinos' numerical solvers facilitates the simulation of coupled multiphysics systems with improved accuracy and performance. Over the years, this synergy has — in parts — evolved to a co-development of both software frameworks. This presentation will delve into the methodologies employed to incorporate Trilinos into the 4C framework, discuss software and development challenges, and showcase application case studies that demonstrate the practical benefits of this integration in simulating complex multiphysics systems such as fluid-solid interactions, contact mechanics or beam-solid interaction.
</td> </tr>
<tr><th>
<abbr>  4:00 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/malachi-hpsf-talk.pdf">Automated Preconditioner Design in the Trilinos/Teko Package</a> (Malachi Phillips)  [<a href="https://www.youtube.com/watch?v=OfvLa9NlgM8">video</a>]  <br><br>
The solution of multiphysics problems depends on the construction of robust preconditioners which significantly influence the convergence rate and computational performance of linear solvers. We employ physics-based block preconditioning strategies from the Trilinos/Teko package developed by Cyr, Shadid, and Tuminaro [SIAM Journal on Scientific Computing, 38(5):S307–S331, 2016]. Teko preconditioner parameter selection, however, remains a difficult task for users. This talk presents an automated approach for the selection of multiphysics preconditioner parameters in the Trilinos/Teko package. We discuss design principles for preconditioners, emphasizing the importance of physics blocking, subblock ordering, and subblock solver choices based on equation types and coupling strengths. Finally, we present an extension to the Trilinos/Teko package in the form of a user-friendly software tool for automatic multiphysics preconditioner design with minimal user input.
</td> </tr>
<tr><th>
<abbr>  4:20 </abbr></th>  <td> <a href="pages/community/trilinos_user_meetings/TUG_2025/HPSF25_Tpetra_Performance.pdf">Keeping Trilinos running performantly everywhere every night</a> (Chris Siefert)  [<a href="https://www.youtube.com/watch?v=q0cXLH78MK8">video</a>]  <br><br>
The Trilinos scientific software library is a key enabling technology for application codes in a variety of physics and engineering areas across the US Department of Energy and beyond. This presentation will "pull back the curtain" and describe the process by which the Trilinos Tpetra/Performance team (a) performs nightly testing across five DOE laboratories, (b) how we identify and remedy performance regressions, (c) how we make the validated build scripts available to Trilinos developers, and (d) how we interface with early users and vendors to ensure that vendor library updates work as advertised.
</td> </tr>
<tr><th>
<abbr>  4:40 </abbr></th>  <td> <a href="https://github.com/trilinos/pytrilinos2_container">PyTrilinos2: Using Trilinos from Python</a> (Christian Glusa)  [<a href="https://www.youtube.com/watch?v=xXYX_xuaaqU">video</a>]  <br><br>
PyTrilinos2 is an auto-generated Python interface for several Trilinos packages. I will explain how additional C++ functionality can be exposed to Python and demonstrate existing solver capabilities.
</td> </tr>
</tbody>
</table>
