---
title: ML API
permalink: ml_api.html
folder: archive
---

**The ML API: A C++ Framework for the Development of Scalable Multilevel and Domain Decomposition Preconditioners based on Aggregation**  
MLAPI is an object oriented framework that enables the development and usage of efficient, scalable and portable implementations of multilevel preconditioners for general distributed sparse matrices, in both serial and parallel environments. To learn more about MLAPI, see the [ACM/TOMS article](http://dx.doi.org/10.1145/1163641.1163643).

The main feature of this framework is the use of several programming paradigms for the different implementation layes, with a strong emphasis on object oriented classes and operator overloading for the top layer, and optimized FORTRAN and C code for the layers underneath. In particular, MLAPI takes advantage of [ML](ml.html) for all computationally intensive tasks.

MLAPI has been designed with the following goals in mind:

1.  **Portability**. Implementations of numerical algorithms should be directly portable across machine platforms. MLAPI is written in ANSI C++. The STL library is employed to increase efficiency. For message passing, we adopted MPI, which is the de-facto standard, and as such widely available and accepted by users of parallel applications. As a result, MLAPI has been successfully compiled on Linux, SGI Origin, DEC-alpha, SUN, and MAC OS X.
2.  **Clarity**. Implementations of numerical algorithms should resemble the mathematical formulation on which they are based. This is in contrast to FORTRAN and C, which can require complicated subroutines or function calls, with a long parameter list. A key design for MLAPI was a user interface that is intuitive. Our intention is that it should be possible for this library to be used by those who have only a basic knowledge of MPI and C++. Ideally, the structure of all MLAPI kernels should be as close as possible to the that of MATLAB. We have developed two types of C++ interfaces to basic kernels. The first type utilizes the binary operators <tt>*, +, -</tt>, overloaded using the C++ capabilities. The second type is a set of interfaces (methods, functions) which can group triads or perform more complex operations.
3.  **Flexibility**. MLAPI is not based on any particular matrix format. This is particularly convenient since several matrix formats are currently in used. MLAPI supports any data format that can offer a getrow() function, which returns the column ID and the value of all nonzero elements for any locally hosted row. C users can provide this using the <tt>ML_Operator</tt> structure, while C++ users can derive a class from the pure virtual <tt>Epetra_RowMatrix</tt> class of the Epetra package. Similarly, all operators defined by MLAPI are wrapped as <tt>Epetra_RowMatrix</tt> and <tt>ML_Operator</tt>, so that users can access their nonzero elements without worrying about the actual data storage used by MLAPI.
4.  **Extensibility**. Multilevel algorithms are far from being completely understood for all classes of problems. It is important for the multilevel library to be easily extended, to validate new approaches. To that aim, encapsulation is used to hide details in specific classes. Besides, a set of function based on abstract interfaces is provided, to generate the necessary multilevel operators. Polymorphism allows the user to derive classes to implement new features. All MLAPI classes and methods automatically use a set of default parameters, that can be tuned by specifying the desired parameters in a parameter list.
5.  **High performance**. A good numerical package that utilizes OO programmingmust exhibit a computational efficiency that is comparable to that of FORTRAN and C codes. This puts severe limitations to the OO design. It is certain easy to generate elegant but inefficient C++ code. We implemented MLAPI as a light layer of C++, on the top of a mixture of FORTRAN77 kernels. for all dense matrix operations and vector updates, C functions for all sparse matrix operations (like distributed sparse matrix-matrix product), and C++, for memory management. As a result, MLAPI is (almost) as efficient as the C or FORTRAN library underneath.
6.  **Memory Management**. One of the most powerful feature of C and C++ if the capability of allocating memory. Unfortunately, this is also the area where most bugs are found — not to mention memory leaks. We have adopted the Teuchos smart pointers to manage memory. MLAPI objects should never be allocated using <tt>new</tt>, and therefore never free them using <tt>delete</tt>. The code automatically deletes memory when it is no longer referenced by any object. Besides, functions or methods that need to return MLAPI objects, should always return an instance of the required object, and not a pointer or a reference.  
    At a first glance, this may appear as a major limitation for optimal performances. Dealing with an instance of an object, and not with pointers or references, signifies that the new instances have to be created and copied, usually an expensive operation. This is not what happens with MLAPI. In fact, all MLAPI objects are defined as light containers of pointers, automatically allocated and managed as necessary.
7.  **Operator overloading**. Operator overloading is an interesting capability of C++ that has been only partially used in the scientific computing community. We adopt expression templates to increase the performances of MLAPI.

We now report one short example of MLAPI usage; more examples can be found [here](docs//ml/index.html). The following is a power method codes using MLAPI:
   
    int NumGlobalRows = 16;
    Space MySpace(NumGlobalRows);
    MultiVector x(MySpace), y(MySpace);
    Operator A = Gallery("Tridiag", MySpace);

    x.Random();
    x = x / sqrt(x * x);

    int MaxIters = 10;

    for (int i = 0 ; i < MaxIters ; ++i) {

      y = A * x;  // matrix-vector product

      double RQ = (y * x) / (x * x);
      if (GetMyPID() == 0)
        cout << "iter = " << i << ", RQ = " << RQ << endl;

      x = y / sqrt(y * y);

    }

As one can see, operators and vectors are mostly like MATLAB. This makes the MLAPI an ideal tool to test and implement novel ideas. The MLAPI distribution, contained within the ML package of Trilinos, reports several examples. including a fully-fledged multilevel preconditioner based on smoothed aggregation, and a working adaptive smoothed aggregation preconditioner.

The [MLAPI documentation](docs//ml/index.html) is maintained using Doxygen.

If you use MLAPI for your applications, please let us know by writing an e-mail to the ml developers. Please also cite MLAPI using the following bibtex entry:

@Article{Sala:2006:OOF,
  author =       "Marzio Sala",
  title =        "An Object-Oriented Framework for the Development of Scalable Parallel Multilevel Preconditioners",
  journal =      "{ACM} Transactions on Mathematical Software",
  volume =       "32",
  number =       "3",
  month =        sep,
  year =         "2006",
  accepted =     "4 November 2005",
}
