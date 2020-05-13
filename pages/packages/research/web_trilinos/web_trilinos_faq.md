---
title: WebTrilinos FAQ
permalink: web_trilinos_faq.html
folder: packages
---

**What is WebTrilinos?**

WebTrilinos is a web-based interface to Trilinos, or a _portal_ to the Trilinos world. It is composed by three modules, contained in three separate directories:

1.  MatrixPortal, which is the matrix-testing environment; (unsupported)
2.  a C++ module, which allows the testing of C++ programs;
3.  a python module, which allows the testing of PyTrilinos programs. (unsupported)

**What’s significant about the name ‘WebTrilinos’?**

Simply that you can use most of Trilinos from the Web. Stated otherwise, WebTrilinos is a new _skin_ of Trilinos. However, you won’t find access to WebTrilinos modules from this web site: you (or your system administrator) have to install WebTrilinos on a web server.

**What platforms does WebTrilinos run on?**

WebTrilinos has been tested on a Linux webserver (Fedora Core), but it should run on all platforms with python, a web server (we use [apache](http://www.apache.org)) and [PHP](http://php.net) installed, and where PyTrilinos runs. If you can install and use PyTrilinos, then you are mostly done; please check the [PyTrilinos web page](pytrilinos.html) for more details on how to install PyTrilinos. WebTrilinos also uses few *nix commands like <tt>convert</tt>.

**Is there support for MPI and threads?**

Yes, the current version of the C++ module does support MPI and multiple threads. After installation, the number of MPI processes and threads can be set using drop-down boxes.

**Which Trilinos packages are required to install and use WebTrilinos?**

WebTrilinos minimally requires the following Trilinos packages:

*   Teuchos
*   Epetra
*   EpetraExt
*   Galeri
*   AztecOO
*   Amesos
*   IFPACK
*   ML

Other packages can be used through the C++ interface. Any package that is installed can be used through the C++ interface because the Makefile.export system determines which packages to link against based on what was installed.

**Which non-Trilinos packages are required to install and use WebTrilinos?**

The following non-Trilinos packages are needed:

*   a web server (for example, [Apache](http://www.apache.org));
*   support for [PHP](http://php.net), version 5 or higher;
*   the XML parser EXPAT, which is typically already installed on most systems (for the unsupported MatrixPortal only). This requires EXPAT to be enabled for Teuchos. EXPAT is only used to load XML problems in the MatrixPortal module, so you might decide to skip it — 99 % of WebTrilinos will run anyway;
*   a Python plotting tool called [PyChart](http://home.gna.org/pychart/) (for the unsupported Python interface only);
*   the <tt>convert</tt> *nix tool;

Note that Trilinos requires BLAS and LAPACK, and the PyTrilinos package requires NumPy and SWIG. However packages can be configured with support for several third-party libraries, but none of them is mandatory to use WebTrilinos.

**What about security?**

The C++ and Python modules of WebTrilinos gives full access to WebTrilinos users, and as such they should be password protected. 
Only trusted users should be able to use the C++ and Python modules. This is easy to do with Apache: just add a <tt>.htaccess</tt> file.
**DO NOT LET ANONYMOUS USERS ACCESS YOUR C++ AND Python MODULES OF WebTRILINOS, THIS IS A SEVERE SECURITY RISK FOR YOUR SYSTEM!!!**. 
The MatrixPortal module, instead, does not expose the system, and can be made accessible to anonymous users. Whether the resulting workload is acceptable or not for a given installation should be established by the user.