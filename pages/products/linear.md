---
title: Linear Solver
permalink: linear_solver.html
folder: products
---

## <span style="text-decoration: underline;">Overview</span>

### <span style="text-decoration: underline;">Introduction</span>

Trilinos provides a wide-variety of solution methods for linear and eigen systems. The purpose of this page is to give an overview of the capabilities in the areas of iterative and [direct](#_Direct_linear_solvers) solvers, [preconditioners](#_Preconditioners), [high-level interfaces](#Stratimikos), and [eigen-solvers](#Anasazi). Unless otherwise noted, all packages have been publicly released.

### <span style="text-decoration: underline;">Getting Started</span>

You should first decide whether you want to use the Epetra or Tpetra sparse linear algebra library. This decision will determine which solvers and preconditioners you can use, as not all solvers are compatible with both. See the [compatibility chart](#_Compatibility_with_Epetra) in the next section for details.

Epetra uses integer ordinal types and double scalar types. This means that it currently can run problems with at most 2<sup>31</sup>-1 (~2.1 billion) degrees of freedom (DOFs). (An upgrade to Epetra is underway, however, that will remove this index limitation.) Tpetra is templated on the ordinal type, scalar type, and node type. Tpetra allows creation of problems with any number of DOFs, problems other than of type double, optimized computations on a variety of many-core architectures (including GPUs) through Kokkos, and mixing of MPI and threading.

Once you have chosen the sparse linear algebra library, you can focus on solver/preconditioner libraries.

### <span style="text-decoration: underline;">Quick Guide to Trilinos</span> <span style="text-decoration: underline;">Preconditioners</span><span style="text-decoration: underline;">/Solvers</span>

The following table gives a one-line description of available Trilinos linear and eigensolver packages and their compatibility with Epetra and Tpetra.

<table border="1" cellspacing="0" cellpadding="0">

<tbody>

<tr>

<td rowspan="2" width="40%"><center> <strong>Description</strong> </center></td>

<td rowspan="2" width="20%"><center> <strong>Package</strong> </center></td>

<td colspan="2" width="40%">

<center><strong>Compatible with</strong></center>

</td>

</tr>

<tr>

<td width="20%">

<strong>Epetra</strong>

</td>

<td width="20%">

<strong>Tpetra</strong>

</td>

</tr>

<tr>

<td rowspan="2" width="261">Krylov methods</td>

<td valign="top" width="99"><a href="#-aztecoo-preconditioners-and-krylov-subspace-methods">AztecOO</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td valign="top" width="99"><a href="#-belos-classical-and-block-krylov-subspace-methods">Belos</a></td>

<td width="68">

Y

</td>

<td width="68">

Y

</td>

</tr>

<tr>

<td rowspan="3" width="261">Direct solvers</td>

<td valign="top" width="99"><a href="#-amesos-direct-sparse-linear-solver-interface">Amesos</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td valign="top" width="99"><a href="#-amesos2-direct-sparse-linear-solver-interface">Amesos2</a></td>

<td width="68">

Y

</td>

<td width="68">

Y

</td>

</tr>

<tr>

<td valign="top" width="99"><a href="#-pliris-direct-dense-linear-solver">Pliris</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td rowspan="2" width="261">Incomplete factorizations, SOR methods, Additive Schwarz</td>

<td valign="top" width="99"><a href="#-ifpack-point-preconditioning-incomplete-factorizations-and-classical-domain-decomposition">Ifpack</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td valign="top" width="99"><a href="#-ifpack2-point-preconditioning-incomplete-factorizations">Ifpack2</a></td>

<td width="68"></td>

<td width="68">

Y

</td>

</tr>

<tr>

<td rowspan="2" width="261">Algebraic multigrid</td>

<td valign="top" width="99"><a href="#-ml-smoothed-aggregation-algebraic-multigrid">ML</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td valign="top" width="99"><a href="#-muelu-multigrid-framework">MueLu</a></td>

<td width="68">

Y

</td>

<td width="68">

Y

</td>

</tr>

<tr>

<td valign="top" width="261">Block preconditioning framework</td>

<td valign="top" width="99"><a href="#-teko-block-preconditioning-framework">Teko</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td valign="top" width="261">Eigen methods</td>

<td valign="top" width="99"><a href="#-anasazi-parallel-eigen-solvers">Anasazi</a></td>

<td width="68">

Y

</td>

<td width="68">

Y

</td>

</tr>

<tr>

<td valign="top" width="261">Domian Decomposition Preconditioners and Subdomain solvers </td>

<td valign="top" width="99"><a href="#-shylu-hybrid-iterativedirect-schur-complement-solver">ShyLU</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td valign="top" width="261">Equivalent real forms</td>

<td valign="top" width="99"><a href="#-komplex-complex-valued-system-solver">Komplex</a></td>

<td width="68">

Y

</td>

<td width="68"></td>

</tr>

<tr>

<td valign="top" width="261">Solver manager</td>

<td valign="top" width="99"><a href="#--stratimikos-high-level-linear-solver-interface">Stratimikos</a></td>

<td width="68">

Y

</td>

<td width="68">

Y

</td>

</tr>

</tbody>

</table>

<a name="Linear_solver_interfaces"></a> 
## <span style="text-decoration: underline;">Linear solver interfaces</span>

### **Stratimikos**: High level linear solver interface

Point-of-contact: Roscoe Bartlett (bartlettra@ornl.gov)  
[http://trilinos.sandia.gov/packages/stratimikos](stratimikos.html)

Stratimikos contains a unified set of wrappers to linear solver and preconditioner capabilities in Trilinos. Stratimikos essentially consists of the single class DefaultLinearSolverBuilder. This class takes as input a (nested) parameter list that contains options for the desired solvers and preconditioners.

Stratimikos has adapters for AztecOO, Belos, Amesos, Ifpack, and ML.

Stratimikos is compatible with Epetra and Tpetra.

* * *

## <span style="text-decoration: underline;">Iterative linear and eigen-solvers</span>

### **AztecOO**: Preconditioners and Krylov subspace methods

Point-of-contact: Mike Heroux (maherou@sandia.gov)  
[https://trilinos.github.io/aztecoo.html](aztecoo.html)

AztecOO includes a number of Krylov iterative methods such as conjugate gradient (CG), generalized minimum residual (GMRES) and stabilized biconjugate gradient (BiCGSTAB) to solve systems of equations. AztecOO may use a variety of internally implemented preconditioners, such as SOR, polynomial, domain decomposition, and incomplete factorization preconditioning, as well as preconditioners provided by other Trilinos packages. AztecOO also fully contains the C-language Aztec linear solver package, so any application that is using Aztec can use the AztecOO library in place of Aztec. Note that only bug fixes are being applied to AztecOO. Active algorithm development is taking place in [Belos](http://trilinos.org/oldsite/CapabilityWebpages/LinearEigenCapabilities/overview.html#Belos).

AztecOO is compatible with Epetra only.

### **Belos**: Classical and block Krylov subspace methods

Points-of-contact: Heidi Thornquist (hkthorn@sandia.gov) and Mike Parks (mlparks@sandia.gov)  
[https://trilinos.github.io/belos.html](belos.html)

Belos provides next-generation iterative linear solvers and a powerful linear solver developer framework. This framework includes the following abstract interfaces and implementations:

*   Abstract interfaces to linear algebra using traits mechanisms. This allows the user to leverage any existing investment in their description of matrices and vectors. The provided concrete linear algebra adapters enable Belos to be used anywhere Epetra and Thyra are employed for linear algebra services.

*   Abstract interfaces to orthogonalization; implementations of iterated classical Gram-Schmidt (ICGS), classical Gram-Schmidt with a DGKS correction step, and iterated modified Gram-Schmidt (IMGS) are included.

*   Abstract interfaces to iteration kernels; implementations of conjugate gradient (CG), block CG, block GMRES, pseudo-block GMRES, block flexible GMRES, and GCRO-DR iterations are included.

*   Powerful solver managers are provided for solving a linear system using CG or block CG, GMRES or block GMRES with restarting, pseudo-block GMRES for performing single-vector GMRES simultaneously on multiple right-hand sides, and a single-vector recycled Krylov method (GCRO-DR).

*   Basic linear problem class is provided for the user to define an unpreconditioned or preconditioned (left, right, two-sided) linear system for Belos to solve.

Belos is compatible with Epetra and Tpetra.

### **Anasazi**: parallel eigen-solvers

Point-of-contact: Heidi Thornquist (hkthorn@sandia.gov)  
[https://trilinos.github.io/anasazi.html](anasazi.html)

Anasazi is an extensible and interoperable framework for large-scale eigenvalue algorithms. The motivation for this framework is to provide a generic interface to a collection of algorithms for solving large-scale eigenvalue problems. Anasazi is interoperable because both the matrix and vectors (defining the eigenspace) are considered to be opaque objects—only knowledge of the matrix and vectors via elementary operations is necessary. An implementation of Anasazi is accomplished via the use of interfaces. Current interfaces available include Epetra and so any libraries that understand Epetra matrices and vectors (such as AztecOO) may also be used in conjunction with Anasazi.

One of the goals of Anasazi is to allow the user the flexibility to specify the data representation for the matrix and vectors and so leverage any existing software investment. The algorithms that are currently available through Anasazi are block Krylov-Schur, block Davidson, and locally-optimal block preconditioned conjugate gradient (LOBPCG) method.

Anasazi is compatible with Epetra and Tpetra.

### **Komplex**: Complex-valued system solver

Points-of-contact: Mike Heroux (maherou@sandia.gov) and David Day (dmday@sandia.gov)  
[https://trilinos.github.io/komplex.html](komplex.html)

KOMPLEX is an add-on module to AZTEC that allows users to solve complex-valued linear systems. KOMPLEX solves a complex-valued linear system Ax=b by solving an equivalent real-valued system of twice the dimension.

<div>

<div align="center">

* * *

</div>

</div>

<a name="_Direct_linear_solvers"></a>

## <span style="text-decoration: underline;">Direct linear solvers</span>

### **Amesos**: direct sparse linear solver interface

Point-of-contact: Siva Rajamanickam (srajama@sandia.gov)  
[https://trilinos.github.io/amesos.html](amesos.html)

Amesos is a set of C++ interfaces to serial and parallel sparse direct solvers. Amesos contains two nice sparse solvers: KLU and Paraklete. KLU is serial, while Paraklete (distributed with Trilinos 7.0 or higher) is a parallel solver. Amesos also offers an interface to LAPACK, and several other well-know solvers available on the web.

The main idea of Amesos is to give a high-level view of direct solvers, as composed by four main phases:

1) specification of parameters  
2) initialization of the solver, using matrix sparsity only  
3) computation of the factors  
4) solution of the linear system

Amesos insulates the user from all the low-level details typical of direct solvers, like the matrix format, data distribution for the matrix, the solution and the right-hand side, parameter settings, and so on. Amesos is not based on any matrix format; instead, an matrix interface (specified by using the Epetra_RowMatrix class) is adopted. This facilitates the usage of Amesos classes in any projects whose matrix can be wrapped as an Epetra_RowMatrix.

### **Amesos2**: direct sparse linear solver interface

Point-of-contact: Siva Rajamanickam (srajama@sandia.gov)  
[https://trilinos.github.io/amesos2.html](amesos2.html)

Amesos2 can be considered a templated version of Amesos that supports a wider variety of scalar and index types. Amesos2 provides two internal serial direct solvers, KLU2 (as of release 11.12) and Basker (as of release 11.14). Users of prior releases will need a third-party direct solver, such as SuperLU.

### **Pliris**: direct dense linear solver

Point-of-contact: Joe Kotulski (jdkotul@sandia.gov)  
[https://trilinos.github.io/pliris.html](pliris.html)

Pliris is an object-oriented interface to a LU solver for dense matrices on parallel platforms. These matrices are double precision real matrices distributed on a parallel machine.

The matrix is torus-wrap mapped onto the processors(transparent to the user) and uses partial pivoting during the factorization of the matrix. Each processor contains a portion of the matrix and the right hand sides determined by a distribution function to optimally load balance the computation and communication during the factorization of the matrix. The general prescription is that no processor can have no more(or less) than one row or column of the matrix than any other processor. Since the input matrix is not torus-wrapped permutation of the results is performed to “unwrap the results” which is transparent to the user.

* * *

## <span style="text-decoration: underline;">Preconditioners</span>

### **ShyLU**: Hybrid iterative/direct Schur complement solver

Points-of-contact: Siva Rajamanickam (srajama@sandia.gov)
[https://trilinos.github.io/shylu.html]shylu.html

ShyLU is designed as a set of domain-decomposition solvers that us distributed memory and node-level solvers and kernels that support the distributed memory solvers. The approaches in ShyLU are algebraic and so can be used as a black-box solvers.

The Domain Decomposition methods in ShyLU are a one-level hybrid direct/iterative approach based on Schur complements, two-level balancing domain decomposition method (bddc) and Overlapping Schwarz methods (FroSch). The node level solvers include sparse LU factorization (basker), sparse Cholesky factorization (Tacho), multithreaded triangular solver (HTS) and a fast iterative ILU algorithm (FastILU).

### **Teko**: Block preconditioning framework

Point-of-contact: Eric Cyr (eccyr@sandia.gov)  
[https://trilinos.github.io/teko.html](teko.html)

Teko is a package for development and implementation of block preconditioners. This includes support for manipulation and setup of block operators. Furthermore tools exist to support decomposition of a fully coupled operator. Additionally, facilities that allow the construction of approximate inverse operators using the full complement of available preconditioners and solvers are available in Teko. Finally, a small number of generic block preconditioners has been implemented in Teko, including block Jacobi, and block Gauss-Seidel. For the Navier-Stokes equation, Teko has implementations of SIMPLE, PCD and LSC.

### **Ifpack**: Point preconditioning, incomplete factorizations, and classical domain decomposition

Points-of-contact: Mike Heroux (maherou@sandia.gov) and Siva Rajamanickam (srajama@sandia.gov)  
[https://trilinos.github.io/ifpack.html](ifpack.html)

Ifpack provides a suite of object-oriented algebraic preconditioners. Ifpack constructors expect an Epetra_RowMatrix object for construction. Ifpack objects interact well with other Trilinos classes. In particular,Ifpack can be used as a preconditioner for AztecOO and smoother in ML.

Ifpack contains one-level domain decomposition preconditioners of overlapping type. Each “subdomain” is defined by the set of rows assigned to a given processors. Several options are available for the local solution, ranging from simple relaxation schemes, to incomplete factorizations, to direct solvers (through the Amesos package).

Ifpack is compatible with Epetra only.

### **Ifpack2**: Point preconditioning, incomplete factorizations

Points-of-contact: Mark Hoemmen (mhoemme@sandia.gov) , Chris Siefert ([csiefer@sandia.gov](mailto:csiefer@sandia.gov)), Jonathan Hu ([jhu@sandia.gov](mailto:jhu@sandia.gov))

[https://trilinos.github.io/ifpack2.html](ifpack2.html)

Ifpack2 can be considered a templated version of Ifpack. It provides SOR type relaxation methods, incomplete factorizations, and additive Schwarz methods.

Ifpack2 is compatible with Tpetra only.

### **ML**: smoothed aggregation algebraic multigrid

Points-of-contact: Ray Tuminaro (rstumin@sandia.gov), Jonathan Hu (jhu@sandia.gov), and Chris Siefert (csiefer@sandia.gov)  
[https://trilinos.github.io/ml.html](ml.html)

ML contains a variety of parallel multigrid schemes for preconditioning or solving large sparse linear systems of equations arising primarily from elliptic PDE discretizations. The main methods in ML are

*   smoothed aggregation algebraic multigrid
*   FAS nonlinear algebraic multigrid
*   two distinct algebraic multigrid methods for the eddy current approximations to Maxwell’s equations
*   a smoothed-aggregation-like method for convection dominated systems
*   matrix-free algebraic multigrid.

Within each of these methods there are several different algorithms to guide the type of coarsening and the inter-grid transfers (including the ability to drop weak coupling within the operator during inter-transfer construction). Additionally, ML can use Zoltan to rebalance coarse grid operators for better parallel performance.

ML provides a variety of smoothers: SOR, polynomial, Ifpack domain decomposition and incomplete factorizations, and Aztec methods. Coarse-grid solvers include the afore-mentioned smoothers, as well as any direct method available through Amesos.

ML can also be used as a framework to generate new multigrid methods. Using ML’s internal aggregation routines and Galerkin products, it is possible to focus on new types of inter-grid transfer operators without having to address the cumbersome aspects of generating an entirely new parallel algebraic multigrid code. We have used this flexibility to produce special multilevel methods using coarse grid finite element functions to serve as inter-grid transfers.

ML is compatible with Epetra only.

### **MueLu**: multigrid framework

Points-of-contact: Ray Tuminaro (rstumin@sandia.gov), Jonathan Hu (jhu@sandia.gov), and Andrey Prokopenko ([aprokop@sandia.gov](mailto:aprokop@sandia.gov))  
[https://trilinos.github.io/muelu.html](muelu.html)

MueLu provides a framework for parallel multigrid preconditioning methods for large sparse linear systems. MueLu provides algebraic multigrid methods for symmetric and nonsymmetric systems based on smoothed aggregation. It is designed to be extensible and can in principle support other algebraic multigrid (e.g., Ruge-Stueben) and geometric multigrid methods. MueLu does not provide any smoothers itself, but instead relies on other Trilinos packages for these capabilities. MueLu is templated on the ordinal and scalar types, and it can also exploit the hybrid communication benefits of Tpetra and Kokkos.

MueLu is compatible with Epetra and Tpetra.

* * *

Last updated Wednesday, November 13, 2013
