---
title: IFPACK2
permalink: ifpack2.html
folder: packages
---

Ifpack2 provides incomplete factorizations, relaxations, and domain decomposition operators for linear algebra objects (sparse matrices, operators, and dense vectors and multivectors) provided by the [Tpetra](http://trilinos.org/packages/tpetra/) package. You may use these operators however you wish: for example as preconditioners in an iterative solver, or as smoothers for algebraic multigrid.

Ifpack2 aims at offering the same functionality as the [Ifpack](http://trilinos.org/packages/ifpack/) package, though it does not promise backwards compatibility. Ifpack only works for [Epetra](http://trilinos.org/packages/epetra/) linear algebra objects; Ifpack2 only works for Tpetra objects.

### Why Ifpack2?

Why do you want to use Ifpack2? First, if you are using Tpetra, you need to use Ifpack2 if you want incomplete factorizations, relaxations, or domain decomposition. Second, Ifpack2 gives you the same advantages as Tpetra. You can solve problems with more than two billion unknowns, by using 64-bit global indices, yet save memory at the same time by only storing 32-bit local indices. You can use matrices and vectors with any sensible data type, not just `double`. For example, you can use `float` to save memory, or an extended-precision type like `dd_real` or `qd_real` to improve robustness for difficult problems. Ifpack2 even works with complex-valued data, like `std::complex<float>` and `std::complex<double>`. Finally, Ifpack2’s algorithms use and produce Tpetra objects, so you can exploit Tpetra’s hybrid (MPI + threads) parallelism features.

### <span style="text-decoration: underline;">Helpful Links</span>

*   [Documentation](http://trilinos.org/packages/ifpack2/ifpack2-documentation/ "Documentation") ([User’s Guide](https://trilinos.org/wordpress/wp-content/uploads/2016/06/ifpack2guide.pdf), [Doxygen](http://trilinos.org/docs/dev/packages/ifpack2/doc/html/index.html))
*   [How to cite Ifpack2](https://trilinos.org/packages/ifpack2/ifpack2-citation/)