---
title: Percept
permalink: percept.html
folder: packages
show_sidebar: true
contact: <a href="mailto:bcarnes@sandia.gov">Brian Carnes</a> (<a href="https://github.com/bricar">@bricar</a>), <a href="https://github.com/orgs/trilinos/teams/percept">@percept</a>
package: percept
doxygen: false
---

Percept is a collection of tools to enable solution verification. The main emphasis is on spatial mesh modification,
including capabilities for uniform and local mesh adaptation. Additionally, we provide separate tools for transfer of field data,
verification of modal eigenvalue problems, and scripts for solution verification studies. Advanced capabilities for
refinement include support for conformal meshes using transition element elements, conversion to all-tet meshes,
enrichment to higher order elements, and special boundary layer refinement on hybrid tet/wedge meshes.

Percept capabilities are provided through an MPI-aware library that can be built as part of Trilinos.
The most commonly used capability is uniform mesh refinement (UMR).
For a given mesh called <code>input.g</code> in the <code>ExodusII</code> format, the simplest command to generate a uniformly refined mesh
called <code>output.g</code> would be

    mesh_adapt --refine=DEFAULT --input_mesh=input.g --output_mesh=output.g

This command runs the UMR in serial and uses the default options when possible.
