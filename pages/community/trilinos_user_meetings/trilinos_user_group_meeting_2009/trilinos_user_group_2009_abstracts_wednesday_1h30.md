---
title: Pattern formation in mesoscopic superconductors
permalink: trilinos_user_group_2009_abstracts_wednesday_1h30.html
folder: community
---

    Nico Schlomer
    Wednesday, November 4th
    1:30 - 2:15 pm
      
One of the most successful theories to describe the physical phenomenon of superconductivity is based upon the Ginzburg--Landau equations, a set of two coupled, nonlinear partial differential equations together with mixed-type boundary conditions. Their solution incorporates the density of superconductive flux as well as the induced magnetic field.

For type-II superconductors (as determined by a system parameter kappa with an applied external magnetic field H, the flux density will exhibit spots (vortices) in which there is no superconductivity and the magnetic flux lines penetrate the sample. In the case of infinite domains, those vortices will align on a triangular grid, whereas for small (mesoscopic) superconductors with less then 20 vortices in total, the geometry of the domain imposes constraints on the possible configurations.

This talk will outline the mathematical obstacles one comes across when trying to solve the Ginzburg--Landau equations, and how the Trilinos framework can help to overcome the difficulties. Of particular interest are vortex configurations for mesoscopic superconductors and how they vary as the strength of the outer magnetic field is altered.

The main share of the computational work is taken by LOCA and NOX, respectively, but several other packages of the Trilinos framework are in use as well (e.g., Tpetra, Anasazi, Komplex, Amesos, Ifpack)