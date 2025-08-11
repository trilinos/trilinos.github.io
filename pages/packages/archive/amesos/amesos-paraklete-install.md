---
title: Amesos Paraklete Install
permalink: amesos-paraklete-install.html
folder: archive
---

## Paraklete Installation

_NOTE:_ These intructions were updated in June 2006\. They may not be kept up-to-date.

Paraklete requires George Karypis’ serial graph partitioner, [metis](http://glaros.dtc.umn.edu/gkhome/metis/metis/overview).

To build metis:

*   Download the [metis code](http://glaros.dtc.umn.edu/gkhome/fetch/sw/metis/metis-5.1.0.tar.gz)
*   Untar it: tar xzf metis-4.0.tar.gz
*   Build it: make

To build Amesos-Paraklete:

*   Update your configure invocation script, to specify where you put the metis library and include files. Something along the following lines:
    *   --enable-amesos-paraklete --with-libs=”/home/username/metis/libmetis.a ” --with-incdirs=”-I/home/username/metis/Lib/”
