---
title: Anasazi Doxygen
permalink: anasazi_doxygen.html
folder: packages
show_sidebar: true
contact: hkthorn@sandia.gov
contact: <a href="mailto:hkthorn@sandia.gov">Heidi Thornquist</a> (<a href="https://github.com/hkthorn">@hkthorn</a>), <a href="https://github.com/orgs/trilinos/teams/anasazi">@anasazi</a>
package: anasazi
doxygen: true
---

Development Doxygen for Anasazi is available [Here](http://trilinos.org/docs/dev/packages/anasazi/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for Anasazi are listed below.  
Trilinos Version: 

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
