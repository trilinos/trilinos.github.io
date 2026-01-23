---
title: Packages by Area 
permalink: packages-by-area.html
keywords: Area Leads, Core Area, Solvers Area, Discretization and Analysis Area, Linear Systems, Performance Portability, Finite Element Analysis, Preconditioners, Eigen Solvers, Optimization, Mesh Adaptation, Stochastic Methods, Adelus, Amesos2, Anasazi, Belos, Compadre, Galeri, Ifpack2, Intrepid2, Kokkos, Krino, MiniTensor, MueLu, PAMGEN, Panzer, Percept, Phalanx, Piro, PyTrilinos2, ROL, RTop, Rapid Optimization Library, SEACAS, STK, Sacado, Shards, ShyLU, Stokhos, Stratimikos, Teko, Tempus, Teuchos, Thyra, Tpetra, TrilinosCouplings, Xpetra, Zoltan, Zoltan2, Trilinos package descriptions, Trilinos package documentation, Trilinos Doxygen, Trilinos GitHub repository, Trilinos continuous integration (CI), Trilinos continuous deployment (CD), Trilinos package teams, Trilinos package leads, Trilinos modular framework, Trilinos interoperability, Trilinos scalability, Trilinos finite element analysis, Trilinos mesh adaptation, Trilinos stochastic methods, Trilinos optimization, Trilinos linear solvers, Trilinos nonlinear solvers, Trilinos eigen solvers, Trilinos preconditioners, Trilinos time integration, Trilinos transient analysis, Trilinos data transfer, Trilinos DAG-based field evaluation, Trilinos meshless discretization, Trilinos high-order finite element discretizations, Trilinos signed distance fields, Trilinos unstructured meshes, Trilinos parallel services, Trilinos load balancing, Trilinos combinatorial scientific computing, Trilinos smart pointers, Trilinos BLAS and LAPACK wrappers, Trilinos XML parsers, Trilinos vector operations, Trilinos parallel data redistribution, Trilinos abstract numerical algorithms, Trilinos linear algebra libraries, Trilinos unified solver interface, Trilinos automatic differentiation, Trilinos stochastic Galerkin methods, Trilinos uncertainty quantification, Trilinos PDE discretizations, Trilinos multigrid solvers, Trilinos domain decomposition methods, Trilinos distributed computing, Trilinos MPI support, Trilinos CUDA support, Trilinos Kokkos ecosystem, Trilinos performance portability, Trilinos massively parallel computations, Trilinos multi-physics computations, Trilinos interfaces between packages, Trilinos Couplings, Trilinos legacy packages, Trilinos experimental tools, Trilinos utilities
---

## Trilinos Area Leads

In the Trilinos project, **Area Leads** play a vital role in overseeing specific areas or components of the software framework. They are responsible for coordinating the needs and requirements of stakeholders, facilitating requests, and managing inter-package interactions. By actively engaging with the community, Area Leads gather valuable feedback to ensure that the packages effectively meet user needs.

Additionally, they are instrumental in creating and maintaining comprehensive documentation for their packages, as well as providing essential support to users. With significant expertise in their respective fields, Area Leads contribute to the strategic direction of the Trilinos project. Their efforts are crucial for the ongoing development, maintenance, and enhancement of Trilinos packages, ensuring that the software remains both relevant and of high quality.

The Trilinos packages are organized into three main areas: **Core**, **Solvers**, and **Discretization and Analysis**.  Additionally, the <a href="download.html#devsecops-team" title="DevSecOps">**DevSecOps** team</a>  handles the Continuous Integration and Continuous Deployment (CI/CD) processes for Trilinos.

{% for area in site.packageAreas %}
<h2>{{ area.name }}</h2>
<ul>
<li><strong>Description</strong>: {{ area.content }}</li>
<li><strong>Lead</strong>: {{ area.lead }}</li>
</ul>
<table>
  <tr style="background-color: {{ area.color }};">
    <td><strong>Package</strong></td>
    <td><strong>Description</strong></td>
    <td><strong>Documentation</strong></td>
    <td><strong>GitHub</strong></td>
    <td><strong>Team</strong></td>
    <td><strong>Team Lead</strong></td>
  </tr>
{% for pkg in site.packages %}
{% if pkg.area == area.area %}
<tr>
<td><a href="{{ pkg.link }}" title="{{ pkg.name }}">{{ pkg.name }}</a></td>
<td>{{ pkg.description }}</td>
{% if pkg.documentation == 'Doxygen' %}
<td><a href="docs/{{ pkg.packageSourceDirectory }}">{{ pkg.name }} Doxygen</a></td>
{% else %}
<td>{{ pkg.documentation }}</td>
{% endif %}
<td><a href="https://github.com/trilinos/Trilinos/tree/master/packages/{{ pkg.packageSourceDirectory }}">{{ pkg.name }}</a></td>
<td><a href="https://github.com/orgs/trilinos/teams/{{ pkg.githubTeam }}">@{{ pkg.githubTeam }}</a></td>
<td>{{ pkg.lead }}</td>
</tr>
{% endif %}
{% endfor %}
</table>
{% endfor %}
