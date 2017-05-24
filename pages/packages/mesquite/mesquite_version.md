---
title: Version Releases & Capabilities 
permalink: mesquite_version_releases.html
folder: packages
---

**Announcing Mesquite 2.1.0**

Date: October 5, 2009

New Features:

*   CMake-based build system and portability fixes restoring the ability to compile Mesquite on MS Windows.
*   Many new target metrics for volume elements
*   Target metric performance improvements
*   Edge-length and area/volume metrics for use in quality assessment
*   QualityAssessor accumulates statistics for only free elements (elements with at least one free vertex) by default. New option to revert to old behavior.
*   New command-line utilities:
    *   msqshape : run ShapeImprovementWrapper for a VTK file
    *   msqquality : run QualityAssessor with a few common metrics for a VTK file and print results.
*   New wrappers:
    *   ViscousCFDTetShapeWrapper
    *   PaverMinEdgeLengthWrapper
*   Experimental support for using iMeshP API with parallel mesquite

**Version 2.0**  
Date: April 17, 2009

A substantial re-design of much of the core Mesquite code has been done over the last several years. This is the first official release of the new core Mesquite implementation. In addition to the re-designed core code, this release includes the several new features and many minor improvements listed below

New Features and Improvements:

*   Core code redesigned to support planned future improvements and to eliminate incompatibilities between various mesquite components
*   Conversion to GNU automake/libtool build system
*   Increases the number of supported platforms
*   Option to compile as a shared library
*   “make install” and other standard make targets work correctly
*   Two new solvers: TrustRegion, QuasiNewton
*   Support for the latest ITAPS C APIs
*   Most solvers support a new block coordinate descent optimization scheme
*   New ArrayMesh class allows Mesquite to operate directly on array-based application mesh data. This will hopefully help to minimize the amount of glue code required to interface with FORTRAN code
*   Significant performance improvements for SteepestDescent solver
*   New mechanism to specify fixed vertices by dimension of associated geometric domain
*   Elimination of performance issues when using ITAPS APIs
*   API simplification
*   Many previous incompatible or nonsensical constructs now result in compile-time errors
*   Many cases where the application had to request what should have been an obvious behavior have been removed. For example: analytical derivative calculations are now used whenever available higher-order nodes are automatically adjusted to logical location as dictated by the default linear shape function for the element.
*   Many minor improvements, bug fixes, etc.

Known Issues:

*   Building using Microsoft Visual C++ is no longer supported
*   Beta “Distance From Target” metrics have been removed

Additional Notes :

*   This information is included in the ANNOUNCE file within within the source distribution
*   Information about updating applications for Mesquite API changes is included in the doc/Updating_From_1.x.txt file in the source distribution.

**Version 1.1**  
Date: October 12, 2005

New Capabilities:

*   Support for Wedge elements
*   Further support for Pyramid elements (more metrics)
*   Windows and Mac build

**Version 1.0**  
Date: July 31, 2005

New Capabilities:

*   ITAPS interface client suppport
*   Support for Pyramid elements
*   Improved Surface smoothing
*   Run-time performance improvements

**Version 0.9**  
Date: June 20, 2004

New Capabilities:

*   Preliminary target-matrix capability

**Version 0.8**  
Date: March 15, 2003

New Capabilities:

*   Inverse Mean Ratio
*   Global Feasible Newton Solver
*   Global Patch Smoothing
*   Simplified geometry engine
*   Active Set Solver (L-infinity)
*   Smooths meshes with fixed flags
*   New Optimization Termination Criteria

**Version 0.5**  
Date: March 20, 2002

Capabilities:

*   Conjugate Gradient Node Mover
*   Laplacian Smoother
*   Shape Improvement
*   Mesh Untangling
*   Local Patch Smoothing
*   Tri, Tet, Quad, or Hex meshes
*   Mixed Tri and Quad Meshes
*   Fixed boundary nodes
*   Quality Assessment
*   Planar and Volume meshes