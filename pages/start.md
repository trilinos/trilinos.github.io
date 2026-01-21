---
title: Getting Started
permalink: getting_started.html
show_sidebar: true
sidebar: nav
keywords: Getting Started with Trilinos, Trilinos installation guide, Trilinos prerequisites, Trilinos build instructions, Trilinos troubleshooting, Trilinos modular architecture, Trilinos packages, Trilinos source code, Trilinos prebuilt packages, Trilinos Spack package, Trilinos GitHub repository, Trilinos support, Trilinos FAQ, Trilinos examples, Trilinos tutorials, Trilinos basic concepts, Trilinos linear algebra, Trilinos finite element assembly, Trilinos distributed computing, Trilinos parallel computing, Trilinos MPI support, Trilinos CMake configuration, Trilinos compilers, Trilinos libraries, Trilinos performance optimization, Trilinos Kokkos ecosystem, Trilinos Tpetra, Trilinos Panzer, Trilinos debugging, Trilinos development tools, Trilinos numerical analysis, Trilinos scalability, Trilinos interoperability, Trilinos computational simulations, Trilinos distributed memory systems, Trilinos shared memory systems, Trilinos parallel execution, Trilinos distributed data management, Trilinos example code
---


## Installation Guide

### Prerequisites
Before installing Trilinos, ensure the following dependencies are available:
- **CMake**: Required for configuring the build system.
- **Compilers**: Compatible C++ compilers such as GCC, Clang, or Intel.
- **MPI**: For parallel computing support (optional but recommended).
- **Libraries**: Additional libraries like BLAS, LAPACK, and Boost may be required depending on the configuration.

### Download Trilinos
You can download Trilinos from the [official repository](https://github.com/trilinos/Trilinos) or the [Download page](download.html).

### Build Instructions

Follow these steps to configure, build, and install Trilinos:

1. Clone the Trilinos repository:
   ```bash
   git clone https://github.com/trilinos/Trilinos.git
   cd Trilinos
   ```

2. Configure with CMake:
   ```bash
   mkdir build
   cd build
   cmake .. -DCMAKE_INSTALL_PREFIX=/path/to/install
   ```
   - Replace /path/to/install with the desired installation directory.
   - Add additional CMake options to enable specific packages or features.

3. Build and install:
   ```bash
   make -j4
   make install
   ```
   - Use -jN to specify the number of parallel build threads (N).

For detailed instructions, refer to the [Quick configure, build and install hints for Trilinos](https://github.com/trilinos/Trilinos/blob/master/INSTALL.rst).

### Prebuilt Packages

If you prefer not to build Trilinos from source, you can explore prebuilt binaries or package managers like [Spack Trilinos Package](https://packages.spack.io/package.html?name=trilinos).

### Troubleshooting

- Common installation issues and solutions.
- FAQ or support forum.

- Common Issues: Check for missing dependencies, incorrect compiler versions, or MPI configuration errors.
- Support: Submit an issue on the [Trilinos GitHub Issues page](https://github.com/trilinos/Trilinos/issues).


---

## Getting Started with Trilinos
### Basic Concepts

- Overview of Trilinos: Learn about Trilinos' modular architecture and how packages interact to solve complex problems. See [Overview of Trilinos](about.html#trilinos-project).
- Modular Architecture: Trilinos is composed of individual packages, each designed for specific tasks (e.g., Tpetra for linear algebra, Panzer for finite element assembly). These packages can be used independently or combined to build custom solutions.


### Simple Example

A simple example demonstrating basic Trilinos functionality:
```cpp
#include <iostream>
#include <Tpetra_Core.hpp>
#include <Tpetra_Vector.hpp>

int main(int argc, char* argv[]) {
    Tpetra::ScopeGuard tpetraScope(&argc, &argv);           // Initialize Tpetra (and MPI if enabled)

    auto comm = Tpetra::getDefaultComm();                   // Get the default communicator (MPI or serial)

    const Tpetra::global_size_t globalSize = 10;            // Define the global size of the vector

    Tpetra::Map<> map(globalSize, 0, comm);                 // One-to-one distribution of elements across processes)

    Tpetra::Vector<> vec(map);                              // Create a Tpetra Vector

    vec.putScalar(1.0);                                     // Fill the vector with scalar value 1.0

    vec.sync<Kokkos::HostSpace>();                          // Ensure data is synchronized to the host
    auto localView = vec.getLocalView<Kokkos::HostSpace>(); // Access local data

    // Print local values for each process
    for (size_t i = 0; i < localView.extent(0); ++i) {
        std::cout << "Process " << comm->getRank() << ", vec[" << map.getGlobalElement(i) 
                  << "] = " << localView(i) << std::endl;
    }

    return 0;
}
```

This example demonstrates:

- Initializing Trilinos and MPI.
- Creating and manipulating a distributed vector using Tpetra.
