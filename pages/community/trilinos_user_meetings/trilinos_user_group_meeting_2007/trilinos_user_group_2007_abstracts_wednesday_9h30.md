---
title: Safe memory usage in C++ with new Teuchos utility classes
permalink: trilinos_user_group_2007_abstracts_wednesday_9h30.html
folder: community
---

    Bartlett
    Wednesday, November 7th  
    9:30 - 10:30 am  

The introduction and the expansion of the use of the Teuchos reference-counted pointer class (now called Teuchos::RCP) has been very successful at improving the quality and safety of C++ code and the productivity of algorithm developers. 
However, the Teuchos::RCP class does not solve all of the issues of memory management in C++ and we still experience too many memory usage problems (e.g. segfaults and memory leaks). 
The core problem here is the use of raw C++ pointers at the application programming level (in this case, the algorithm programming level). 
I will describe a new set Teuchos utility classes that are currently being developed that will encapsulate almost all basic uses of raw C++ pointers. 
Specifically, I will discuss some new utility classes for managing arrays of objects in a safe and efficient way. Together with Teuchos::RCP, these utility classes provide a more solid foundation for developing C++ software and catching common memory usage mistakes. 
I will also discuss why using STL classes does not automatically make for safer memory usage and can actually make code less safe than when using raw C++ pointers. 
I will also describe why I believe that memory checking tools like Valgrind and Purify will never be able to sufficiently verify the memory usage of our programs or even help to find errors when they occur. 
I will end the talk by discussing strategies for assimilating these new memory encapsulation utility classes into current Trilinos packages and helping users to transition to the use of the new interfaces in a smooth and safe way.