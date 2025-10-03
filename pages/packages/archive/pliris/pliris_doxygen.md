---
title: Pliris
permalink: pliris_doxygen.html
folder: archive
show_sidebar: true
contact: maherou@sandia.gov
package: pliris
doxygen: true
---

Development Doxygen for Pliris is available [Here](docs/dev//pliris/index.html)  
Links to all available Trilinos release Doxygen collections for Pliris are listed below.  
Trilinos Version: 

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/index.html" }}),{% endfor %}
