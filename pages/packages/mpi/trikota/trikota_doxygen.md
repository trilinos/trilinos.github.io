---
title: TriKota Doxygen
permalink: trikota_doxygen.html
folder: mpi
show_sidebar: true
contact: agsalin@sandia.gov
package: trikota
doxygen: true
---

Development Doxygen for TriKota is available [Here](http://trilinos.org/docs/dev/packages/TriKota/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for TriKota are listed below.  
Trilinos Version: 

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
