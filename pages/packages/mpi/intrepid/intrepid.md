---
title: Intrepid
permalink: intrepid.html
folder: mpi
show_sidebar: true
contact: mperego@sandia.gov, pbboche@sandia.gov, dridzal@sandia.gov, kjpeter@sandia.gov
package: intrepid
doxygen: true
---

![](images/intrepid-balloon.jpg)

Intrepid is still mantained but not developed. For a performance portable implementation see [Intrepid2](intrepid2.html)

Intrepid stands for **IN**teroperable **T**ools for **R**apid d**E**velo**P**ment of compat**I**ble **D**iscretizations.

Intrepid is a library of interoperable tools for compatible discretizations of Partial Differential Equations (PDEs). It is intended primarily for application developers who want to reuse large parts of their existing code frameworks such as I/O, data structures, assembly routines, etc. while gaining access to advanced discretization capabilities provided by Intrepid. In such cases the bulk of the data is owned and managed by the user rather than by Intrepid. To avoid unnecessary and possibly expensive copying of data to and from Intrepid, the expert version of the package comprises of mostly stateless classes operating on user-owned data.Virtually all numerical data required by PDE codes can be represented as a multi-dimensional array of scalar values. For this reason, and to enahnce interoprability, Intrepid classes are templated on generic multi-dimensional arrays. The [Shards](shards.html) package provides an implementation of a multi-dimensional array that can be used for that purpose, or users can write their own multi-dimensional arrays as long as a minimal interface is supported. 

Overview

Intrepid includes the following features:

*   Default finite element basis functions for _H(grad)_, _H(curl)_, _H(div)_ and _L2_ spaces of orders up to 2 on standard cell topologies in 1D, 2D and 3D
*   High-order (up to 10) basis functions for _H(grad)_, _H(curl)_, _H(div)_ and _L2_ spaces on select cell topologies
*   Pullbacks (transformations) from reference coordinate frame of _H(grad)_, _H(curl)_, _H(div)_ and _L2_ fields
*   Pullbacks of gradient, curl and divergence of _H(grad)_, _H(curl)_, _H(div)_ fields
*   Cubature rules of orders up to 20 on most standard 1D, 2D and 3D cell topologies
*   Implementation of multi-diumensional arrays and algebraic operations on them
*   Examples showing solution of basic 2nd order elliptic boundary value problems (Poisson, div-curl, and curl-curl systems) using Intrepid

Supplementary materials

*   [Solving PDEs with Intrepid](https://content.iospress.com/articles/scientific-programming/spr340) by Bochev, Edwards, Kirby, Peterson, Ridzal.

<span style="text-decoration: underline;">**Overview**</span>

Functionality of Intrepid is organized by directory as follows:

*   **Cell**: tools for managing cells (elements) in mesh-based numerical methods for PDEs. This includes methods to query cell topologies of standard cells, construction of custom (usr-defined) cell topologies, mappings from reference to physical coordinates for select cell topologies, inclusion tests, and methods to compute edge tangents and face normals in reference and physical coordinates.
*   **Discretization:** tools for building discretizations of PDEs. This includes definition of **Basis** functions on select cell topologies; definition of **Integration** rules for one, two and three-dimensional reference cells, and a set of **FunctionSpaceTools** for computation of integrals, and transformation (pullback) of basis functions from reference to physical frame.
*   **Shared:** tools for operations on generic multi-dimensional arrays (**ArayTools)**, implementation of Intrepid’s own version of multidimensional array (**FieldContainer)**, collection of methods for vectors and matrices in Euclidean spaces (**RealSpaceTools)**; methods to define various point lattices used by finite element basis functions (**PointTools)**; Intrepid’s version of **[Polylib](http://www2.imperial.ac.uk/ssherw/spectralhp/nektarplusplus/doxygen/pagepolylib.html)** library. Also included in **Shared** are definitions of types, enumerations and global constants (**Types)** used by Intrepid; and various utilities (**Utils)**.

An overview of the basic requirements and features of Intrepid follows. For more details, please consult the documentation!

* * *

**Mutli-dimensional arrays**

The expert version of Intrepid is essentially a collection of mathematical methods operating on user-supplied data. To promote interoperability and easy porting to existing user codes, most of Intrepid classes are templated on generic multi-dimensional arrays. Users can implement their own arrays, use Intrepid’s **FieldContainer**, or use multi-dimensional arrays from [Shards.](shards.html) In either case, a multi-dimensional array class used with Intrepid is expected to support the following minimal interface:

<table width="726" border="1"><caption>**Required multi-dimensional array interface**</caption>

<tbody>

<tr>

<th scope="col" align="left" width="256">int rank()</th>

<th scope="col" align="left" width="454">returns number of dimensions</th>

</tr>

<tr>

<td>int dimension(int k)</td>

<td>returns th k-th dimension</td>

</tr>

<tr>

<td>int size()</td>

<td>returns size, i.e., number of scalar values that can be stored (capacity)</td>

</tr>

<tr>

<td>const Scalar & operator(i,j,…,k)</td>

<td>const accessor using multi-index</td>

</tr>

<tr>

<td>Scalar & operator(i,j,…,k)</td>

<td>non-const accessor using multi-index</td>

</tr>

<tr>

<td>const Scalar & operator[i]</td>

<td>const accessor using the ordinal of the array element</td>

</tr>

<tr>

<td>Scalar& operator[i]</td>

<td>non-const accessor using the ordinal of the array element</td>

</tr>

</tbody>

</table>

Intrepid documentation uses the following notation for indices and dimensions of multi-dimensional arrays:

<table width="729" border="1"><caption>Dimension and index notation used in Intrepid</caption>

<tbody>

<tr>

<th scope="col" width="70">Index</th>

<th scope="col" width="145">Index Type</th>

<th scope="col" width="113">Dimension</th>

<th scope="col" width="373">Description</th>

</tr>

<tr>

<td align="center">p</td>

<td align="center">point</td>

<td align="center">P</td>

<td>number of points</td>

</tr>

<tr>

<td align="center">v or n</td>

<td align="center">vertex or node</td>

<td align="center">V</td>

<td>number of vertices or nodes</td>

</tr>

<tr>

<td align="center">f, l, r</td>

<td align="center">field</td>

<td align="center">F, L, R</td>

<td>number of Fields, Left field and Right fields (in integration)</td>

</tr>

<tr>

<td align="center">c</td>

<td align="center">cell</td>

<td align="center">C</td>

<td>number of cells</td>

</tr>

<tr>

<td align="center">i</td>

<td align="center">field coordinate</td>

<td align="center">D</td>

<td>space dimension</td>

</tr>

<tr>

<td align="center">k</td>

<td align="center">derivative ordinal</td>

<td align="center">K</td>

<td>cardinality of the set of all kth order derivatives</td>

</tr>

</tbody>

</table>

Here are some examples of typical multi-dimensional array formats that are ubiquitous in PDE codes:

<table width="730" border="1"><caption>Typical multi-dimensional arrays in PDE codes</caption>

<tbody>

<tr>

<th scope="col" width="52">Rank</th>

<th scope="col" width="110">Dimensions</th>

<th scope="col" width="111">Multi-index</th>

<th scope="col" width="429">Description</th>

</tr>

<tr>

<td align="center">1</td>

<td>(P)</td>

<td>(p)</td>

<td>Scalar (rank 0) field evaluated at P points</td>

</tr>

<tr>

<td align="center">2</td>

<td>(P,D)</td>

<td>(p,i)</td>

<td>Vector (rank 1) field evaluated at P points</td>

</tr>

<tr>

<td align="center">3</td>

<td>(P,D,D)</td>

<td>(p,i,j)</td>

<td>Tensor (rank 2) field evaluated at P points</td>

</tr>

<tr>

<td align="center">2</td>

<td>(F,P)</td>

<td>(f,p)</td>

<td>F scalar fields evaluated at P points</td>

</tr>

<tr>

<td align="center">3</td>

<td>(F,P,D)</td>

<td>(f,p,i)</td>

<td>F vector fields evaluated at P points</td>

</tr>

<tr>

<td align="center">4</td>

<td>(F,P,D,D)</td>

<td>(f,p,i,j)</td>

<td>F tensor fields evaluated at P points</td>

</tr>

<tr>

<td align="center">3</td>

<td>(F,P,K)</td>

<td>(f,p,k)</td>

<td>kth derivatives of F scalar fields evaluated at P points</td>

</tr>

<tr>

<td align="center">4</td>

<td>(F,P,D,K)</td>

<td>(f,p,i,k)</td>

<td>kth derivatives of F vector fields evaluated at P points</td>

</tr>

<tr>

<td align="center">5</td>

<td>(F,P,D,D,K)</td>

<td>(f,p,i,j,k)</td>

<td>kth deriv. of F tensor fields evaluated at P points</td>

</tr>

<tr>

<td align="center">3</td>

<td>(C,V,D)</td>

<td>(c,v,i)</td>

<td>Vertex coords. of C cells having V vertices each</td>

</tr>

<tr>

<td align="center">3</td>

<td>(C,P,D)</td>

<td>(c,p,i)</td>

<td>Coordinates of C*P points in C cells, P points per cell</td>

</tr>

</tbody>

</table>

* * *

**Basis definitions**

Naming of basis classes and filesfollows a convention that allows to quickly determine the type of basis implemented in a particular class. Each name consists of 4 fields. The following table shows the currently admissible values for each field:

<table width="735" border="1"><caption>Naming of basis classes</caption>

<tbody>

<tr>

<th scope="col" width="164">Field</th>

<th scope="col" width="555">Admissible field values</th>

</tr>

<tr>

<th scope="row">function space</th>

<td>HGRAD, HCURL, HDIV, HVOL</td>

</tr>

<tr>

<th scope="row">cell topology</th>

<td>LINE, QUAD, TRI, HEX, TET, WEDGE</td>

</tr>

<tr>

<th scope="row">discrete space type</th>

<td>C (Complete), I (Incomplete), B (Broken)</td>

</tr>

<tr>

<th scope="row">basis order</th>

<td>0,…,10</td>

</tr>

<tr>

<th scope="row">basis type</th>

<td>FEM (default basis implementation), FEM_JACOBI, FEM_ORTH</td>

</tr>

</tbody>

</table>

For example, Basis_HGRAD_TET_C2_FEM stands for the default implementation of quadratic Lagrangian basis on Tetrahedron cells, and Basis_HCURL_HEX_I1_FEM is the default implementation of the lowest-order Nedelec edge element on Hexahedron.

Basis classes have very simple interface. The input arguments are a multi-dimensional array with the evaluation points and the desired operator type (VALUE, GRAD, CURL, DIV, etc) and the output is a multi-dimensional array with the basis function values. Rank and dimensions of the output array depend on the field rank of the basis functions, which can be 0 (scalar fields), 1 (vector fields), or 2 (tensor fields), the space dimension, and the operator type. The following table summarizes all admissible combinations:

<table width="738" border="1"><caption>Rank and dimensions of the output multi-dimensional array in getValues methods</caption>

<tbody>

<tr>

<th scope="col" width="162">operator/field rank</th>

<th colspan="2" scope="col">rank 0 (scalars)</th>

<th colspan="2" scope="col">rank1 (vectors)</th>

<th colspan="2" scope="col">rank 2 (tensors)</th>

</tr>

<tr>

<th scope="row">spatial dimension</th>

<td align="center" width="88">2D</td>

<td align="center" width="82">3D</td>

<td align="center" width="82">2D</td>

<td align="center" width="85">3D</td>

<td align="center" width="100">2D</td>

<td align="center" width="93">3D</td>

</tr>

<tr>

<th scope="row">VALUE</th>

<td colspan="2" align="center">(F,P)</td>

<td colspan="2" align="center">(F,P,D)</td>

<td colspan="2" align="center">(F,P,D,D)</td>

</tr>

<tr>

<th scope="row">GRAD, D1</th>

<td colspan="2" align="center">(F,P,D)</td>

<td colspan="2" align="center">(F,P,D,D)</td>

<td colspan="2" align="center">(F,P,D,D)</td>

</tr>

<tr>

<th scope="row">CURL</th>

<td align="center">(F,P,D)</td>

<td align="center">undefined</td>

<td align="center">(F,P)</td>

<td align="center">(F,P,D)</td>

<td align="center">(F,P,D)</td>

<td align="center">(F,P,D,D)</td>

</tr>

<tr>

<th scope="row">DIV</th>

<td colspan="2" align="center">undefined</td>

<td colspan="2" align="center">(F,P)</td>

<td colspan="2" align="center">(F,P,D)</td>

</tr>

<tr>

<th scope="row">D1,D2,…,D10</th>

<td colspan="2" align="center">(F,P,K)</td>

<td colspan="2" align="center">(F,P,D,K)</td>

<td colspan="2" align="center">(F,P,D,D,K)</td>

</tr>

</tbody>

</table>
