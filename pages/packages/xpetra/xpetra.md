---
title: Xpetra
permalink: xpetra.html
folder: packages
show_sidebar: true
contact: <a href="mailto:jhu@sandia.gov">Jonathan Hu</a> (<a href="https://github.com/jhux2">@jhux2</a>), <a href="https://github.com/orgs/trilinos/teams/xpetra">@xpetra</a>
package: xpetra
doxygen: true
---

[xpetra](images/xpetra.jpg)

Xpetra a lightweight wrapper to both the Epetra and Tpetra linear algebra libraries. The Xpetra syntax mirrors as much as possible that of Tpetra.   
Xpetra enables algorithm developers to write to a single interface but be able to use either Epetra or Tpetra.   
Xpetra can also be introduced into existing Epetra code to allow for eventual migration to Tpetra.

Xpetra is used extensively in Frosch and MueLu.  By virtue of using Xpetra, many MueLu tests and example allow the runtime selection of either Epetra or Tpetra.
Xpetra is also used in Zoltan2, Ifpack2, and Galeri.
