---
title: Isorropia
permalink: isorropia.html
folder: archive
show_sidebar: true
contact: egboman@sandia.gov
package: isorropia
doxygen: true
---

**Welcome to the Isorropia Home**

Isorropia is a package for combinatorial scientific computing, with focus on partitioning and load balancing, but also supports coloring and ordering of sparse matrices. Its main purpose is to assist with redistributing objects such as matrices and graphs in a parallel execution setting, to allow for more efficient computations. Isorropia partitions matrices by rows, and produces good maps for Epetra matrices (graphs). Isorropia should be called after the matrix (graph) is filled, so the sparsity pattern is known.

<span style="text-decoration: underline;">**Overview**</span>

Isorropia is a package for combinatorial scientific computing, with focus on partitioning (load balancing), but also supports coloring and ordering of sparse matrices. Its main purpose is to assist with redistributing objects such as matrices and graphs in a parallel execution setting, to allow for more efficient computations. Isorropia partitions matrices by rows, and produces good maps for Epetra matrices (graphs). Isorropia should be called after the matrix (graph) is filled, so the sparsity pattern is known.

Isorropia is primarily a matrix-based interface to the [Zoltan toolkit](https://sandialabs.github.io/Zoltan/), which is required. Zoltan became a Trilinos package in 9.0 and is automatically enabled by Isorropia. Zoltan contains both built-in (native) partitioners and provides access to other (third-party) partitioners. If you wish to use third-party libraries (such as ParMetis or PT-Scotch) with Isorropia via Zoltan, see the configure options for Zoltan.

For details on the latest Isorropia version, please see the Release_notes.txt file.
