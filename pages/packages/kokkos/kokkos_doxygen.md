---
title: Kokkos Doxygen
permalink: kokkos_doxygen.html
folder: packages
show_sidebar: true
contact: <a href="mailto:crtrott@sandia.gov">Christian Trott</a> (<a href="https://github.com/crtrott">@crtrott</a>), <a href="https://github.com/orgs/trilinos/teams/kokkos">@kokkos</a>
package: kokkos
doxygen: true
---

Development Doxygen for Kokkos is available [Here](http://trilinos.org/docs/dev/packages/kokkos/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for Kokkos are listed below.  
Trilinos Version:

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
