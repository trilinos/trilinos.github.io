---
title: ForTrilinos
permalink: fortrilinos.html
folder: packages
show_sidebar: true
contact: william@sandia.gov
package: ForTrilinos
doxygen: true
redirect_to:
  - https://trilinos.github.io/ForTrilinos/  
---

**Welcome to the ForTrilinos Home**

ForTrilinos provides object-oriented Fortran interfaces to Trilinos C++ packages. Please use the menu bar on the left of this page to learn more about ForTrilinos.

<span style="text-decoration: underline;">**Overview**</span>

The ForTrilinos project emphasizes portability, robustness, and scalable development. Portability results from standards conformance. In particular, ForTrilinos exploits the C interoperability features of the Fortran 2003 standard to interact with other Trilinos packages through the CTrilinos package. This approach provides platform-independent type safety and procedure name resolution using language constructs supported by the recent releases of all ten Fortran compilers [surveyed](http://portal.acm.org/ft_gateway.cfm?id=1961365&type=pdf&CFID=21623089&CFTOKEN=87671454 "Chivers and Sleightholme survey"). Robustness results in part from a Fortran implementation of runtime assertions and in part by embedding an automated memory management architecture into each ForTrilinos object. Scalable development results from automating the most labor-intensive portions of the interface development effort.

ForTrilinos currently wraps portions of [Epetra](epetra.html "Trilinos Epetra package"), [Pliris](pliris.html "Trilinos Pliris home"), and [AztecOO](aztecoo.html "Trilinos AztecOO home"). The development of ForTrilinos is primarily user-driven, so new interfaces are developed at the request of Trilinos users.
