---
title: User experience
permalink: user_experience.html
folder: capabilities
---

## Trilinos User Experience Capability Area

> [Introduction](#Intro)  
> [Application Support](#AppSupport)  
> [Documentation, Examples and Tutorials](#DocExTut)  
> [Web Site Design](#WebSiteDesign)  
> [Simplified Layers and Skins](#LayersAndSkins)  
> [Human/Computer Interaction](#HCI)

<a name="Intro"></a>

* * *

## Introduction

The User Experience capability area is aimed at improving the ability of developers who use Trilinos to use it effectively and efficiently. Our goals are to make documentation, examples, and tutorials clear, accurate and easy to find; to improve interfaces; and to foster relationships between Trilinos and application developers.

<a name="AppSupport"></a>

* * *

## Application Support

Sub-area lead: Jim Willenbring

In the context of Trilinos UX, Application Support refers to forging specific relationships between representatives of applications that use Trilinos, and appropriate Trilinos developers who will act as advocates for their assigned applications. The developers who participate in this sub-area are responsible for determining what capabilities users need, and devising strategies for prioritizing and implementing those capabilities.

<a name="DocExTut"></a>

* * *

## Documentation, Examples and Tutorials

Sub-area lead: Mark Hoemenn

The Trilinos community provides tutorials in several forms. Expert-led, hands-on tutorials are provided two or three times a year at conferences and the Trilinos Users Group (TUG) meeting; videos of these tutorials are sometimes produced (especially at TUG), and these videos are made available on the web; some heavily commented coding examples are provided; the Didasko package is intended to be a tutorial package. While these sets of tutorials are well intentioned, they often fall short of helping the intended audience achieve their goals. A common goal of users, not currently addressed by tutorials, is to improve performance of codes that use Trilinos. Improving the quality of tutorials, for both users and developers, is an important UX goal. The primary Trilinos documentation effort is through Doxygen, which automatically generates a reference manual for each Trilinos package, covering the classes and functions of that package. Depending on the level of detail provided by the developers, these reference manuals are invaluable, but they are insufficient for new users. **The most important form of documentation may in fact be examples and tutorials**.

Forcing every Trilinos package to maintain a Users Manual in addition to the Doxygen Reference Manual is probably beyond the scope of the UX capability area. And unlike the Reference Manual, a Users Manual is much harder to keep up-to-date. If done well enough, the tutorial examples could serve in place of a Users Manual, with the added benefit that the Trilinos testing infrastructure will help developers keep their examples current.

<a name="WebSiteDesign"></a>

* * *

## Web Site Design

Sub-area lead: Dena Vigil

The Trilinos web site has traditionally been a set of static web pages coupled to Doxygen-generated reference manuals for each package. This model for supporting a web site does not scale well to the current size of Trilinos and leads to stale or incorrect information. The UX team is currently migrating the Trilinos web site to a modern content management system. When completed, we intend to provide current and accurate information, forums, extensive search capabilities, and much more.

<a name="LayersAndSkins"></a>

* * *

## Simplified Layers and Skins

Sub-area lead: Bill Spotz

Simplified layers are higher-level packages or codes that attempt to simplify the task of solving a linear, nonlinear, or optimization problem. Skins are interfaces to Trilinos from other languages, such as C, Fortran, Python, etc. Both simplified layers and skins increase interoperability, either between or among packages or languages.

Package | Description
--------| -----------
[Stratimikos](http://trilinos.org/packages/stratimikos/) | Single interface to all Trilinos linear solver capabilities
[Piro](http://trilinos.org/packages/piro) | Single interface to all Trilinos nonlinear solver capabilities
[PyTrilinos](http://trilinos.org/packages/pytrilinos/) | Python interfaces to selected Trilinos packages and classes
[ForTrilinos](http://trilinos.org/packages/fortrilinos/) | Fortran interfaces to selected Trilinos packages and classes
CTrilinos | C interfaces to selected Trilinos packages and classes

* * *

## Human/Computer Interaction

Sub-area lead: vacant

This sub-area covers any and all aids aimed at improving the learning curve for new developers or users and increasing the efficiency of seasoned developers or users.