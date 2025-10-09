---
title: Optika Doxygen
permalink: optika_doxygen.html
folder: archive
show_sidebar: true
contact: klnusbaum@gmail.com
package: optika
doxygen: true
---

Development Doxygen for Optika is available [Here](docs//optika/index.html)  
Links to all available Trilinos release Doxygen collections for Optika are listed below.  
Trilinos Version:

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/index.html" }}),{% endfor %}
