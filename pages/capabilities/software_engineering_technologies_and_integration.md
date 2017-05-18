---
title: Software Engineering Technologies and Integration
permalink: software_engineering_technologies.html
folder: capabilities
---

Trilinos Software Engineering Technologies and Integration Capabilities

## Outline

*   [Introduction](#setic_intro_sec)
*   [Numerical Algorithm Interoperability and Vertical Integration](#setic_numerical_algo_sec)
    *   [Abstract Numerical Algorithms (ANAs)](#setic_ana_sub_sec)
    *   [Thyra: Interoperability and vertical integration of ANAs](#setic_thyra_sub_sec)
    *   [Kokkos & Tpetra / Epetra: Linear algebra data structures](#setic_epetra_sub_sec)
*   [General Software Interoperability and Integration](#setic_general_soft_integrate_sec)
    *   [Memory management](#setic_mem_mng_sub_sec)
    *   [User input and configuration control](#setic_user_input_control_sub_sec)
    *   [User introspection](#setic_coord_output_sub_sec)
*   [General Software Quality and Design](#setic_general_soft_design_sec)
*   [Lean/Agile Software Engineering Principles and Practices](#setic_lean_agile_sec)

## Introduction

The Trilinos “Software Engineering Technologies and Integration” capabilities area spans all of Trilinos relating to aspects of scalability, interoperability, integration, and any other critical Trilinos software engineering issue. At the numerical algorithmic level, the Thyra package plays a critical role in defining the standard interfaces to allow the scalable, interoperable, composeable vertical integration of basic linear operators and vectors, preconditioners and linear solvers, nonlinear solvers, bifurcation and stability analysis, transient solvers, optimization, and more. The Kokkos, Tpetra, and Epetra packages provide concrete linear algebra data structures which these abstract numerical algorithms use as input. At a lower level, tools in Teuchos package for memory management (e.g. RCP), configuration control (e.g. ParameterList), and other areas also play a critical role in the composition and interoperability of software. Also included are the various Trilinos “skins” such as PyTrilinos that provide users access to Trilinos capabilities in other programming languages and environments. Finally, principles and practices from the modern Lean & Agile software engineering community are refined and adapted to the numerical computational computing area to support the various missions of Trilinos.

## Numerical Algorithm Interoperability and Vertical Integration

One of the major strategic goals for Trilinos is to make all combinations of numerical algorithms in Trilinos interoperable so that any combination that makes sense mathematically will be well supported. To the greatest extent possible, we try to define solver algorithms and the interoperability of numerical objects at as high of an abstract at level as we can. The highest such level is the so-called “Abstract Numerical Algorithm” (ANA) level. More concrete lower-level algorithms and interoperability is currently defined primarily through Epetra objects.

### Abstract Numerical Algorithms (ANAs)

An ANA is a numerical algorithm that can be expressed abstractly solely in terms of vectors, vector spaces, linear operators, and other abstractions built on top of these without general direct data access or any general assumptions about data locality.

Perhaps the simplest example of a useful ANA is the linear Conjugate Gradient (CG) method for solving linear systems involving a symmetric positive-definite linear operator which can be stated as:

*   Compute ![$r^{(0)} = b - A x^{(0)}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_0.png) for the initial guess ![$x^{(0)}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_1.png)
*   **for**![$i = 1, 2, \ldots$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_2.png)
    *   ![$\rho_{i-1} = \left<r^{(i-1)},r^{(i-1)}\right>$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_3.png)
    *   ![$\beta_{i-1} = \rho_{i-1}/\rho_{i-2}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_4.png) ( ![$\beta_{0} = 0$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_5.png))
    *   ![$p^{(i)} = r^{(i-1)} + \beta_{i-1} p^{(i-1)}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_6.png) ( ![$p^{(1)} = r^{(1)}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_7.png))
    *   ![$q^{(i)} = A p^{(i)}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_8.png)
    *   ![$\gamma_{i} = \left<p^{(i)},q^{(i)}\right>$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_9.png)
    *   ![$\alpha_{i} = \rho_{i-1}/\gamma_{i}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_10.png)
    *   ![$x^{(i)} = x^{(i-1)} + \alpha_{i} p^{(i)}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_11.png)
    *   ![$r^{(i)} = r^{(i-1)} - \alpha_{i} q^{(i)}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_12.png)
    *   check convergence; continue if necessary
*   **end**

The linear CG algorithm above shows the essential features of all ANAs in that only the following types of operations are performed:

*   Linear operator applications (e.g. ![$A x$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_13.png))
*   Vector-vector element-wise reduction and transformation operations (e.g. ![$y = x, y = a x + y$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_14.png))
*   Scalar only operations (e.g. ![$\beta_{i-1} = \rho_{i-1}/\rho_{i-2}$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_4.png))
*   Vector scalar (inner) products (e.g. ![$\gamma = < x, y >$](http://trilinos.org/oldsite/CapabilityWebpages/SoftwareEngineeringTechnogiesAndIntegration/html/form_15.png))

A few important points about ANAs are worth noting:

*   _ANAs can be very mathematically sophisticated._ For example, while CG can be stated in ANA form in only a half a page, the optimization algorithms in the Trilinos package MOOCHO (see below) take many pages of ANA math notation to express.
*   _ANAs can be extremely reusable._ An algorithm implemented as a pure ANA can be run with any underlying model definition, on any computer platform, in any computing configuration (i.e. serial, parallel, shared memory etc.), that exists.
*   _Flexibility is needed to achieve high performance._ Since ANA objects and operations may be implemented in a variety of ways, great flexibility can be exploited in creating very specialized, high-performance, problem specific implementations. Therefore, rather than being an ´abstraction penalty” there is actually an ´abstraction speedup” that can occur. This runs counter to a lot of the anti-object-oriented literature.

The concepts involved with ANAs are independent of Trilinos and of are even independent any particular programming language. In Trilinos, however, that ANA concept is primarily expressed as a set of C++ interfaces in the Trilinos Thyra package.

### Thyra (Interoperability and vertical integration of ANAs)

The [Thyra](http://trilinos.org/packages/thyra/) package contains a set of interfaces and supporting code that defines basic interoperability mechanisms between different types of abstract numerical algorithm (ANA) software. The foundations for all Thyra interfaces are the mathematical concepts of vectors, vector spaces, and linear operators. All other ANA interfaces and support software are built on these fundamental operator/vector interfaces.

The following document describes the basic ideas behind Thyra and provides an overview of the operator/vector interfaces:

*   Bartlett, Roscoe. _Thyra Linear Operators and Vectors: Overview of Interfaces and Support Software for the Development and Interoperability of Abstract Numerical Algorithms._ SAND2007-5984, Sandia National Laboratories, 2007 [[PDF](http://web.ornl.gov/~8vt/ThyraOverview2007.pdf)]

The primary [Thyra](http://trilinos.org/packages/thyra/) ANA interfaces are broadly layered as followed:

*   **[Operator/vector interfaces](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/src/interfaces/operator_vector/ana/fundamental/doc/html/index.html)**
    *   [Thyra::VectorBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1VectorBase.html)
    *   [Thyra::VectorSpaceBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1VectorSpaceBase.html)
    *   [Thyra::LinearOpBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1LinearOpBase.html)
    *   [Thyra::MultiVectorBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1MultiVectorBase.html)
*   **[Operator solve interfaces](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/src/interfaces/operator_solve/ana/fundamental/doc/html/index.html)**
    *   [Thyra::PreconditionerBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1PreconditionerBase.html)
    *   [Thyra::PreconditionerFactoryBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1PreconditionerFactoryBase.html)
    *   [Thyra::LinearOpWithSolveBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1LinearOpWithSolveBase.html)
    *   [Thyra::LinearOpWithSolveFactoryBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1LinearOpWithSolveFactoryBase.html)
*   **[Nonlinear Intefaces](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/src/interfaces/nonlinear/model_evaluator/ana/fundamental/doc/html/index.html)**
    *   [Thyra::ModelEvaluator](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1ModelEvaluator.html)
    *   [Thyra::NonlinearSolverBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1NonlinearSolverBase.html)

A few important points about Thyra interfaces are:

*   All interfaces are expressed as abstract C++ base classes (i.e. object-oriented)
*   All interfaces are templated on a Scalar data type (i.e. generic)
*   All memory management is performed using [Teuchos](http://trilinos.org/docs/dev/packages/teuchos/doc/html/namespaceTeuchos.html) memory management classes involving no raw C++ pointers (see below)

For each of these sets of interfaces, the Thyra package also a set of general adapter and general support software. See the Thyra package documentation for more details.

There are several Trilinos packages that implement ANAs, and/or can accept input as ANA object, and/or can provide implementations of ANA objects for other ANAs to use. The primary packages related to Thyra and ANAs are:

*   **[Thyra](http://trilinos.org/packages/thyra/)**
    *   Adapters
        *   [Thyra/{Epetra, Tpetra} Adapters](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/adapters/epetra/doc/html/index.html):
            *   Utility classes and functions for mapping between Thyra wrapper objects, and Epetra or Tpetra linear algebra objects
        *   [Thyra/EpetraExt Adatpers](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/adapters/epetraext/doc/html/index.html):
            *   [Thyra::EpetraModelEvaluator](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1EpetraModelEvaluator.html): Implements [Thyra::ModelEvaluator](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1ModelEvaluator.html) in terms of an [EpetraExt::ModelEvaluator](http://trilinos.org/docs/dev/packages/epetraext/doc/html/classEpetraExt_1_1ModelEvaluator.html) object
*   **[Stratimikos](http://trilinos.org/packages/stratimikos/)**
    *   User Interfaces:
        *   Stratimikos::DefaultLinearSolverBuilder: Derives from [Thyra::LinearSolverBuilderBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1LinearSolverBuilderBase.html) and provides access PFB and LOWSFB factory objects for preconditioners and linear solvers in Amesos, AztecOO, Belos, Ifpack, and ML
    *   Adapters:
        *   Thyra/Amesos Adapters: Provides implementations of LOWS[F]B using Amesos
        *   Thyra/AztecOO Adapters: Provides implementations of LOWS[F]B using AztecOO
        *   Thyra/Belos Adapters: Provides implementations of LOWS[F]B using Belos
        *   Thyra/Ifpack Adapters: Provides implementations of P[F]B using Ifpack
        *   Thyra/ML Adapters: Provides implementations of P[F]B using ML
*   **[NOX/LOCA](http://trilinos.org/packages/nox-and-loca/)**
    *   Adapters
        *   NOX::Thyra::Group: Implements NOX::Abstract::Group in terms of a [Thyra::ModelEvaluator](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1ModelEvaluator.html) object
        *   Thyra::NOXNonlinearSolver: Implements [Thyra::NonlinearSolverBase](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1NonlinearSolverBase.html) in terms of NOX::Solver::Generic and NOX::StatusTest::Generic objects
*   **[Rythmos](http://trilinos.org/packages/rythmos)**
    *   Implemented directly in terms of Thyra interfaces and objects
*   **[MOOCHO](http://trilinos.org/packages/moocho/)**
    *   [Moocho/Thyra adapters](http://trilinos.org/docs/dev/packages/moocho/thyra/doc/html/index.html):
        *   MoochoPack::MoochoThyraSolver: Allows the solution of optimization problems provided as [Thyra::ModelEvaluator](http://trilinos.sandia.gov/packages/docs/dev/packages/thyra/doc/html/classThyra_1_1ModelEvaluator.html) objects

### Linear algebra data structures

It’s not enough just to have abstract numerical algorithms. Users also need to be able to construct mathematical problems, such as linear systems or eigenvalue problems, using specific data structures. Trilinos has several different packages which provide this functionality at different levels of abstraction.

The Tpetra package provides sparse graphs and matrices, dense vectors, and MPI-parallel data distributions and redistribution. Users may create or modify Tpetra data structures and pass them to abstract numerical algorithms implemented in other packages. Tpetra can exploit both MPI for distributed-memory parallelism, and various shared-memory programming models for thread parallelism. Some users might be more familiar with the older Epetra package, which provides similar functionality.

Tpetra depends on the Kokkos package. Kokkos implements a shared-memory parallel programming model which wraps various back-ends, including CUDA, OpenMP, and Pthreads. Kokkos also provides multidimensional arrays and sparse graphs and matrices. These data structures have a minimal interface suitable for optimized computational kernels within a single MPI process. To exploit all levels of parallelism, including MPI and threads, users may either write to Tpetra directly, or use a combination of Tpetra and Kokkos data structures.

## General Software Interoperability and Integration

In addition to numerical algorithm integration issues, there are more fundamental lower-level software interoperability issues that need to be addressed as well. These issues involve memory management, user configuration control, and coordinated output, and they relate every type of C++ software in Trilinos.

A number of these issues are addressed in the following document:

*   Bartlett, Roscoe. _Thyra Coding and Documentation Guidelines (TCDG)._ Sandia National Laboratories [[PDF](http://www.ornl.gov/~8vt/ThyraCodingGuideLines.pdf)]

Specifically, some of the critical issues for general software integration and interoperability include:

### Memory management

The most fundamental prerequisite for software interoperability is correct and flexible memory management. The [Teuchos](http://trilinos.org/docs/dev/packages/teuchos/doc/html/namespaceTeuchos.html) classes [Teuchos::RCP](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1RCP.html), [Teuchos::Ptr](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1Ptr.html), [Teuchos::ArrayView](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1ArrayView.html), [Teuchos::ArrayRCP](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1ArrayRCP.html), [Teuchos::Array](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1Array.html), [Teuchos::Tuple](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1Tuple.html), and [Teuchos::Workspace](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1Workspace.html) form a complete system of types to safely replace all raw C++ pointers in all higher-level C++ code. Specifically, the reference-counted classes RCP and ArrayRCP provide support for resolving circular references in a very general way (more general that what is provided by similar classes in the boost library in the new C++11 standard).

The following documents provide some more specific information on the use of these classes:

*   Bartlett, Roscoe. _Teuchos::RCP Beginner’s Guide (An Introduction to the Trilinos Smart Reference-Counted Pointer Class for (Almost) Automatic Dynamic Memory Management in C++)_. SAND2004-3268, Sandia National Laboratories, 2007 (Updated December 2007) [[PDF](http://web.ornl.gov/~8vt/RefCountPtrBeginnersGuideSAND.pdf)]
*   Bartlett, Roscoe. _Teuchos C++ Memory Management Classes, Idioms, and Related Topics: The Complete Reference (A Comprehensive Strategy for Safe and Efficient Memory Management in C++ for High Performance Computing)._ SAND2010-2234, Sandia National Laboratories. May 2010 [[PDF](http://web.ornl.gov/~8vt/TeuchosMemoryManagementSAND.pdf)]
*   Bartlett, Roscoe. _Teuchos::RCP: An Introduction to the Trilinos Smart Reference-Counted Pointer Class for (Almost) Automatic Dynamic Memory Management in C++._ SAND2005-4855P, Sandia National Laboratories, 2005 (Updated February 2008) [[PPT](http://web.ornl.gov/~8vt/rabartl_TUG_RCP_Talk.ppt), [PDF](http://web.ornl.gov/~8vt/rabartl_TUG_RCP_Talk.pdf)]
*   Bartlett, Roscoe. _New Teuchos Utility Classes for Safer Memory Management in C++._ SAND2007-7237C, 2007 Trilinos User~s Group Meeting, Sandia National Laboratories, November 2007 [[PPT](http://web.ornl.gov/~8vt/TUG2007_Teuchos_MemoryManagement.ppt), [PDF](http://web.ornl.gov/~8vt/TUG2007_Teuchos_MemoryManagement.pdf)]

### User input and configuration control

Another fundamental issue in software integration and interoperability is in allowing clients to specify configuration parameters in a flexible and general way. The approach adopted must be able to support embedded hierarchical configurations of objects and must be able to fully validate user input.

In Trilinos, the class [Teuchos::ParameterList](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1ParameterList.html) provides the fundamental means to handle and communicate configuration of parameters between different Trilinos (and non-Trilinos) objects. The ParameterList class can accept XML input and can produce XML output and therefore provides a nearly complete solution for configuration control and persistence. The abstract base class [Teuchos::ParameterListAcceptor](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1ParameterListAcceptor.html) defines a standard protocol for objects to accept configuration parameters and provides basic configuration parameter documentation also through ParameterList objects.

### User introspection

Yet another issue to address is how objects interoperate to allow users to introspect the current state and transient behavior of objects in a coordinated and understandable manner. The general issue of user introspection and outputting is addressed with the following [Teuchos](http://trilinos.org/docs/dev/packages/teuchos/doc/html/namespaceTeuchos.html) classes:

*   [Teuchos::FancyOStream](http://trilinos.org/docs/dev/packages/teuchos/doc/html/group__teuchos__outputting__grp.html#ga348df63f6befd76c5cfad4f13414b2c7): A general utility wrapper for any std::ostream object that adds a number of capabilities including multi-processor output control, formatted indentation, and other features
*   [Teuchos::Describable](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1Describable.html): A general base class that allows a client to print out various levels of detail as to the state of an object. Subclasses can override the describe(…) and description() functions to specialize the output to a FancyOStream object.
*   [Teuchos::VerboseObject](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1VerboseObject.html): A general base class that allows a client to register a [Teuchos::FancyOStream](http://trilinos.org/docs/dev/packages/teuchos/doc/html/group__teuchos__outputting__grp.html#ga348df63f6befd76c5cfad4f13414b2c7) object and verbosity level and then get formatted indented output for the dynamic behavior of the object.
*   [Teuchos::TimeMonitor](http://trilinos.org/docs/dev/packages/teuchos/doc/html/classTeuchos_1_1TimeMonitor.html): Utility class for timing important computations and accumulating timing statistics across processors

## General Software Quality and Design

General software design and quality issues are important to any large-scale software effort.

The following document outlines a set of modern C++ coding and Doxygen documentation guidelines for numerical C++ software:

*   Bartlett, Roscoe. _Thyra Coding and Documentation Guidelines (TCDG)._ Sandia National Laboratories [[PDF](http://web.ornl.gov/~8vt/ThyraCodingGuideLines.pdf)]

## Lean/Agile Software Engineering Principles and Practices

At the foundation of any software development effort is a set of underlying software engineering principles. We firmly believe that the Lean/Agile software engineering movement provides an excellent foundation for the development of high-quality, research-drive computation software. Some of the modern literature on Lean/Agile methods is described here.

The following document describes how various Lean/Agile principles can be applied to the Trilinos development and release practices:

*   Bartlett, Roscoe. _Daily Integration and Testing of the Development Versions of Applications and Trilinos: A stronger foundation for enhanced collaboration in application and algorithm research and development._SAND2007-7040, Sandia National Laboratories, October 2007 [[PDF](http://web.ornl.gov/~8vt/AppPlusTrilinosDev2007.pdf)]

Some of the areas where Lean/Agile methods relate to Trilinos development and release issues include:

*   Internal Trilinos development tools principles and practices
    *   Scalability and robustness of build system and test tools
    *   Continuous integration development principles and practices
    *   Release process principles and practices
*   Integration with customer application codes
    *   Coordination of co-development with customer application codes (i.e. daily integration and asynchronous continuous integration)
    *   Coordination of release schedules with customer application codes

