---
title: CXX11
permalink: CXX11.html
folder: about
---

As of Trilinos version 12.0 (perhaps even 11.12), some Trilinos packages, including Kokkos and Tpetra, depend on some C++11 features that require minimum versions of common compilers, including GCC 4.7.2 and Intel 13\. As of 2/4/15, by default, the C++11 flag was set to “ON” for the Trilinos development branch. On 2/5/15, the public repository reflected this change. As a result, as long as your compiler implements C++11, you should not have to set any special flags or CMake options for these packages to build correctly.

Packages that do not depend on C++11, either directly or through other packages, will still be able to build without requiring C++11 features. This includes Teuchos. They must also build with C++11 as well. However, it is VERY IMPORTANT not to mix C++11 flags in your builds. Committing to C++11 in one part of your build requires committing to C++11 in all parts of your build. Otherwise, you will get build or link errors. If you need to disable C++11 in your Trilinos build, set the following CMake option:

`-DTrilinos_ENABLE_CXX11=OFF`

Using this option will cause Trilinos to behave exactly the same as it did prior to turning on C++11 support by default.

### Helpful Links:

[Instructions for installing GCC](install_gcc.html)
[Adding C++11 dependency for Trilinos packages and client codes](add_CXX11.html)