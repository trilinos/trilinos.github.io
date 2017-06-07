---
title: Isorropia FAQ
permalink: isorropia_faq.html
folder: packages
---

**What’s significant about the name ‘Isorropia’?**

Isorropia is a Greek term meaning “equilibrium” or “balance”. This refers to the load-balancing capabilities. The preferred pronounciation is as ‘Issoropia’.

**What’s the difference between Isorropia and Zoltan?**

Isorropia provides a convenient and powerful interface between Zoltan and Epetra. Zoltan provides the underlying partitioning (load balancing), coloring, and ordering algorithms. Isorropia sets up graph/hypergraph models of sparse matrices and calls Zoltan. 
Note that Isorropia supports many Zoltan features but not all (e.g. multiple weights). In most cases, if you have an Epetra matrix or graph, you should use Isorropia not Zoltan.

**Can I build Isorropia without Zoltan?**

No, Isorropia automatically enables Zoltan in the Trilinos configure system, and there is no simple way to disable Zoltan. Isorropia is not very useful without Zoltan, so this should not be a problem.

**What is the partitioning model used for sparse matrices?**

By default, Isorropia uses a hypergraph model where rows correspond to vertices. This will minimize the communication volume in sparse matrix-vector multiplication, and generally gives a good data distribution for many operations.

**Can I partition a matrix by columns, not by rows?**

No, this is currently not supported. Epetra uses row-based sparse matrix structures, so partition by rows is most useful. You could of course manually transpose the matrix.

**I have {a mesh, points, particles} that I need to load-balance. Can I use Isorropia?**

Geometric partitioning of mesh/points/particles is supported in Isorropia 3.2 (Trilinos 10.0) and later. Create a Partitioner with an Epetra_MultiVector.