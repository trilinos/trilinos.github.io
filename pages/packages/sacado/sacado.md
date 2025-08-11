---
title: Sacado
permalink: sacado.html
folder: packages
show_sidebar: true
contact: <a href="mailto:etphipp@sandia.gov">Eric Phipps</a> (<a href="https://github.com/etphipp">@etphipp</a>), <a href="https://github.com/orgs/trilinos/teams/sacado">@sacado</a>
package: sacado
doxygen: true
---

Welcome to the Sacado Home

Automatic Differentiation tools for C++ codes have been developed in SACADO to automatically extract analytic derivative information from codes. This capability is implemented with expression templates that essentially inline code that performs the chain rule. The application code must template a key part of their code (such as the single element fill portion in a finite element code) on the type.
