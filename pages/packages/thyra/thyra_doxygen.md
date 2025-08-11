---
title: Thyra Doxygen
permalink: thyra_doxygen.html
folder: packages
show_sidebar: true
contact: <a href="mailto:rabartl@sandia.gov">Ross Bartlett</a> (<a href="https://github.com/bartlettroscoe">@bartlettroscoe</a>), <a href="https://github.com/orgs/trilinos/teams/thyra">@thyra</a>
package: thyra
doxygen: true
---

Development Doxygen for Thyra is available [Here](http://trilinos.org/docs/dev/packages/thyra/doc/html/index.html)  
Links to all available Trilinos release Doxygen collections for Thyra are listed below.  
Trilinos Version:

{% for trilinos_version in site.trilinos_versions %}
[{{ trilinos_version }}]({{ "http://trilinos.org/docs/r" | append: trilinos_version | append: "/packages/" | append: page.package | append: "/doc/html/index.html" }}),{% endfor %}
