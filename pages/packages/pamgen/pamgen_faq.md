---
title: PAMGEN FAQ
permalink: pamgen_faq.html
folder: packages
---

**What is PAMGEN useful for?**

PAMGEN is useful for providing a parallel unstructured finite-element analysis code with a huge mesh.

**How many elements can PAMGEN generate?**

The number of elements PAMGEN can generate is limited by the size of a 32 bit integer (just above two billion).

**Does PAMGEN scale well?**

PAMGEN performs no internal inter-processor communication and so scales very well.

**What kinds of elements can PAMGEN generate?**

4 node quads in 2D and 8 node hexes in 3D.

**Does PAMGEN perform any communication within its routines?**

No.

**What kinds of domain decomposition does PAMGEN provide.**

PAMGEN provides several decomposition options. The most useful is a simple bisection strategy that slices the mesh in different topological directions. 
This strategy works best when the number of processors has many prime factors. A user defined slicing strategy allows control which topological direction are sliced. 
A random decomposition method is provided as a stress test for analysis codes.
