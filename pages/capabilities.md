---
title: Trilinos Capabilities
permalink: capabilities.html
show_sidebar: true
sidebar: nav
keywords: Trilinos capabilities, Scientific computing framework, High-performance computing tools, Performance portability, Parallel computing architectures, Distributed-memory systems, Sparse matrix operations, Linear solvers, Nonlinear solvers, Optimization solvers, Eigensolvers, Preconditioners, Multigrid methods, Domain decomposition, Automatic differentiation, Uncertainty quantification, Stochastic methods, Mesh generation, Mesh manipulation, Mesh I/O, Mesh refinement and adaptivity, Mesh quality assessment, Mesh-based data transfer, Finite element assembly, Field evaluation, Meshless discretization, Partitioning and load balancing, Multiphysics simulations, Scalability, Leadership-class systems, Numerical analysis, Engineering applications, Scientific applications, Kokkos, Tpetra, Teuchos, Intrepid2, Panzer, Phalanx, Compadre, Zoltan, Zoltan2, Ifpack2, FROSch, MueLu, Teko, Belos, Amesos2, ShyLU, Adelus, Anasazi, NOX, LOCA, Tempus, ROL, Sacado, Stokhos, Stratimikos, PyTrilinos2, Thyra, Parallel execution, Memory management, Hierarchical parallelism, Graph algorithms, MPI-based communication, Halo exchange, Multidimensional arrays, PDE assembly, Jacobian computation, Sensitivity analysis, Polynomial chaos expansions, Block-structured linear systems, Ensemble-based simulations, GPU-based systems, CUDA, HIP, SYCL, Python wrappers, Unified solver interface, Abstract numerical algorithms, HPC tools
---


Trilinos is a comprehensive software framework for scientific computing, providing a wide range of capabilities for solving complex engineering and scientific problems. Below is a categorized list of Trilinos capabilities with detailed descriptions.

---
{% comment %}Loop over capability areas.{% endcomment -%}
{% for capabilityArea in site.capabilityAreas %}
<h2 id="{{ capabilityArea.label }}">{{ capabilityArea.name }}</h2>
<ul>

{% comment %}Loop over capabilities.{% endcomment -%}
{% for capability in site.capabilities %}
{% comment %}Check if its in the capability area.{% endcomment -%}
{% if capability.area == capabilityArea.label %}
{% comment %}Grab the packages that provide the capability.{% endcomment -%}
{% assign pkgs = capability.providedBy | split: " "  %}
<li>
<strong>{{ capability.name }}</strong> <span style="float:right;"><em>Provided by package{% if pkgs.size > 1 %}s{% endif %}: 
{% for pkg in pkgs %}{% assign p = site.packages | where:"packageSourceDirectory", pkg  | first -%}
<a href="{{ p.link }}">{{ p.name }}</a>
{% comment %}Commas between packages{% endcomment -%}
{% unless forloop.last -%}, {% endunless -%}{% endfor -%}{{ capability.providedByNote -}}
</em></span><br />
{{ capability.content }}
</li>
{% endif %}
{% endfor %}
</ul>
{% endfor %}

---

Trilinos continues to evolve, providing cutting-edge tools for scientific computing while maintaining performance portability across diverse hardware architectures.

## Trilinos Packages

[Trilinos Packages by Area](packages-by-area)


