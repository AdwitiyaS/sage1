gap_packages: A collection of GAP packages
==========================================

Description
-----------

Several "official" and "undeposited" GAP packages available from
https://www.gap-system.org/Packages/packages.html

Installing this SPKG will install the corresponding GAP packages, but
before you can use them in Sage, they still have to be loaded into
either the GAP interface or libgap::

  sage: gap.eval('LoadPackage("Grape")')  [†]
  'true'
  sage: libgap.LoadPackage("Grape")       [‡]
  true

Those correspond to::

  gap> LoadPackage("Grape");

within the GAP interface and libgap, respectively.
.. [†] This loads "Grape" package in the GAP interface.
.. [‡] This loads "Grape" package using libgap.
Upstream Contact
----------------

Mailing list at https://mail.gap-system.org/mailman/listinfo/gap

Dependencies
------------

-  GAP (a standard spkg)

TODO
----

The crystallographic group packages are untested/untestable. They rely
on polymake and the dependency "cryst" is missing. This needs to be
cleaned up.

Notes
-----

A brief description of each package follows:

cohomolo - The cohomolo package is a GAP interface to some ``C`` programs
for computing Schur multipliers and covering groups of finite groups and
first and second cohomology groups of finite groups acting on finite
modules. (Author: Max Horn, Markus Pfeiffer)

CoReLG - Contains functionality for working with real semisimple Lie
algebras. (Author: Heiko Dietrich, Paolo Faccin, Willem Adriaan de
Graaf)

crime - package to compute the cohomology ring of finite p-groups,
induced maps, and Massey products. (Author: Marcus Bishop)

cryst - Computing with crystallographic groups (Authors: Bettina Eick,
Franz Gähler, Werner Nickel)

CTblLib - The GAP Character Table Library (Author: Thomas Breuer)

DESIGN is a package for classifying, partitioning and studying block
designs. (Author: Leonard H. Soicher)

FactInt is a package providing routines for factoring integers, in
particular:

-  Pollard's p-1
-  Williams' p+1
-  Elliptic Curves Method (ECM)
-  Continued Fraction Algorithm (CFRAC)
-  Multiple Polynomial Quadratic Sieve (MPQS)

(Author: Stefan Kohl)

GAPDoc is a package containing a definition of a structure for GAP
documentation, based on XML. It also contains conversion programs for
producing text-, DVI-, PDF- or HTML-versions of such documents, with
hyperlinks if possible. (Authors: Frank Luebeck, Max Neunhoeffer)

GBNP - The GBNP package provides algorithms for computing Grobner bases
of noncommutative polynomials with coefficients from a field implemented
in GAP and with respect to the "total degree first then lexicographical"
ordering. Further provided are some variations, such as a weighted and
truncated version and a tracing facility. The word "algorithm" is to be
interpreted loosely here: in general one cannot expect such an algorithm
to terminate, as it would imply solvability of the word problem for
finitely presented (semi)groups. (Authors: A.M. Cohen, J.W. Knopper)

GRAPE is a package for computing with graphs and groups, and is
primarily designed for constructing and analysing graphs related to
groups, finite geometries, and designs. (Author: Leonard H. Soicher)

GUAVA is included here, and with Sage standard.

HAP (Homological Algebra Programming) is a GAP package providing some
functions for group cohomology computation. (Author: Graham Ellis)

HAPcryst - an extension package for HAP, which allows for group
cohomology computation for a wider class of groups. (Author: Marc
Roeder)

hecke - Provides functions for calculating decomposition matrices of
Hecke algebras of the symmetric groups and q-Schur algebras. Hecke is a
port of the GAP 3 package Specht 2.4 to GAP 4. (Author: Dmitriy Traytel)

LAGUNA - this package provides functionality for calculation of the
normalized unit group of the modular group algebra of the finite p-group
and for investigation of Lie algebra associated with group algebras and
other associative algebras. (Authors :Victor Bovdi, Alexander Konovalov,
Richard Rossmanith, Csaba Schneider)

liealgdb - A database of Lie algebras (Author: Serena Cicalo', Willem
Adriaan de Graaf, Csaba Schneider)

LiePRing - Database and algorithms for Lie p-rings (Author: Michael
Vaughan-Lee, Bettina Eick)

LieRing - contains functionality for working with finitely presented Lie
rings and the Lazard correspondence. (Author: Serena Cicalo', Willem
Adriaan de Graaf)

loops - Provides researchers in nonassociative algebra with a
computational tool that integrates standard notions of loop theory with
libraries of loops and group-theoretical algorithms of GAP. The package
also expands GAP toward nonassociative structures. (Authors: Gabor Nagy,
Petr Vojtechovsky)

mapclass - The package calculates the mapping class group orbits for a
given finite group. (Authors: Adam James, Kay Magaard, Sergey
Shpectorov, Helmut Volklein)

polymake - an interface with the (standalone) polymake program used by
HAPcryst. (Author: Marc Roeder)

qpa - Quivers and Path Algebras provides data structures and algorithms
for doing computations with finite dimensional quotients of path
algebras, and finitely generated modules over such algebras. The current
version of the QPA package has data structures for quivers, quotients of
path algebras, and modules, homomorphisms and complexes of modules over
quotients of path algebras. (Authors: Edward Green, Oeyvind Solberg)

quagroup - Contains functionality for working with quantized enveloping
algebras of finite-dimensional semisimple Lie algebras. (Author: Willem
Adriaan de Graaf)

repsn - The package provides GAP functions for computing characteristic
zero matrix representations of finite groups. (Author: Vahid Dabbaghian)

sla - a package for doing computations with simple Lie algebras (Author:
Willem Adriaan de Graaf)

SONATA ("System Of Nearrings And Their Applications") is a package which
constructs finite nearrings and related objects. (Authors: Erhard
Aichinger, Franz Binder, Jürgen Ecker, Peter Mayr, Christof Noebauer)

TORIC is a GAP package for computing with toric varieties. (Author:
David Joyner)
