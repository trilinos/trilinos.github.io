---
title: Adding CXX11 Dependencies for Packages
permalink: about/CXX11/add_CXX11.html
folder: about
---

## How to define optional and required dependencies on C++11 for packages/subpackages

Trilinos has the CMake option `Trilinos_ENABLE_CXX11`. It is ON if C++11 is enabled (which is the default), and OFF otherwise.

### A) How to define an optional dependency on C++11:

A Trilinos package that wants to depend *optionally* on C++11 has to just change two lines in their CMake-related code. This is demonstrated in the TeuchosCore subpackage.

#### A.1) Add the package-specific #cmakedefine HAVE_<PACKAGE_UC>_CXX11 to the <Package>_config.h.in file.

For TeuchosCore the names are:

*   **<PACKAGE_UC>** = **TEUCHOSCORE** (“UC” stands for “upper case.” This is the upper-case version of the (sub)package name used in C/C++ macros.)
*   **<Package>** = **TeuchosCore** (regular (sub)package name as known by TriBITS)

the file is:

`Trilinos/packages/teuchos/core/cmake/TeuchosCore_config.h.in`

and the line is:

`#cmakedefine HAVE_TEUCHOSCORE_CXX11`

#### A.2) Set HAVE_<PACKAGE_UC>_CXX11 to ${Trilinos_ENABLE_CXX11} in CMakeLists.txt *before* configuring the <Package>_config.h file.

For TeuchosCore, the line of code is:

`SET(HAVE_TEUCHOSCORE_CXX11 ${${PROJECT_NAME}_ENABLE_CXX11})`

set in the file:

`Trilinos/packages/teuchos/core/src/CMakeLists.txt`

WARNING: Set this CMake variable **`HAVE_<PACKAGE_UC>_CXX11`** (i.e. `HAVE_TEUCHOSCORE_CXX11`) ****BEFORE**** you call:

`TRIBITS_CONFIGURE_FILE(${PACKAGE_NAME}_config.h`)

#### A.3) Put in #ifdefs in your code for C++11 support based on the C++ macro HAVE_<PACKAGE_UC>_CXX11.

For TeuchosCore, an example is in the file:

`Trilinos/packages/teuchos/core/test/MemoryManagement/RCP_UnitTests.cpp`

which shows the lines:

`#ifdef HAVE_TEUCHOSCORE_CXX11  
#include "Teuchos_RCPStdSharedPtrConversions.hpp"  
#endif  
...  
#ifdef HAVE_TEUCHOSCORE_CXX11  
TEUCHOS_UNIT_TEST( std_shared_ptr, nonnull_is_null )  
{  
...  
}  
...  
#endif // HAVE_TEUCHOSCORE_CXX11`

If there are any questions, send email to [trilinos-framework@software.sandia.gov](mailto:trilinos-framework@software.sandia.gov).

### B) How to define a required dependency on C++11:

Once we get the okay, and Kokkos and Tpetra (and selected other packages) are allowed to have a required dependency on C++11, then these packages just need to ‘CXX11’ to the list to the [TRIBITS_PACKAGE_DEFINE_DEPENDENCIES()](https://tribits.org/doc/TribitsDevelopersGuide.html#tribits-package-define-dependencies) macro call:

`TRIBITS_PACKAGE_DEFINE_DEPENDENCIES(  
...  
LIB_REQUIRED_TPLS ... CXX11 ...  
)`

This will have the effect that if someone configures with:

`-D Trilinos_ENABLE_CXX11=ON`

then it will automatically disable packages like Kokkos, Tpetra, and all others downstream from them that have a required dependence on on them (just like it would if you were to disable BLAS and that woiuld take out TeuchosNumerics and all downstream dependencies).

If a package is explicitly enabled that requires C++11, then it will either gracefully disable that package or will result in a configure error depending on the value of `Trilinos_DISABLE_ENABLED_FORWARD_DEP_PACKAGES` as described [here](https://tribits.org/doc/TribitsDevelopersGuide.html#disables-trump-enables-where-there-is-a-conflict).

This dummy ‘CXX11’ TPL will be added to TriBITS proper and snapshotted to Trilinos *before* Trilinos is allowed to make C++11 required.

### FAQ:

**Q:** Why can’t each individual C++ package decide to support C++11 or not?

**A:** Some C++ standard library classes and functions, like std::vector, changed interfaces in C++11\. Mixing C++98 and C++11 may pull in inconsistent definitions of these classes or functions, [resulting in build errors or other troubles](http://stackoverflow.com/questions/6494101/any-issues-with-mixing-libraries-with-and-without-std-c0x). Behavior varies between compilers and systems, and may be very hard to debug. Thus, it’s better if a project commits fully either to C++98 or C++11.

**Q:** How long do we need this guards for CXX11 ?

**A**: Until mid-March in some cases. When Sierra is ready for CXX11 we can make it required.

If a package has a required dependence on Kokkos or Tpetra, then it can remove the include guards in mid-March. If a package does ***not*** have a required dependence on Kokkos or Tpetra, then the include guards might need to stay for an unknown amount of time depending on the users of the package (see below).

**Q**: After mid-March, some packages may REQUIRE CXX11 in order to build. Do we need to tell CMake that a package REQUIREs CXX11 so that CMake can abort if a users requests such a package but disables CXX11? If so, how does a package developer specify this requirement?

**A**: Yes, there is an experimental feature in TriBITS to handle CXX11 as a TPL. It is in the collaboration branch cxx11_as_tpl. Once C++11 can be required by Kokkos and Tpetra, then this feature will be merged into TriBITS master and snapshotted to Trilinos. Then Kokkos and Tpetra (and other packages) can define a required dependency on the dummy TPL ‘CXX11’ and they will be automatically disabled when someone sets `Trilinos_ENABLE_CXX11=OFF`.

If the package was explicitly enabled and `Trilinos_ENABLE_CXX11=OFF`, configure will fail if CXX11 is a required dependency. If the package was not enabled explicitly, it will be disabled.

**Q**: Are there some Trilinos packages that will not be allowed to REQUIRE CXX11, even after Sierra enables CXX11?

**A**: Yes, Teuchos will not, because of the needs of Xyce and possibly also Dakota. This list may include other packages, but NOT Kokkos, Tpetra, or packages downstream of Tpetra. Kokkos, Tpetra, and its downstream packages WILL require CXX11 when Sierra requires it.