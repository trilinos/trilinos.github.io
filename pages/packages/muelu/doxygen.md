---
title: MueLu Doxygen
permalink: muelu_doxygen.html
folder: packages
show_sidebar: true
contact: <a href="mailto:jhu@sandia.gov">Jonathan Hu</a> (<a href="https://github.com/jhux2">@jhux2</a>), <a href="https://github.com/orgs/trilinos/teams/muelu">@muelu</a>
package: muelu
doxygen: true
---

Development Doxygen for MueLu is available [Here](http://trilinos.org/docs/dev/packages/muelu/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for MueLu are listed below.  
Trilinos Version:

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
