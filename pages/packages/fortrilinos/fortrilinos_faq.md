---
title: ForTrilinos FAQ
permalink: fortrilinos_faq.html
folder: packages
show_sidebar: true
contact: 
package: ForTrilinos
---

**What features must a Fortran compiler support to successfully compile ForTrilinos?**

The object-oriented programming and C interoperability features defined in the Fortran 2003 standard.

**Which compilers support these features?**

[ACM SIGPLAN Fortran Forum](http://portal.acm.org/citation.cfm?id=J286 "Fortran Forum") publishes a running survey of compiler support for Fortran 2003\. As of the April 2011 [survey](http://portal.acm.org/ft_gateway.cfm?id=1961365&type=pdf&CFID=21623089&CFTOKEN=87671454 "Chivers and Sleightholme survey"), all ten compilers supported the C interoperability subset of Fortran 2003 and the IBM XL Fortran (XLF) and Cray Compiler Environment (CCE) each supported the full Fortran 2003 standard. Intel, Portland Group, the Gnu Compiler Collection (GCC), and the Numerical Algorithms Group (NAG) Fortran compilers are all supporting substantial and increasingly large portions of the standard with each release.

We have successfully built ForTrilinos with the XLF and NAG compilers and believe we are close to a successful build with CCE. We are in regular contact with each compiler project. Please [contact us](http://trilinos.org/oldsite/packages/fortrilinos/contact.html "Contact Us") for an estimated timeline on building with the Intel, Portland Group, or GCC (gfortran) compilers. It will help our cause for you to also let your compiler vendor know about your interest in using ForTrilinos.

**My code is written in Fortran 77/90/95\. Do I need to learn Fortran 2003 to use ForTrilinos?**

Yes but the required facility with Fortran 2003 depends on your level of involvement with ForTrilinos. The language subset required of users is signficantly smaller than that required of contributors. Use of most ForTrilinos interfaces requires only that you know how to declare and construct derived types and invoke type-bound procedures. You also need to be familiar with using the KIND parameters declared in the standard ISO_C_BINDING module. Several texts now cover these topics, including Chapters 12 and 14 of [Modern Fortran Explained](http://books.google.com/books?id=MmOIFEgsDLwC&printsec=frontcover&dq=modern+fortran+explained&hl=en&ei=sGLRTYacMtSbhQfpp6HyDA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CDUQ6AEwAA "Metcalf, Reid and Cohen (Cambridge University Press, 2011)") and Chapters 2 and 11 of [Scientific Software Design: The Object-Oriented Way](http://tinyurl.com/ScientificSoftwareDesignGoogle "textbook"). The latter includes a case study on the design of ForTrilinos.

**Is ForTrilinos portable?**

Yes, the very reason for using the C interoperability features of Fortran 2003 is to provide portable mechanisms for calling C procedures from Fortran and vice versa.

**What about name mangling and trailing underscores and such?**

Unlike most previous attempts to interface Fortran and C/C++, you no longer have to learn the naming convention of your compiler. The Fortran 2003 C interoperability constructs allow the programmer to bind a Fortran procedure name to a corresponding C procedure and vice versa. Also, it is possible for callbacks to occur by passing back and forth C function pointers via their corresponding Fortran 2003 derived type.

**What if I don’t see Fortran interfaces for the Trilinos packages I want to use?**

The development of ForTrilinos is user-driven. Let us know what packages you want to use, and we will either develop them or guide you in doing so. As with any open-source package, most of our developers contribute in ways that address their own needs as users
