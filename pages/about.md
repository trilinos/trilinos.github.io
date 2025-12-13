---
title: About Trilinos
permalink: about.html
show_sidebar: true
sidebar: nav
keywords: About Trilinos, Trilinos Project, Scientific computing framework, Open-source software, High-performance computing (HPC), Modular software framework, Scalable scientific computing, Parallel computing, Distributed memory systems, Multicore computing, GPU-based computing, Kokkos ecosystem, Software development philosophy, Interoperability, Scalability, Trilinos packages, Robust algorithms, Engineering applications, Scientific applications, Performance portability, Configure Trilinos, Build Trilinos, Install Trilinos, TriBITS, CMake, Linear solvers, Nonlinear solvers, Eigensystems, Optimization problems, Uncertainty quantification, Sandia National Laboratories, Federated software development model, Rigorous software engineering practices, Testing, Documentation, Lean/agile lifecycle model, MPI, OpenMP, Pthreads, TBB, CUDA, HIP, SYCL, Vectorized computing, Kokkos abstractions, Parallel execution, Memory management, R&D 100 Award, SC2004 HPC Software Challenge Award, Awards and recognition, High Performance Software Foundation (HPSF), Linux Foundation, Trilinos governance, Trilinos Technical Steering Committee (TSC), Trilinos charter, Trilinos code of conduct, Trilinos community, Trilinos citation guidelines, Trilinos BibTeX entry, Trilinos logos, Feedback, Support, Scalability in HPC, Accessibility, Emerging HPC architectures, Leadership-class supercomputers
---

The Trilinos Project is a community-driven, open-source software framework designed to enable scalable scientific computing for complex engineering and scientific problems. It provides a modular collection of reusable libraries, known as packages, that support the development of high-performance algorithms for solving linear and nonlinear systems of equations, eigensystems, optimization problems, and uncertainty quantification. Trilinos is widely used in applications requiring robust and scalable solutions across diverse hardware architectures, from desktops to leadership-class supercomputers.

Originally developed at [Sandia National Laboratories](https://www.sandia.gov/) in 2001, Trilinos has grown significantly and now encompasses nearly 40 packages, each contributing unique [capabilities](capabilities.html). The project emphasizes scalability, interoperability, and accessibility, fostering collaboration among developers and users.

In May 2024, Trilinos became part of the [Linux Foundation](https://www.linuxfoundation.org/) and [High Performance Software Foundation](https://hpsf.io/) (HPSF), marking a significant milestone in its commitment to fostering open-source collaboration, enhancing [governance](community.html#trilinos-and-hpsf) practices, and advancing scalable scientific computing solutions for modern high-performance computing (HPC) architectures. This partnership ensures long-term sustainability and broader community engagement for the Trilinos Project.

---

## Key Features

- **Parallel Computing Support**: Optimized for high-performance computing environments, supporting MPI, OpenMP, and other parallel execution models.
- **Wide Range of Solvers**: Includes linear, nonlinear, eigenvalue, and optimization solvers to address diverse computational challenges.
- **Modular Architecture**: Composed of individual packages that can be used independently or integrated seamlessly to build custom solutions.
- **Advanced Tools**: Offers capabilities for discretization, mesh manipulation, automatic differentiation, and uncertainty quantification.
- **Performance Portability**: Achieved through the Kokkos ecosystem, enabling efficient execution across distributed, multicore, accelerator, and vectorized computing devices.

---

## Who Should Use Trilinos?

Trilinos is ideal for:
- Researchers and engineers working on scientific computing problems.
- Developers building scalable applications for high-performance computing environments.
- Teams seeking modular and extensible tools for numerical analysis and simulation.

---

## Trilinos Philosophy

Trilinos is built on a federated model of software development, emphasizing collaboration, modularity, and autonomy. Each package is developed by a focused team, allowing for specialization and innovation while adhering to common standards for interoperability and software quality.

Key principles include:
- **Modularity**: Packages are semi-autonomous, with well-defined capabilities and interfaces.
- **Interoperability**: Designed to work seamlessly together, enabling users to combine capabilities algorithmically.
- **Scalability**: Optimized for parallel computing environments, ensuring efficient performance as problem sizes and processor counts increase.
- **Accessibility**: Available across major programming environments (C++, Fortran, Python) and portable across diverse hardware architectures.

The Trilinos philosophy also emphasizes rigorous software engineering practices, including thorough testing, comprehensive documentation, and a lean/agile lifecycle model. This ensures Trilinos remains robust, maintainable, and adaptable to emerging challenges in scientific computing.

---

## Targeted Platforms and Architectures

Trilinos supports all major parallel computing architectures:
- **Distributed Memory Systems**: Using MPI for communication.
- **Multicore Architectures**: Leveraging OpenMP, Pthreads, and TBB for shared-memory parallelism.
- **Accelerators**: Supporting GPU-based systems through CUDA, HIP, and SYCL, as well as emerging hardware technologies.
- **Vectorization**: Optimized for vectorized computing to maximize performance on modern processors.

Performance portability is achieved through the Kokkos ecosystem, which provides abstractions for parallel execution and memory management.

---

## Awards and Recognition

### R&D 100 Award (2004)
Trilinos received a prestigious R&D 100 Award in 2004, recognizing it as one of the "100 most technologically significant products introduced in the past year." 

- [R&D Magazine: R&D 100 Awards Software](http://www.rdmag.com/award-winners/2004/08/pearl-real-gem)
- [Sandia National Labs News Center: Sandia wins two R&D 100 Awards](https://software.sandia.gov/trilinos/TrilinosRD100Newsnote.pdf)
- [New Mexico Business Weekly: New Mexico firms, labs earn R&D awards](http://www.bizjournals.com/albuquerque/stories/2004/07/12/daily6.html)

### SC2004 HPC Software Challenge Award
Trilinos was awarded one of two HPC Software Challenge Awards at SC2004 for its commitment to professional software engineering practices and processes. 

- [SC2004 HPC Software Challenge Details](http://www.sc-conference.org/sc2004/hpc_challenge.html)
- [SC2004 Conference Award Winners](http://www.sc-conference.org/sc2004/awards.html)

---

## Citing Trilinos

If you are using Trilinos, please cite our software in your publications. Below is a suitable BibTeX entry:

```bibtex
@Manual{trilinos,
  title        = {The {T}rilinos {P}roject},
  author       = {The Trilinos Project Team},
  organization = {Linux Foundation / High Performance Software Foundation},
  year         = {2026},
  url          = {https://trilinos.github.io},
  note         = {Accessed: January 8, 2026},
}
```

For specific packages, you may cite their individual webpages. For example:
```
@Manual{muelu,
  title  = {The {M}uelu {P}roject},
  author = {The {M}uelu {T}eam}},
  year   = {2026},
  url    = {https://trilinos.github.io/docs/muelu/index.html}
  note   = {Accessed: January 8, 2026},
}
```

---

## License and Copyright

Trilinos is a collection of open-source packages licensed under multiple open-source licenses, primarily BSD 3-Clause and LGPL. License and copyright information is provided at the root of the Trilinos repository and within individual package directories.

**BSD 3-Clause License**

<pre>
Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

1. Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.
 
2. Redistributions in binary form must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.
 
3. Neither the name of the copyright holder nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.
 
THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
“AS IS” AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS
FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE
COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT,
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN
ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.
</pre>

**NTESS Copyright Statement**

<pre>
           Trilinos: An Object-Oriented Solver Framework
                      Copyright (2001) NTESS
 
Copyright 2001 National Technology & Engineering Solutions of Sandia,
LLC (NTESS). Under the terms of Contract DE-NA0003525 with NTESS, the
U.S. Government retains certain rights in this software.
</pre>

For more information for Trilinos developers, refer to [Guidance on Copyrights and Licenses](https://github.com/trilinos/Trilinos/wiki/Guidance-on-Copyrights-and-Licenses).

---

## Trilinos Logos

For Trilinos logos, visit the [Trilinos Logos Repository](https://github.com/trilinos/Logos).

## Contacts

For support, visit the [Support page](support.html).

## Feedback

We value your feedback! Please share your <a class="email" title="Submit feedback" href="#" onclick="javascript:window.location='mailto:{{site.feedback_email}}?subject={{site.feedback_subject_line}} Feedback&body=I have some feedback about ... %0A';"><i class="fa fa-envelope-o"></i> thoughts or suggestions</a> about the Trilinos Homepage.

