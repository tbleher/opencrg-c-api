OpenCRG
=======

[OpenCRG](https://en.wikipedia.org/wiki/OpenCRG) is a library and file format
used to describe road surfaces, enabling applications such as simulation of
tires and vibrations during driving.


This Repository
===============

This repository contains the C API for reading OpenCRG files, with some
bugfixes and improvements relative to release 1.1.2 which was previously
published on [opencrg.org](http://opencrg.org/).

The repo is based on [hlrs-vis](https://github.com/hlrs-vis/opencrg), which
helpfully collected historical releases of OpenCRG.

Building OpenCRG C API
======================

Use `cmake` to build. Example invocation:

    mkdir build
    cd build
    cmake ..
    cmake --build .

