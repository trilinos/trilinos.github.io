---
title: Trilinos Home Page
keywords: homepage scientific libraries parallel computing
permalink: index.html
---


## Welcome to the Trilinos Project Home Page

The Trilinos Project is a community of developers, users and
<a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.user_developer}}">user-developers</a>
focused on collaborative creation of algorithms and enabling technologies within an object-oriented software framework for the solution of large-scale, complex multi-physics engineering and scientific problems on new and emerging high-performance computing (HPC) architectures.

Trilinos is organized around fundamental software elements called <a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.trilinos_package}}">packages</a>.  The Trilinos package architecture enables simultaneous development of many new capabilities in a federated system.  Each package has its own name and identity within the research community, giving the package team recognition outside of Trilinos itself.

## What Trilinos Can Do: Trilinos Capability Areas

[The Trilinos Capability Area homepage](capability-areas.html) organizes Trilinos capabilities into nine collections of functionality and describes
which packages are relevant to each area. This discussion is especially useful for new Trilinos users.

## Trilinos is on GitHub

The [primary Trilinos repository](https://github.com/trilinos/Trilinos)
is now hosted on GitHub. This allows users and potential developers greater access to Trilinos source code.

## TUG 2019

[The 2019 Trilinos User Group Meeting (TUG)](https://trilinos.github.io/trilinos_user-developer_group_meeting_2019.html) is  held in October in Albuquerque.

## Trilinos v12 Code Deprecation

Trilinos announces 37 code deprecations in 16 packages.  Code removal from the Trilinos develop branch will begin November 15, 2019.  See the [Trilinos v12 Deprecation Document](https://github.com/trilinos/Trilinos/wiki/Trilinos_v12_code_deprecation.pdf) for details.

## Trilinos 12.12 Release

Trilinos 12.12 is now available for [download](download.html).
The 12.12 release uses a [CMake](https://cmake.org/)
build system, which requires CMake version 2.8.11 or greater.
Instructions for building Trilinos 10.0 and later are available
[here](pdfs/Trilinos10.12Tutorial.pdf).

## Trilinos Packages

Each Trilinos package is a self-contained, independent piece of software with its own set of requirements,
its own development team and group of users. Because of this, Trilinos itself is designed to respect the autonomy of packages.
Trilinos offers a variety of ways for a particular package to interact with other Trilinos packages.
It also offers a set of tools that can assist package developers with builds across multiple platforms,
generating documentation and regression testing across a set of target platforms.
At the same time, what a package must do to be called a Trilinos package is minimal, and varies with each package.
