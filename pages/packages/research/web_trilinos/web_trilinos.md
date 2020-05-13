---
title: Web Trilinos
permalink: web_trilinos.html
folder: research
show_sidebar: true
contact: marzio.sala@gmail.com
package: trios
---

![WebTrilinos Logo](images/webtrilinos_logo.jpg)

WebTrilinos is a scientific portal, a web-based environment to use several Trilinos packages through the web.

If you are a teaching sparse linear algebra, you can use WebTrilinos to present code snippets and simple scripts, and let the students execute them from their browsers.

If you want to test linear algebra solvers, you can use the MatrixPortal module, and you just have to select problems and options, then plot the results in nice graphs.

From the user’s perspective, the only component required to use WebTrilinos is _any_ browser and an internet connection. Then, (simple) C++ and Python programs can be written on a web form, executed on a server, and the output is sent back to the user’s browser. Code snippets for most of Trilinos and PyTrilinos packages are already available in convenient repositories. Most commonly, code snippets are pasted in from the Trilinos Hands-on Tutorial or from some other source to allow for highly customized tutorials, and the code snippets available directly through WebTrilinos serve only to introduce the WebTrilinos interface. WebTrilinos also contains a problem solving environment (PSE) for the analysis of linear algebra solvers, like direct solvers, Krylov solvers, and preconditioners. This environment is called MatrixPortal.

NOTE: Currently, only the C++ interface for WebTrilinos is maintained. Tutorial hosts are encouraged to use the C++ interface page as the landing page for students. If anyone wishes to contribute changes back to WebTrilinos in the form of GitHub pull requests for the maintenance of the Python and MatrixPortal interfaces, they are welcome to do so.

NOTE: this web site does not offer access to WebTrilinos capabilities. The **recommended approach for accessing WebTrilinos functionality** is to use the [WebTrilinos Docker image](web_trilinos_docker_image.html). Alternatively, you (or your system administrator) can install it on your web server.

To be installed, WebTrilinos requires the following:

1.  a web server, like Apache;
2.  PHP installed on the web server. PHP must process both <tt>.html</tt> and <tt>.php</tt> files;
3.  an installed version of Trilinos, with the following packages: Teuchos, Epetra, EpetraExt, AztecOO, IFPACK, Amesos, ML, Galeri, PyTrilinos (and, of course, WebTrilinos itself);
4.  the [PyChart](http://home.gna.org/pychart/) package;
5.  the <tt>convert</tt> *nix tool to convert image files.

WebTrilinos comes with a set of easy-to-use tools that suggest the configuration options. For more details, please check the [FAQ](webtrilinos_faq.html) page. Check also the [installation page](webtrilinos_install.html) for more details on the installation procedure.

<span style="text-decoration: underline;">**Overview**</span>

WebTrilinos is a web-based interface to Trilinos, or a _portal_ to the Trilinos world. It is composed by three modules, contained in three separate directories:

1.  MatrixPortal, which is the matrix-testing environment; (unsupported)
2.  a C++ module, which allows the testing of C++ programs;
3.  a Python module, which allows the testing of PyTrilinos programs. (unsupported)

The goal of WebTrilinos is to make the usage of Trilinos (and PyTrilinos) as easy as possible. As such, WebTrilinos is targeted to new users, or to those who want to get a taste of Trilinos and its components without the hassles of downloading and installing it. Clearly, don’t expect to unleash the full Trilinos power through WebTrilinos: the entire code (or script, for PyTrilinos) must be contained in the text form of the web page. However, if you are starting with Trilinos, or if you want to teach Trilinos, then you get enough flexibility to show the usage of algorithms to your students, without the need to install Trilinos on each student’s machine.

If your focus are sparse linear system, you can experiment with various solution techniques, like direct solvers, Krylov solvers, relaxation preconditioners, incomplete factorizations, multilevel smoothed aggregation methods, in an easy-to-use way. You can either use the Galeri problem generator, or upload linear systems using the Harwell/Boeing format, or a custom XML matrix format.

A simplified workflow for WebTrilinos is reported in the figure below; note that, in the current implementation, the server and solver are hosted on the same machine.

![](images/diagram.png)

* * *

We now give an overview of the MatrixPortal module of WebTrilinos. With MatrixPortal, you define a set of linear problems and a set of methods to solve them, then you compare the solution phases, in order to evaluate (using a criterion you specified) the effectiveness of the solution methods.

Matrix Portal operates as a sequence of five **steps**, defined as follows:

1.  **Step 1: Select Data** is the definition of the linear system matrices. After step 1, you have one or more **ProblemID**‘s or labels, and each of them identifies the linear problem you want to analyze or solve.
2.  **Step 1C: Check Data (optional)** is a simple, optional check on the selected data, aiming to verify the matrix dimension and nonzeros. You can also give a look to the sparsity pattern of the matrix.
3.  **Step 2: Select Parameters** defines the parameters for the Krylov accelerators, like CG and GMRES, and the preconditioners. You can choose among polynomial preconditioners, relaxation preconditioners like Jacobi, Gauss-Seidel and symmetric Gauss-Seidel, incomplete factorizations, and multilevel preconditioners. You also have to specify an evaluation criterion, in order to evaluate the different solvers. Typical evaluation parameters are the CPU time for the solution, or the iterations to converge, or the estimated condition number.
4.  **Step 3: Compute** performs all the computations and reports the result on the web browser. In this phase, each result is given a label, and as such is recordered.
5.  **Step 4: Check Results** collects the results and offers tools to analyze and compare them. A simple tool is given, to generate a bar chart for selected data. From here, you can go back to step 1 and select new problems, or go to step 2 and select new solution techniques for already defined problems.

You can move across these steps as shown in the following picture:  
[![](images/workflow.png)](https://trilinos.org/webtrilinos/step1.html)

An overview of the installation procedure is reported in the [FAQ](/webtrilinos_faq.html) page.
