---
title: Getting started
permalink: getting_started.html
---

Beginning to use Trilinos can be a daunting task, as it is a large and complex software suite. This page walks you through the various resources available to new users. First, you’ll want to acquaint yourself with Trilinos at a high level. Next, learn where particular functionality resides. Then, you’ll be ready to begin configuring and installing Trilinos on your own machine. Finally, dig in to the details of actually putting Trilinos to work on your problems.

Note that there may be overlap between some documents.

### What Trilinos is About

- [About page](about.html)
- [Trilinos Overview (.pdf)](pdfs/TrilinosOverview.pdf) A broad overview of Trilinos.  Legacy document but still instructive.
- [Events](events.html) Recent Trilinos User-Developer Group meeting pages contain links to recorded presentations covering introductory and advanced topics
- [An Overview of the Trilinos Project (.pdf)](pdfs/TrilinosACMTOMS2004.pdf) The original Trilinos article from ACM Transactions on Mathematical Software, Vol. V, No. N, December 2004, Pages 1-27

- [Packages page](packages.html) Links to individual package site

### Configuring, Building, and Installing Trilinos

- [Trilinos CMake Reference](http://trilinos.org/docs/files/TrilinosBuildReference.pdf)) Instructions for building Trilinos 10.0 and later.
- [Third-party library (TPL) version compatibility](tpl_version_compatibility.html)

### Working With Trilinos

- [Trilinos Hands-on Tutorial](https://github.com/trilinos/Trilinos_tutorial/wiki/TrilinosHandsOnTutorial)  Introductory and example material used for numerous live hands-on tutorials
- [FIND_PACKAGE(Trilinos) Documentation](pdfs/Finding_Trilinos.txt)  Instructions for building your Trilinos 10.0 and later compatible CMake-aware software project. The FIND_PACKAGE capability makes it easy to build against Trilinos, including linking against the correct list of libraries. In Trilinos 10.6 and later, a small functional example to be used as a template for applications wanting to use FIND_PACKAGE(Trilinos) can be found in the source code under demos/buildAgainstTrilinos.
- [Makefile.export Documentation](pdfs/Export_Makefile.txt)  The Makefile.export system, avaialble in Trilinos 10.4 and later, provides an easy way to build against Trilinos for code that is compiled using simple Makefiles.
- [Documentation page](documentation.html)  A list of Trilinos publications and other documentation
