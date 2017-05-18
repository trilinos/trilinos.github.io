---
title: FAQ for Contributing to trilinos.org
permalink: faq_for_contributing_to_trilinos_org.html
folder: community
---

Below are some frequently asked questions about adding to trilinos.org web content.

[Q: I would like to contribute to trilinos.org. How do I get started?](#GetStarted)  
[Q: I need to add/update metadata. Where can I make the changes?](#Metadata)  
[Q: What metadata is defined for the Trilinos-level?](#TrilinosMetadata)  
[Q: What metadata must be defined for each package homepage?](#PackageMetadata)  
[Q: What metadata must be defined for each package child page?](#PackageChildMetadata)  
[Q: How do I add a new package homepage?](#AddPackageHomepage)  
[Q: How do I add a new package child page?](#AddPackageChildPage)  
[Q: Other than adding new pages, what do I need to do when adding a new package to trilinos.org?](#AddPackageOther)

<a name="GetStarted"></a>**Q: I would like to contribute to trilinos.org. How do I get started?**

**A:** (Note this question addresses contributing to the trilinos.org website. Information about contributing to the Trilinos Project can be found on the [Contribute](contribute.html) page.) If you are part of the Trilinos development team, after you register for an account (see “Register” in the footer menu), your account should be granted elevated permissions by an administrator. If you need the permission elevation process expedited, send a note to trilinos-framework@software.sandia.gov. If you are not part of the Trilinos development team, we are in the process of figuring out how to accept your contributions. If you are interested in contributing to the site, please contact trilinos-framework@software.sandia.gov.

<a name="Metadata"></a>**Q: I need to add/update metadata. Where can I make the changes?**

**A:** All metadata is associated with a specific WordPress page. To view the metadata associated with a page, or add new metadata, click on “Screen Options” in the upper right when you are editing the page. Then click on “Custom Fields”. The metadata will then appear in the custom Fields area near the bottom of the page.

<a name="TrilinosMetadata"></a>**Q: What metadata is defined for the Trilinos-level?**

**A:** All of the metadata defined at the Trilinos-level is currently associated with the “Download” page. This metadata includes:

*   Current Major Release -- The most recent major release expressed in the form X.Y, e.g., 12.0.
*   Current Minor Release -- The most recent minor release expressed in the form X.Y.Z, e.g., 12.0.1.
*   MajorRelease -- One key/value pair for each Trilinos major release (since 4.0) with the common key “MajorRelease” and a value in the same form as “Current Major Release”.

<a name="PackageMetadata"></a>**Q: What metadata must be defined for each package homepage?**

**A:** Some pieces of metadata are expected to be associated with each package homepage. A few pieces are conditionally required.

*   Current Release Status -- Package release status. possible values include “future”, “current”, “previous”. This piece of metadata is not yet used.
*   Package Contact -- Contact email(s), and optionally name(s). Sometimes a specific developer, sometimes a developer mail list.
*   Package Dev Doxygen -- (Required only if “Package Doxygen” = “t”.) Does the package support a current development branch Doxygen version? (“t” or “f” -- denoting true or false.)
*   Package Doxygen -- Does the package currently, or has the package in the past, supported Doxygen Documentation? (“t” or “f”)
*   Package First Doxygen Release -- (Required only if “Package Release Doxygen” = “t”.) What was the first major Trilinos release for which the package provided Doxygen documentation? Value expressed in the same format as “Current Major Release” (see answer to previous question).
*   Package Last Doxygen Release -- (Required only if “Package Release Doxygen” = “t”.) What was the last major Trilinos release for which the package provided Doxygen documentation? If Doxygen is currently still supported for the package, and the package is still part of the Trilinos release, use “NA”. Value expressed in the same format as “Current Major Release” (see answer to previous question).
*   Package Name -- The name of the package as it is commonly printed, e.g., “Epetra”.
*   Package Release Doxygen -- (Required only if “Package Doxygen” = “t”.) Does the package currently, or has the package in the past, supported Doxygen Documentation for Trilinos releases? (“t” or “f”)
*   Repository Package Name -- The name of the package as it appears in the repository, e.g. Trilinos/packages/<package_name>, e.g. “epetra”.

<a name="PackageChildMetadata"></a>**Q: What metadata must be defined for each package child page?**

**A:** Each package child page must include a single piece of metadata to associate the page with the metadata of the package homepage. This is used, for example, to construct the right side menu items specific to the package. The required metadata is:

*   Package Home ID -- The page ID for the package home page. This can be found by clicking on “Get Shortlink” near the top of the page when editing the package homepage. For example “501”.

<a name="AddPackageHomepage"></a>**Q: How do I add a new package homepage?**

**A:** Prior to creating a new package homepage, please contact the [Trilinos Framework team](mailto:trilinos-framework@software.sandia.gov). Creating a new package homepage is the same as creating any WordPress page on the Trilinos site, except:

1.  Under Page Attributes -> Parent select “Packages”.
2.  Under Sidebars -> Main Sidebar select “Package Sidebar”.
3.  Define the metadata for a package homepage as described above.

<a name="AddPackageChildPage"></a>**Q: How do I add a new package child page?**

**A:** Creating a new package homepage is the same as creating any WordPress page on the Trilinos site, except:

1.  Under Page Attributes -> Parent select the package homepage, or the package child page that should be the immediate parent of the new child page.
2.  Under Sidebars -> Main Sidebar select “Package Sidebar”.
3.  Define the metadata for a package child page as described above.

<a name="AddPackageOther"></a>**Q: Other than adding new pages, what do I need to do when adding a new package to trilinos.org?**

A: New packages should be mentioned on:

*   [http://trilinos.github.io/packages/](packages.html)
*   [http://trilinos.github.io/capabilities/](capability.html)
*   If the license for the package is anything other than BSD (including if any additional third-party licenses are included in the code), the information needs to be added to the [licenses](license.html) page also. Contact [trilinos-framework@software.sandia.gov](mailto:trilinos-framework@software.sandia.gov) for assistance.