---
title: Nonlinear
permalink: nonlinear_solver.html
folder: products
---

# Embedded Nonlinear Analysis Tools Capability Area

## Overview

The Trilinos Embedded Nonlinear Analysis Tools Capability Area collects the top level algorithms (outermost loops) in a computational simulation or design study. These include: the solution of nonlinear equations, time integration, bifurcation tracking, parameter continuation, optimization, and uncertainty quantification. A common theme of our algorithm R&D efforts is the philosophy of Analysis beyond Simulation, which aims to automate many computational tasks that are often performed by application code users by trial-and-error or repeated simulation. The tasks that can be automated include performing parameter studies, sensitivity analysis, calibration, optimization, time step size control, and locating instabilities. Also included in this capability area is the automatic differentiation technology that can be used in an application code to provide the derivatives critical to the analysis algorithms.

The capabilities in this area are spread across several Trilinos packages, which are independently developed software libraries. However, it is a high priority of the software developers to make the codes interoperable wherever possible, and we are well on our way to unifying the interface to the applications around a interface class called the ModelEvaluator. The ModelEvaluator is found in the Thyra and EpetraExt packages, and examples of its implementation can be found in many example problems in the analysis code packages.

A pair of packages also summarized in this section are the Sacado Automatic Differentiation capability and the Stokhos library for polynomial chaos expansions for embedded Uncertainty Quantification. The interface between Sacado and Stokhos and a C++ application code requires templating of the relevant pieces of code on a Scalar type.

All the capabilities in this area rely heavily on the lower-level (inner loop) algorithms such as scalable linear solvers and preconditioners, and Trilinos utilities and interfaces. The algorithm development in this area is particularly well aligned with several of the Trilinos Strategic Goals, including Full Vertical Coverage, Scalability, and Hardened Solvers.

If you have questions on the algorithm, software, or vision of this capability area, please contact Andy Salinger or any of the package leads listed below.

## Trilinos Packages in the Embedded Nonlinear Analysis Capability Area

Package Name | Quick Description | Point of Contact
------ | ------ | ------
[NOX](nox_and_loca.html) | Nonlinear Solver with Globalized Newton’s methods | Roger Pawlowski
[LOCA](nox_and_loca.html) | Parameter Continuation, Bifurcation Tracking | Eric Phipps
[Rythmos](rythmos.html) | Time integration algorithms | Curt Ober
[MOOCHO](moocho,html) | Embedded (PDE-constrained) Optimization, rSQP | Roscoe Bartlett
Aristos | Full-space intrusive optimization (not yet released) | Dennis Ridzal
[Sacado](sacado.html) | Automatic Differentiation using Expression Templates | Eric Phipps
[Stokhos](stokhos.html) | Stochastic-Galerkin Uncertainty Quantification Tools | Eric Phipps
TriKota | Interface to Dakota toolkit for a Trilinos application (not yet released) | Andy Salinger

## Related Efforts Outside of Trilinos

|         |         |
| -------- | --------- |
| [Dakota](http://dakota.sandia.gov) | Dakota is a mature and widely-used software toolkit at Sandia, independent from Trilinos, that delivers many related analysis capabilities using non-intrusive (black box) methods. These include numerous algorithms in the areas of Optimization, Uncertainty Quantification, Nonlinear-Least-Squares, and Reliability. A adapter package called TriKota is under development for the Trilinos 10.0 release to make these capabilities accessible through the same interface as the above anaysis codes. |
| DemoApps | The DemoApps code project is building a prototype PDE code primarily from Trilinos packages. The code will demonstrate the use of Embedded Nonlinear Analysis Tools as well as cutting edge algorithms from all other Trilinos capability areas (not yet externally released). |

## Brief Mathematical Description of Trilinos’ Embedded Nonlinear Analysis Tools

This is brief description of the types of analysis that are performed by the codes in the nonlinear analysis capability area. The starting point is a set of nonlinear equations, such as those coming from discretized Partial Differential Equations or Integral Equations.

The **Nonlinear Solver** [NOX](nox_and_loca.html) solves a set of nonlinear algebraic equations ![$f(x)=0$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_0.png) for ![$x$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_1.png) The methods included Newton-based algorithms such as inexact Newton, matrix-free Newton-Krylov, line-search methods, trust-region methods, tensor methods, and homotopy methods. Most of these methods ask the user to supply a Jacobian matrix ![$J = \frac{df}{dx} $](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_2.png) and include the computational step of approximating ![$J = \frac{df}{dx} $](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_2.png).

The **Time Integration** algorithms in [Rythmos](rythmos.html) solve ODEs and DAEs of the form ![$f(\dot{x}, x, t)=0$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_3.png) . The algorithms include explicit and implicit methods with adaptive step size control and integration order control, including BDF and Runge-Kutta methods. Given an initial conditions ![$x(t=0)$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_4.png) , the methods find a series of solutions ![$x(t_i)$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_5.png) at time points ![$t=t_i$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_6.png). For systems with parameter dependence, ![$f(\dot{x}, x, t, p)=0$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_7.png), a sensitivity analysis capability is now available to solve for ![$\frac{dx}{dp} $](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_8.png) simultaneously. A checkpointing interface for adjoint integrations is under development.

A set of **Bifurcation Tracking** algorithms have been implemented in [LOCA](nox_and_loca.html). These algorithms augment the steady-state system of equations with extra distinguishing conditions that find a parameter value where there is an exchange of stability (![$F(X) = \left[ \begin{array}{c}f(x,p)\\ h(x,p) \end{array} \right] =0$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_9.png)). This augmented system is then solved by the nonlinear solver package. Specifically, turning point (folds), pitchfork bifurcations, and Hopf bifurcations can be located and tracked. Similarly, this formulation can be used for **Constraint Enforcement**, where the extra equations ![$h(x,p)$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_10.png) can be supplied by the user, and the same number of parameters can be freed to be part of the solution.

An initial implementation of a capability for solving for **Space-Time and Periodic Solutions** called “4D” in LOCA has been developed. With this approach, analysis algorithms designed for steady problems can be applied to transient problems. The all-at-once methodology greatly expands the size of the system, which is in part mitigated by the ability of “4D” to parallelize computations over the time axes.

Steady-state (or equilibrium) solutions, including bifurcations points, can be tracked through parameter space with **Parameter Continuation** algorithms in [LOCA](http://trilinos.org/packages/nox-and-loca/). An curve of points ![$f(x,p)=0 \ \ \mbox{for}\ p_{min} < p < p_{max}$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_11.png) are calculated in this manner. The code can perform Natural Parameter or Pseudo Arclength continuation methods, with a variety of predictors and steps size control algorithms. Homotopy algorithms have been pre-programmed using this interface as a globalized nonlinear solver.

A driver for performing **Stability Analysis** is included in the parameter continuation library. This implements spectral transformations, and then calls an eigensolver (typically Trilinos’ Anasazi package). For generalized eigenvalue problems of the form ![$Jz=\lambda Mz$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_12.png) , the spectral transformations include Shift-and-Invert and the generalized Cayley transformation

**PDE-Constrained Optimization** algorithms have been implemented in [MOOCHO](moocho.html) and Aristos packages to take advantage of the efficiencies accessible by embedded algorithms. These have the form: ![$\mbox{minimize } g(x,p) \mbox{ subject to } f(x,p)=0$](http://trilinos.org/oldsite/CapabilityWebpages/NonlinearTransientOptimizationSolvers/html/form_13.png) The algorithms use Quasi-Newton approaches to simultaneously minimize the objective function and satisfy the constraint equations. The algorithms can make use if adjoint information if available to most efficiently solve systems with large design spaces. Both reduced-space (MOOCHO) and full-space (Aristos) algorithms have been developed.

**Automatic Differentiation** tools for C++ codes have been developed in [SACADO](sacado.html) to automatically extract analytic derivative information from codes. This capability is implemented with expression templates that essentially inline code that performs the chain rule. The application code must template a key part of their code (such as the single element fill portion in a finite element code) on the <scalar> type.

**Embedded UQ** methods are under active development. This includes the [Stokhos](stokhos.html) tools to automate the propagation of random variables through codes, such as stochastic finite element formulations, leveraging the same templated interfaces as the automatic differentiation capability. Other pieces include the subsequent nonlinear solution, transient propoagation, and linear solution of the full stochastic system.

## Active Areas of Research and Development

The following are areas of algorithm and software development that will be receiving focused attention in the near- to mid-term by the Trilinos developers working in the Embedded Nonlinear Analysis Tools capability area.

*   Expansion of the Rythmos transient integration code to include adjoint integrations with checkpointing, and error estimation.
*   Development of the embedded UQ capability, hybrid UQ methods combining sampling and embedded algorithms, and scalable linear solver algorithms for stochastic systems.
*   Develop System Modeling capability: systems abstractions, networks, and UQ-enabled systems solvers.
*   Development of a single factory to generate any solution or analysis scheme from a parameter list.
*   Improved software quality, such as appropriate handling of thrown exceptions.
*   Demonstrations of the transformational analyses that can be performed with embedded algorithms on a large-scale applicaiton code that uses automatic differentiation.

## Where should you look next?

For more detailed information on the capabilities available through Trilinos, you can look at the web pages for the individual packages, that were listed in the [above Table](#trilinos-packages-in-the-embedded-nonlinear-analysis-capability-area). Each package has example problems that show common use cases.