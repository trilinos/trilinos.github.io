---
title: Piro
permalink: piro.html
folder: mpi
show_sidebar: true
contact: agsalin@sandia.gov
package: piro
doxygen: true
---

**Welcome to the Piro Home**

Piro is the top-level, unifying package of the Embedded Nonlinear Analysis Capability area. The main purpose of the package is to provide driver classes for the common uses of Trilinos nonlinear analysis tools. These drivers all can be constructed similarly, with a ModelEvaluator and a ParameterList, to make it simple to switch between different types of analysis. 
They also all inherit from the same base classes (reponse-only model evaluators) so that the resulting analysis can in turn driven by non-intrusive analysis routines.
