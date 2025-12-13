---
title: About Trilinos
permalink: about.html
show_sidebar: true
sidebar: nav
keywords: About Trilinos, Trilinos Project, Scientific computing framework, Open-source software for HPC, High-performance computing tools, Modular software framework, Scalable scientific computing, Parallel computing architectures, Distributed memory systems, Multicore computing, GPU-based computing, Kokkos ecosystem, Software development philosophy, Interoperability in scientific computing, Scalability in engineering applications, Trilinos packages, Robust algorithms for HPC, Engineering and scientific applications, Performance portability, Configure Trilinos, Build Trilinos, Install Trilinos, TriBITS, CMake, Reference Guide, Software Development, Mathematical Software, Linear solvers, Nonlinear solvers, Eigensystems, Optimization problems, Uncertainty quantification, Sandia National Laboratories, Federated software development model, Modularity in software, Interoperability in Trilinos, Scalability in HPC, Accessibility in scientific computing, Rigorous software engineering practices, Testing in software development, Documentation in software development, Lean/agile lifecycle model, MPI, OpenMP, Pthreads, TBB, CUDA, HIP, SYCL, Vectorized computing, Kokkos abstractions, Parallel execution, Memory management, R&D 100 Award, SC2004 HPC Software Challenge Award, Awards and recognition, High Performance Software Foundation (HPSF), Linux Foundation, Trilinos governance, Trilinos Technical Steering Committee (TSC), Trilinos charter, Trilinos code of conduct, Trilinos community, Trilinos citation guidelines, Trilinos BibTeX entry, Trilinos package citation, Trilinos logos, Trilinos feedback, Trilinos support, Trilinos Homepage, Trilinos philosophy, Trilinos software engineering practices, Trilinos documentation, Trilinos user guide, Trilinos contacts, Trilinos feedback email, Trilinos scalability, Trilinos interoperability, Trilinos accessibility, Trilinos awards, Trilinos recognition, Trilinos targeted platforms, Trilinos accelerators, Trilinos vectorization, Trilinos performance portability, Trilinos user-developers, Trilinos developers, Trilinos users, Trilinos community-driven development, Trilinos collaboration, Trilinos testing, Trilinos maintainability, Trilinos adaptability, Trilinos emerging HPC architectures, Trilinos leadership-class supercomputers, Trilinos engineering applications, Trilinos scientific applications
---

The Trilinos Project is a community-driven, open-source software framework designed to enable scalable scientific computing for complex engineering and scientific problems. It provides a modular collection of reusable libraries, known as packages, that support the development of high-performance algorithms for solving linear and nonlinear systems of equations, eigensystems, optimization problems, and uncertainty quantification. Trilinos is widely used in applications requiring robust and scalable solutions across diverse hardware architectures, from desktops to leadership-class supercomputers.

Originally developed at Sandia National Laboratories in 2001, Trilinos has grown significantly and now encompasses nearly 40 packages, each contributing unique capabilities. The project emphasizes scalability, interoperability, and accessibility, fostering collaboration among developers and users.

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

### Software Development Philosophy
Trilinos is built on a federated model of software development, emphasizing collaboration, modularity, and autonomy. Each package is developed by a focused team, allowing for specialization and innovation while adhering to common standards for interoperability and software quality.

Key principles include:
1. **Modularity**: Packages are semi-autonomous, with well-defined capabilities and interfaces.
2. **Interoperability**: Designed to work seamlessly together, enabling users to combine capabilities algorithmically.
3. **Scalability**: Optimized for parallel computing environments, ensuring efficient performance as problem sizes and processor counts increase.
4. **Accessibility**: Available across major programming environments (C++, Fortran, Python) and portable across diverse hardware architectures.

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

## Governance and Community

Trilinos is part of the High Performance Software Foundation (HPSF) and the Linux Foundation. Governance is managed through the following resources:
- [Introduction](https://github.com/trilinos/governance/tree/main?tab=readme-ov-file#trilinos)
- [Governance](https://github.com/trilinos/governance/blob/main/GOVERNANCE.md)
- [Charter](https://github.com/trilinos/governance/blob/main/Trilinos_Technical_Charter_6-6-2024.pdf)
- [Code of Conduct](https://github.com/trilinos/governance/blob/main/code-of-conduct.md)

---

## Citing Trilinos

If you are using Trilinos, please cite our software in your publications. Below is a suitable BibTeX entry:

```bibtex
@Manual{trilinos-website,
title = {The {T}rilinos {P}roject {W}ebsite},
author = {The {T}rilinos {P}roject {T}eam}},
year = {2020 (accessed May 22, 2020)},
url = {https://trilinos.github.io}
}
```

For specific packages, you may cite their individual webpages. For example:
```
@Manual{muelu-website,
title = {The {M}uelu {P}roject {W}ebsite},
author = {The {M}uelu {P}roject {T}eam}},
year = {2020 (acccessed May 22, 2020)},
url = {https://trilinos.github.io/muelu.html}
}
```

---

## Trilinos Logos

For Trilinos logos, visit the [Trilinos Logos Repository](https://github.com/trilinos/Logos).

## Contacts

For support, visit the [Support page](support.html).

## Feedback

We value your feedback! Please share your <a class="email" title="Submit feedback" href="#" onclick="javascript:window.location='mailto:{{site.feedback_email}}?subject={{site.feedback_subject_line}} Feedback&body=I have some feedback about ... %0A';"><i class="fa fa-envelope-o"></i> thoughts or suggestions</a> about the Trilinos Homepage.

