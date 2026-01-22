# trilinos.github.io

Github website platform for Trilinos organization


# Instructions on editing and maintaining repos

## Running locally

Running `bundle exec jekyll serve` test website locally before pushing to Github repo

## Edit top navigation

Material on top navigation is located in `_data/topnav.yml`
Items on top navigation are listed in order with **title** and **url**
_Note_: Careful on indentation. Wrong indentation leads to build page errors.

## Edit home page

Home page is in **index.md**

## Edit contents

All the contents are in **pages** directory and located in appropriate sub_folders correspond to the website
All the contents are written in `markdown` and editable.

___

More details on update website can be found [here](https://cse-software.github.io/Howto/TrilinosMaintenance.html) 

 


# Structure

We are using so-called collections to manage packages, package areas, capabilities and capability areas.
These are collected in the folders `_packages`, `_packageAreas`, `_capabilities` and `_capabilityAreas`.
Each folder contains a file `0_fileFormat.txt` with a description of the metadata fields.
