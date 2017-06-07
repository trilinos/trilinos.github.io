---
title: WebTrilinos Install
permalink: web_trilinos_install.html
folder: packages
---

**Installation**

It is recommended that users not install WebTrilinos, but rather access WebTrilinos via the [WebTrilinos Docker Image](web_trilinos_docker_image.html).

Below is the procedure to follow to install WebTrilinos:

1.  Download or clone Trilinos 12.4 or higher, and configure it with support for the required packages (see the FAQ page).
2.  Build Trilinos by typing <tt>make</tt> in the build directory.
3.  Type <tt>make install</tt> at the top build Trilinos level.
4.  Clone or download Trilinos from the [WebTrilinos repository on GitHub](https://github.com/trilinos/WebTrilinos) into the httpdocs directory of your web server (for example, <tt>/var/www/html/WebTrilinos</tt>).
5.  Load that directory from the web, and open the <tt>index.html</tt> file. A web page shows up; note that you must have PHP installed or you will not be able to proceed. PHP must process both <tt>.html</tt> and <tt>.php</tt> files. Follows the instruction in this page, and configure your installation. A basic testing page is also provided to assist with troubleshooting.

Since the Python and MatrixPortal modules are unsupported, it is recommended that unless these features are verified be necessary and working that users be directed to the C++ interface landing page.

The FAQ page reports the list of Trilinos and non-Trilinos packages to install.