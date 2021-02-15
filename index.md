---
title: Trilinos Home Page
keywords: homepage scientific libraries parallel computing
permalink: index.html
---

### The Trilinos Community
The Trilinos Project is a community of developers, users and
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.user_developer}}">user-developers</a>
focused on collaborative creation of algorithms and enabling technologies within an object-oriented software framework for the solution of large-scale, complex multi-physics engineering and scientific problems on new and emerging high-performance computing (HPC) architectures.

### Trilinos Software
Trilinos is also a collection of reusable scientific software libraries, known in particular for
 <a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.linear_solver}}">linear solvers</a>,
  <a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.nonlinear_solver}}">non-linear solvers</a>,
 <a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.transient_solver}}">transient solvers</a>,
 <a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.optimization_solver}}">optimization solvers</a>, and
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.uq_solver}}">uncertainty quantification (UQ) solvers</a>.

### Parallel Computing Using Trilinos
Most Trilinos algorithms and software are built upon its abilities to construct and solve
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.sparse_problem}}">sparse problems</a>, using
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.sparse_linear_solver}}">sparse linear solvers</a>. These solvers rely on a collection of data structure classes and functions (kernels) for
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.parallel_linear_algebra_kernels}}">parallel linear algebra</a>, especially
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.parallel_sparse_kernels}}">parallel sparse kernels</a>.

### Trilinos Portable Parallel Execution
Trilinos is targeted for all major parallel architectures, including distributed memory using the
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.mpi}}">Message Passing Interface (MPI)</a>,
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.multicore}}">multicore</a> using a variety of common approaches,
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.accelerator}}">accelerators</a> using common and emerging approaches, and
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.vectorization}}">vectorization</a>.

 Trilinos parallel functionality is written on top of libraries that support compile-time polymorphism, such that, as long as a given algorithm and problem size contain enough latent parallelism, the same Trilinos source code can be compiled and execution on any reasonable combination of distributed, multicore, accelerator and vectorizing computing devices.


### Trilinos Packages
Trilinos is organized around fundamental software elements called <a href="#" data-toggle="tooltip" data-original-title="{{site.data.definitions.trilinos_package}}">packages</a>.  The Trilinos package architecture enables simultaneous development of many new capabilities in a federated system.  Each package has its own name and identity within the research community, giving the package team recognition outside of Trilinos itself.

### Trilinos Product Suites
Trilinos contains many packages, organized in [five product suites](product.html):
- Data services: Vectors, matrices, graphs and similar data containers, and related operations.
- Linear and Eigenproblem solvers: For large, distributed systems of equations.
- Nonlinear solvers and analysis tools: Includes basic nonlinear approaches, continuation methods and similar.
- Discretizations: Tools for the discretization of integral and differential equations.
- Framework: Tools for building, testing and integrating Trilinos capabilities.

### Related sites for Trilinos information:
[Trilinos Home Page](https://trilinos.github.io/)
- Software description, downloads, doxygen, etc.
- If you are a new user, this is a great place to start!  (See [also](https://github.com/trilinos/Trilinos#documentation).)

[Trilinos Repository](https://github.com/trilinos/Trilinos)
- Site for the Trilinos git repository to handle open/general issues.
- Developer's wiki.

[Trilinos Developers Site](https://github.com/trilinos/Trilinos/wiki)
- Site for information that Trilinos developers need to know.

[Sandia Trilinos Portal](https://snl-wiki.sandia.gov/display/TRIL/Trilinos+Portal)
- Site containing Sandia specific information related to Trilinos.
- Access limited to Sandia staff.

[Sandia Trilinos Strategy Planning](https://sems-atlassian-srn.sandia.gov/projects/TRILINOS/summary)
- Sandia Jira site for Trilinos strategy epics and tasks.
- Access limited to Sandia staff.

### TUG 2020
[The 2020 Trilinos User-Developer Group (TUG) Meeting](https://trilinos.github.io/trilinos_user-developer_group_meeting_2020.html) was cancelled due to the COVID-19 pandemic.

### TUG 2019
[The 2019 Trilinos User-Developer Group Meeting (TUG)](https://trilinos.github.io/trilinos_user-developer_group_meeting_2019.html) was held in October in Albuquerque.
