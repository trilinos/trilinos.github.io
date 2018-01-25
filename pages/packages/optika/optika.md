---
title: Optika
permalink: optika.html
folder: packages
show_sidebar: true
contact: klnusbaum@gmail.com
package: optika
doxygen: true
---

![Optika](images/optikabanner.png)

Welcome to the Optika Home

The Optika package provides trilinos users with easy access to GUI input methods for their programs.

The Users Manual

For a complete and detailed descrption of what Optika is and how to use it, please see the [Optika Users Manual](pdfs/OptikaSANDReport.pdf)

### Overview

The Optika package gives developers the tools they need to quickly obtain information from their users, while still implementing a robust GUI. The general work flow of a program utilizing the Optika package goes something like this:

1.  Determine what inputs are needed from the user
2.  Create a list specifying these inputs
3.  Execute the GUI with the getInput() function to obtain the inputs specified in step 2
4.  Proceed with the rest of the program with the given user inputs

An alternate work flow is also available. In this work flow, the developer specifies a custom fucntion along with the inputs. When the GUI is executed, it stays active for the entire duration of the program. Everytime the user clicks a button, the custom function is called with the current input values.

### Contact

The Optika package is still under heavy development. At this point in time we would greatly appreciate any bug reports or feature requests. Please submit all bugs and requests through bugzilla. If you don’t have a bugzilla account please send an e-mail to the lead developer [Kurtis Nusbaum](mailto:klnusbaum@gmail.com). We like feedback, so please let us know what you think.
