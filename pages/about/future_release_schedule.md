---
title: Future Release Schedule
permalink: future_release_schedule.html
folder: about
---

With the growth in continuous integration and delivery, the Trilinos team does not emphasize planning explicit releases or release dates as much as in the past.  Having said that, Trilinos does follow Semantic Versioning (SEMVER) practices, as defined by [semver.org](https://semver.org).  As a result, major release versioning is particularly consequential, since it signals the disruption of backward compatibility.

Presently, the Trilinos team is preparing Trilinos Version 13, which eliminates numerous dynamic allocation functionality in Tpetra.  Availability of "on-demand" memory allocation, while convenient to the user, essentially prohibits shared memory parallel scalability because at any time a thread could be forced to re-allocate storage.
