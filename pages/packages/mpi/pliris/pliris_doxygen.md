---
title: Pliris
permalink: pliris_doxygen.html
folder: mpi
show_sidebar: true
contact: maherou@sandia.gov
package: pliris
doxygen: true
---

Development Doxygen for Pliris is available [Here](http://trilinos.org/docs/dev/packages/pliris/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for Pliris are listed below.  
Trilinos Version: 

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
