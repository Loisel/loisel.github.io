---
title: "colorview2d"
date: 2022-12-20T15:11:59+01:00
startdate: 2015-01-20
draft: false
description: "Extendible 2D color plotting tool for 3D data."
image: "screenshot.png"
giturl: "https://github.com/Loisel/colorview2d"
languages: "Python"
technologies: "Numpy, matplotlib, wxPython"
---
<img class="img-fluid rounded float-start me-3" src="screenshot.png">

I developed `colorview2d` during my PhD to easily plot and prepare 3D data sets from measurements
for a first screening. Being able to quickly play with colorscales and ranges, apply filters and
extract arrays of linecuts is very useful to extract important features early on during a measurment.

The initial version supplied a [wxPython](https://www.wxpython.org/) GUI but it turned out that
the integration of GUI and logic was a bad idea. I removed the GUI from the package at some point
with the aim to provide a separate package for the GUI. I never did.

The version available on [sourceforge](https://sourceforge.net/projects/colorview2d/) still provides
the GUI and even ships a Windows (7!) binary.

