---
title: Galeri
permalink: galeri.html
folder: packages
---

![Galeri Logo](http://trilinos.org/oldsite/packages/galeri/galeri.png)

Galeri: Finite Element and Matrix Generation Package

_Loosely translated, the Greek term “Galeri” simply means **“Gallery”**._

The Trilinos package **Galeri** contains a suite of utilities and classes to generate a variety of (distributed) linear systems. Galeri’s functionalities are very close to that of the MATLAB’s gallery() function.

Several well-know finite element and finite difference matrices can be generated using only a few simple code lines. For a quick overview of Galeri, see [here](http://trilinos.org/oldsite/packages/galeri/slides-overview.html). You can also give a look to the example below, which generates a matrix corresponding to a <tt>nx * ny</tt> Cartesian grid, divided across <tt>mx * my</tt> processors (so that <tt>Comm.NumProc() = mx * my</tt>).:



    int main(int argv, char* argc[])
    {
    #ifdef HAVE_MPI
        MPI_Init(&argv, &argc);
        Epetra_MpiComm Comm(MPI_COMM_WORLD);
    #else
        Epetra_SerialComm Comm;
    #endif

    Teuchos::ParameterList GaleriList;
    GaleriList.set("nx", 10 * Comm.NumProc());
    GaleriList.set("ny", 10);
    
    GaleriList.set("mx", Comm.NumProc());
    GaleriList.set("my", 1);

    Epetra_Map* Map = CreateMap("Cartesian2D", Comm, GaleriList);
    Epetra_RowMatrix* Matrix = CreateCrsMatrix("Laplace2D", Map, GaleriList);
    ...
    #ifdef HAVE_MPI
        MPI_Finalize();
    #endif
    }



And that’s it! (The code snippet above only misses the header files; see the examples in the distribution for a compilable code.) A list of supported matrices is reported [here](http://trilinos.org/docs/dev/packages/galeri/doc/html/gl_GalleryCrsMatrix.html). The supported Epetra_Map’s are instead [here](http://trilinos.org/docs/dev/packages/galeri/doc/html/gl_GalleryMaps.html).

Galeri also contains a nice and simple finite element code, to be used for scalar and vector elliptic-type equations using Galerkin and SUPG discretization techniques, on both 2D and 3D unstructured grids, composed by triangles, quads, tetrahedra and hexahedra.

Galeri’s technical documentation is maintained using Doxygen; click [here](http://trilinos.org/docs/dev/packages/galeri/doc/html/index.html) to access the latest Doxygen documentation.

<span style="text-decoration: underline;">**Overview**</span>  
Understanding, validating, using and developing algorithms and software tools for distributed linear algebra solvers, like Krylov accelerators and preconditioners, requires input data. This data should have three critical properties:

1.  reflect real-life applications to a sufficient extent so that we can use them to predict performance;
2.  be sufficiently simple to be amenable to mathematical analysis;
3.  it is possible to write generators that easily provide instances of these problems.

The goal of the Galeri package is exactly to produce these input data for linear solvers.

As regards real-life applications, we have here selected PDE-type problems. Although Galeri can generate some non-PDE linear systems, surely there is a strong focus on PDE applications. Among them, the Laplace problem is probably the most widely studied application, and a broad range of results are available. For most solvers and preconditioners, often there is a sharp convergence bound that can be used to validate a particular class, or to get a sense of the performances of a new method. A Trilinos package that uses Galeri is the MatrixPortal module of [WebTrilinos](http://trilinos.org/packages/webtrilinos).

Galeri’s Matrix generation capabilities can help to make examples shorter and easier to read, since they can produce challenging linear systems in a few code lines. Therefore, the attention of the example’s reader is not distracted by complicated instructions aiming to build this or that linear system. Since most linear algebra packages of Trilinos use Galeri, users will quickly become familiar with it. Galeri is used in the examples of the [Amesos](amesos.html), [IFPACK](ifpack.html), and [ML](ml.html) packages.

Finally, Galeri is very convenient for software testing. A large variety of problems can be produced, to understand or validate the performances of a given class. Galeri is used in the testing of [Amesos](amesos.html), [IFPACK](ifpack.html), and [ML](ml.html).
