---
title: What’s New in the Old - Rythmos, ML, Amesos
permalink: trilinos_user_group_2007_abstracts_tuesday_2h15.html
folder: community
---

    Coffey / Siefert / Thornquist  
    Tuesday, November 6th  
    2:15 - 3:15 pm  

## Rythmos:

Rythmos has undergone a significant transformation between Trilinos 7.0 and 8.0. The number of base stepper algorithms has remained the same, but the interfaces and the features available for use with these algorithms have grown immensely. In particular, Rythmos now features a high-level integrator that is breakpoint aware, forward sensitivities can be computed with the BDF and Backward Euler steppers, a full concrete implementation of the interpolation buffer class along with two specific interpolator classes, and the BDF stepper has received a complete refactor which separates out the step control strategy from the algorithm and allows specifying your own error weight norm calculation. This talk will be a brief overview of the interface and feature updates to Rythmos.

## ML:

This talk with provide an update for users of ML. It will focus primarily on two new features: a new solver for the eddy current Maxwell's equations, known as RefMaxwell and parameter list validation. The first provides more advanced solver capacity, while the second helps catch spelling and type errors in user parameter lists passed to ML.

## Amesos:

This talk will provide an update for developers and users on the solvers provided through the Amesos package. The subjects being discussed in this talk include the integration of KLU 1.0, updates to Paraklete, and the new Amesos timing class. This will be a brief overview and is suited for beginning to advanced Amesos users.