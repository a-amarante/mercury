Mercury Binary Package v6.4bin
===============================
The Mercury binary package version created by John E. Chambers
-------------------------------------------------

This repository contains the original ``MERCURY 6.4bin`` FORTRAN77 code from John E. Chambers.

Mercury is a general-purpose N-body integration package for problems in celestial mechanics. It is the N-body integrator based on Bulirsh-Stoer, Everhart and other methods. It can "out of box" integrate every system like Solar System, 3 body problem and so on. The Mercury binary version can also work for either single stars (central -> Chambers, 1999) and binary stars (close/wide -> Chambers et al., 2002). The configuration is really simple. Current package is preconfigured for Linux and Mac OS X users with compile and clean tasks.

Overview
--------

These are the files necessary to compile and run the Mercury N-body integrator package, version 6.4bin.

The following files should be present:

- big.in
- close.in
- close6.for
- element.in
- element6.for
- files.in
- mercury.inc
- mercury6.man
- mercury6_4bin.for
- message.in
- param.in
- small.in
- swift.inc

Start by looking at the manual contained in mercury6.man

- mercury6_4bin.for contains the source code for the integrator.
- element6.for contains source code for a programme to turn compressed output from mercury into coordinates or orbital elements for each object.
- close6.for contains source code for a programme to provide details on close encounters during an integration.

Running Mercury
-----

Remove ``*.out``, ``*.dmp`` and ``*.tmp`` files from older runs before running. Remember to compile the code before each run, using ```gfortran mercury6_4bin.for -o mercury6``` for example. Then run ```mercury6```, ```element6```, and ```close6``` optionally.

Or use the ``Makefile:``

To compile on Linux or Mac OS X just run ``make`` on the terminal at current directory. You need to have gfortran compiler. If you don't have you need to install it. For other compilers change the corresponding lines in ``Makefile``. This file can be changed if you want to use another compiler as the default one (gfortran). Usually I use the compiler ifort, which leads to faster integration time.

To clean the directory *.o files run ``make clean``.

References
-------------------

* A Symplectic Integration Scheme that Allows Close Encounters between Massive Bodies. J.E.Chambers (1999) IAU Colloquium 172, The Impact of Modern Dynamics in Astronomy, 449-450.
* A Hybrid Symplectic Integrator that Permits Close Encounters between Massive Bodies. J.E.Chambers (1999) Monthly Notices of Royal Astron. Soc., 304, 793-799.
* Mercury - A New Software Package for Orbital Integrations. J.E.Chambers and F.Migliorini (1997) Bull. American Astron. Soc., 29, 1024.
* Symplectic Integrator Algorithms for Modeling Planetary Accretion in Binary Star Systems. Chambers, John E.; Quintana, Elisa V.; Duncan, Martin J.; Lissauer, Jack J. (2002) The Astronomical Journal, Volume 123, Issue 5, pp. 2884-2894.
