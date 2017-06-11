---
title: Effective partitioning and load balancing
permalink: trilinos_user_group_2007_abstracts_wednesday_11h.html
folder: community
---

    Boman
    Wednesday, November 7th  
    11:00 - 11:45 am  

A good data distribution is crucial to achieve good performance in parallel computing. 
Partitioning and load balancing are techniques to distribute the work (load) approximately evenly among processors, while keeping the communication low. 
Combinatorial models like graphs and hypergraphs are powerful tools. We discuss these models in the context of sparse matrix computations. 
We show that two-dimensional data distributions can reduce the communication requirement compared to the commonly used row (or column) distributions.


We give an overview of Zoltan, a general-purpose toolkit for load balancing, which will soon become available as a Trilinos package, and Isorropia, a current Trilinos package that interfaces with Zoltan.