---
title: The MESQUITE Vision
permalink: mesquite_vision.html
folder: packages
---

Many successful improvement algorithms have been developed in the context of particular data structures or software packages and are thus not widely available to mesh generation developers or application scientists. Currently, no stand-alone, portable package for mesh improvement exists that encompasses many of the latest, most sophisticated algorithms for robust performance, that can be used for any element type and order, that can be referenced to both isotropic and anisotropic ideal elements, and that provides both patch-based and nonpatch-based objective functions. The package that comes closest to these goals is [Opt-MS](http://www.osti.gov/estsc/details.jsp?rcdid=3500) by Lori Frietag. It is stand-alone and portable and uses some optimization algorithms for homogeneous simplicial meshes. However, it provides smoothing algorithms only for isotropic simplicial elements on local patches.

The MESQUITE software package will address all of the issues mentioned above and will provide a freely available mesh quality improvement toolkit that meets the following design goals.

**Versatile and Comprehensive.**  
MESQUITE will work on structured, unstructured, and hybrid meshes for both surface and volume meshes. The design will permit improvements to meshes composed of tetrahedral, hexahedral, prismatic, pyramidal, and even polyhedral elements. MESQUITE will incorporate the best quality improvement methods from both continuum variational methods and from discrete objective functions composed of mesh quality metrics. Node movement strategies will include both local patch based iteration schemes and nonpatch based global objective functions. MESQUITE will be applicable to both adaptive and nonadaptive meshing and to both low- and high-order discretization schemes. MESQUITE will, however, strive to include only the minimal number of mature algorithms needed to cover as many contexts as possible. In addition, it will incorporate the research algorithms enabled by its development.

**Effective.**  
MESQUITE will use state-of-the-art algorithms and metrics to guarantee improvement in mesh quality. Because the definition of mesh quality is application specific, we will provide referenced quality metrics that allow the user to untangle meshes; improve mesh smoothness, element size, shape, and orientation; and control element anisotropy. The software will be customizable, enabling users to insert their own quality metric and/or objective functions, and mechanisms for easily creating a combined approach that uses one or more improvement algorithms.

**Interoperable.**  
To ensure that MESQUITE will be interoperable with a large number of mesh generation packages and simulation codes, we will use the common TSTTM interface for mesh query developed by the ITAPS center. These interfaces will provide uniform access to mesh geometry and topology and will be implemented by all ITAPS center software. We are working with the interface design team to ensure efficient information access through strategies such as information caching and agglomeration.

**Robust.**  
MESQUITE will guarantee that there will be no degradation to mesh quality as measured by the objective function and metric used for improvement. We will use sound software engineering principles and robust numerical algorithms. A comprehensive suite of test problems will be developed to verify the correct execution of the code. Extensive error checking will be employed, and mechanisms for reporting failure problems will be provided.

**Efficient.**  
We will make effective use of high-performance architectures and languages. In particular, we will design the outer layers of MESQUITE using object-oriented design in C++ but will implement the inner kernels using easily optimizable coding styles (arrays, inlined functions, etc.). To ensure efficient use of computationally intensive optimization algorithms, we will employ a strategic use of inexpensive smoothers, such as Laplacian smoothing, as “preconditioners” for the more expensive optimization techniques and loose stopping tolerances that attain sufficient improvement in mesh quality.<span class="feature style23">  
  
**Automatic and User Friendly.**  
We will provide a number of mechanisms that lower the expertise barrier for using MESQUITE. In the simplest usage scenario, a ITAPS mesh pointer is passed to MESQUITE and improved using a default set of metrics and strategies determined by the mesh type. If desired, the user can guide the mesh improvement process by setting a few parameter values indicating preferred metrics and strategies from a list of provided functionalities. Once these parameters are defined, MESQUITE will proceed to optimize the mesh without further input from the user. Additional interfaces will be provided for those who desire advanced functionalities, user defined metrics or objective functions, or more control over the optimization process. Mesh quality assessment and statistics will be provided to help the user determine whether the mesh needs to be improved and to evaluate the effectiveness of MESQUITE.