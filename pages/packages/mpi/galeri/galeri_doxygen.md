---
title: Galeri Doxygen
permalink: galeri_doxygen.html
folder: mpi
show_sidebar: true
contact: marzio.sala@gmail.com
package: galeri
doxygen: true
---

Development Doxygen for Galeri is available [Here](http://trilinos.org/docs/dev/packages/galeri/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for Galeri are listed below.  
Trilinos Version:

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
