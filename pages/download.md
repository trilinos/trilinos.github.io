---
title: Download
permalink: download.html
show_sidebar: true
sidebar: nav
keywords: Download Trilinos, Trilinos source code, Trilinos containers, HPC package manager, Spack Trilinos, GitHub repository, Trilinos releases, Semantic versioning (SEMVER), BSD license, NTESS copyright, Open-source software, Scientific computing framework, High-performance computing tools, How to install Trilinos, Trilinos installation guide, Trilinos build instructions, Trilinos configure, build, and install, Trilinos special build instructions, CUDA support in Trilinos, nvcc_wrapper, Kokkos, OpenMPI, Trilinos DevSecOps team, Trilinos development tools, Trilinos testing tools, Trilinos automation tools, Trilinos release process, Trilinos repositories, Trilinos legacy packages, Trilinos experimental tools, Trilinos utilities, Trilinos organization repositories, Trilinos containers repository, Trilinos Spack package, Trilinos backward compatibility, Trilinos major releases, Trilinos versioning practices, Trilinos GitHub tags, Trilinos GitHub history, Trilinos GitHub contributions, Trilinos community resources, Trilinos additional resources, Trilinos developer resources, Trilinos pull request testing interface, Trilinos MPI support, Trilinos HPC environments, Trilinos installation scripts, Trilinos CMake configuration, Trilinos CMake flags, Trilinos compilers, Trilinos build environments, Trilinos backward-incompatible changes, Trilinos annual releases, Trilinos on-demand releases, Trilinos scalability, Trilinos interoperability, Trilinos performance optimization, Trilinos integration tools
---

This page outlines the various ways to obtain Trilinos, including source code, containerized environments, and package managers like Spack. Whether you're a developer looking to contribute or a user seeking to integrate Trilinos into your application, you'll find the resources you need here.

---

## Ways to Obtain Trilinos

### Source Code
- **GitHub Repository**:  
  If you plan to develop Trilinos capabilities, you can fork the [Trilinos GitHub repository](https://github.com/trilinos/Trilinos).  
  - Additional information about building and using Trilinos can be found on the [Trilinos Wiki](https://github.com/trilinos/Trilinos/wiki).

### Containers
- Trilinos is available via containers, providing an easy way to set up and run Trilinos without manual installation.  
  - See [Trilinos Containers](https://github.com/trilinos/Trilinos/wiki/Containers) for details.
  - Additional container resources are available at the [Trilinos Containers Repository](https://github.com/trilinos/containers).

### Spack
- Trilinos can be built and installed using [Spack](https://packages.spack.io/package.html?name=trilinos), a package manager for HPC environments. Spack simplifies dependency management and builds Trilinos with optimized configurations for your system.

---

## Releases

To download a specific release, visit the [Trilinos releases page](https://github.com/trilinos/Trilinos/releases). Older versions are available as tags (see [Trilinos Tags](https://github.com/trilinos/Trilinos/tags)).

Trilinos follows **Semantic Versioning (SEMVER)** practices as defined by [semver.org](https://semver.org). This ensures clear communication about backward compatibility and versioning. Major releases signal backward-incompatible changes and are typically planned on an annual basis, though they may occur on demand when necessary.

---

## TPL Version Compatibility

Trilinos relies on many Third Party Libraries (TPLs). Versioning is managed as part of our CMake build system and via Spack packaging.

---

## Other Trilinos Repositories

The Trilinos organization on GitHub hosts several additional repositories that complement the main Trilinos framework. These repositories include legacy packages, experimental tools, and utilities. Explore the [Trilinos organization repositories](https://github.com/orgs/trilinos/repositories) for more information.

---

## DevSecOps Team
- **Description**: Provides streamlined processes and a set of tools for the development of Trilinos packages.
- **Lead**: Sam Browne  [@sebrowne](https://github.com/sebrowne)
- **Responsibilities**:
  - Implements various development, testing, automation tools, and IT infrastructure.
  - Defines and sets development, test, release, update, and support processes.
  - Organizes and maintains the Trilinos release process.
- **Team Members**:
  - Anderson Chauphan  [@achauphan](https://github.com/achauphan)
  - Joe Frye  [@fryeguy52](https://github.com/fryeguy52)
  - Justin LaPre  [@jmlapre](https://github.com/jmlapre)

---

## Special Build Instructions

### Building with CUDA Support

See this page for a list of current compilers (including CUDA): https://github.com/trilinos/Trilinos/wiki/Pull-Request-Testing-Interface

Building Trilinos with CUDA support requires a script called nvcc_wrapper, which is distributed inside Kokkos within Trilinos. Enabling both CUDA and MPI using OpenMPI can be done by setting these environment variables:

    export OMPI_CXX=/<Tpath>/Trilinos/Trilinos/packages/kokkos/config/nvcc_wrapper

where _Tpath_ is the path at which a copy of Trilinos is available.

This variable tells mpicxx to use nvcc_wrapper as the underlying compiler. Note that nvcc_wrapper uses g++ as the default C++ host compiler.

Below is a CMake configure script fragment to then configure Trilinos:

     -DCMAKE_CXX_COMPILER=/<Mpath>/bin/mpicxx \
     -DCMAKE_C_COMPILER=/<Mpath>/bin/mpicc \
     -DCMAKE_Fortran_COMPILER=/<Mpath>/bin/mpif77 \
     -DCMAKE_CXX_FLAGS="-g -lineinfo -Xcudafe \
    --diag_suppress=conversion_function_not_usable -Xcudafe \
    --diag_suppress=cc_clobber_ignored -Xcudafe \
    --diag_suppress=code_is_unreachable" \
     -DTPL_ENABLE_MPI=ON \
     -DTPL_ENABLE_CUDA=ON \
     -DKokkos_ENABLE_CUDA=ON \

where _Mpath_ is the path to the base of the OpenMPI installation to use for the build.

The _CMAKE_CXX_FLAGS_ line adds some nvcc_wrapper command-line arguments to disable some superfluous warnings generated by nvcc.

---

## Additional Resources

- [Trilinos GitHub Repository](https://github.com/trilinos/Trilinos)
- [Trilinos Wiki](https://github.com/trilinos/Trilinos/wiki)
- [Trilinos Releases](https://github.com/trilinos/Trilinos/releases)
- [Trilinos Containers](https://github.com/trilinos/containers)
- [Spack Trilinos Package](https://packages.spack.io/package.html?name=trilinos)

---


