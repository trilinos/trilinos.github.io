---
title: Amesos Doxygen
permalink: amesos_doxygen.html
folder: mpi
show_sidebar: true
contact: amesos-developers@software.sandia.gov
package: amesos
doxygen: true
---

Development Doxygen for Amesos is available [here](http://trilinos.org/docs/dev/packages/amesos/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for Amesos are listed below.  
Trilinos Version:


{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
