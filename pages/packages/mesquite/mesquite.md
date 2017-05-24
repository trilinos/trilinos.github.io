---
title: Mesquite
permalink: mesquite.html
folder: packages
---

<span class="style20">**MESQUITE** is a linkable software library that applies a variety of node-movement algorithms to improve the quality and/or adapt a given mesh. Mesquite uses advanced smoothing and optimization to:</span>

*   Untangle meshes,
*   Provide local size control,
*   Improve angles, orthogonality, and skew,
*   Increase minimum edge-lengths for increased time-steps,
*   Improve mesh smoothness,
*   Perform anisotropic smoothing,
*   Improve surface meshes, adapt to surface curvature,
*   Improve hybrid meshes (including pyramids & wedges),
*   Smooth meshes with hanging nodes,
*   Maintain quality of moving and/or deforming meshes,
*   Perform ALE rezoning,
*   Improve mesh quality on and near boundaries,
*   Improve transitions across internal boundaries,
*   Align meshes with vector fields, and
*   R-adapt meshes to solutions using error estimates.

Mesquite improves surface or volume meshes which are structured, unstructured, hybrid, or non-comformal. A variety of element types are permitted. Mesquite is designed to be as efficient as possible so that large meshes can be improved.

## <span class="style20">**INTRODUCTION**</span>

<span class="style20">Mesh quality is potentially impacted in many stages of the mesh generation process from defeaturing CAD models to postprocessing via a smoothing scheme to mesh adaptivity. At any stage after a mesh is created, its quality can be improved by techniques such as node point movement and topology modification. The simplest algorithm is Laplacian smoothing, which moves each vertex to the geometric center of its neighboring vertices. Although this method is often effective, it does not guarantee mesh improvement and can create inverted elements. Thus, in many situations, more sophisticated smoothing algorithms are needed. In structured meshing, for example, the Winslow smoother is widely used because it guarantees invertibility in two dimensions. Using a local approach to Winslow smoothing is equivalent to using SOR to solve a quasi-linear system of equations. For small problems, this is sufficient, but for large problems, one must turn to iterative solvers involving multigrid, Krylov subspace, or other techniques. In unstructured meshing, effective smoothers with invertibility guarantees often require the use of numerical optimization techniques, and topology modification routines are also highly specialized.</span>

Applications scientists doing computational field simulations generally do not have the time or expertise to write their own sophisticated mesh quality improvement algorithms; _they rightly want to concentrate on the results of their field simulations._This situation creates the need for stand-alone, comprehensive, and widely available mesh quality improvement software similar in spirit to the “solver” packages that encapsulate solver expertise and remove this burden from the analyst. Our plan for creating such a toolkit is funded under the DOE [SciDAC](http://www.scidac.org/) Interoperable Technologies for Advanced Petascale Simulations ([ITAPS](http://www.itaps.org/)) project.

The Mesquite mesh quality improvement toolkit is a software library that can be run stand-alone using provided drivers or called directly from an application code to improve meshes via node-movement techniques. Mesquite development is supported through the [SciDAC](http://www.scidac.org/) Interoperable Technologies for Advanced Petascale Simulations (ITAPS) Center. Mesquite is a platform for testing the new ideas and research products of our MICS mesh improvement research efforts. In addition, Mesquite is the delivery vehicle for the successful mesh optimization algorithms to applications such as those described in the Application section of this web-site. Mesquite is open source software available for [download](http://trilinos.org/oldsite/packages/mesquite/Software.htm). Mesquite architecture is derived directly from the underlying mathematical mesh optimization theory we have developed under MICS funding. For example, at the highest level Mesquite consists of objects and classes such as mesh quality metrics, objective function templates, mesh quality improvement solvers), mesh quality assessors, and Target-matrix calculators. The latter class provides the crucial link between geometric mesh properties such as length, area, angles, and orientation and solution properties such as gradients, curvature, and local error estimates. This flexible design is ideal for rapid prototyping and testing our research ideas through the ability to quickly swap in and out various metrics, templates, optimization solvers, and target calculators. In addition, Mesquite provides the capability to loop over mesh vertices or sets of vertices; this is useful in testing various solution strategies. Mesquite is the ideal platform for doing this kind of research because

*   the flexible architecture makes it easy to try and compare different algorithms,
*   it provides access to a wide variety of test meshes and applications,
*   the existing framework removes the need to develop basic mesh optimization capabilities in order to test a particular idea, and
*   it allows us to deliver results to our existing user base and increase dissemination of the work.

## **The MESQUITE Team**

Lori Freitag-Diachin (PI)  
Lawrence Livermore National Laboratory  
[**diachin2@llnl.gov**](mailto:diachin2@llnl.gov)  
[**http://www.llnl.gov/CASC/people/diachin**](http://www.llnl.gov/CASC/people/diachin)

Patrick Knupp (retired)  
Sandia National Laboratories  
**[Center for Computing Research](http://www.cs.sandia.gov/)**

**Jason Kraftcheck  
University of Wisconsin**
