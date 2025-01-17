*************
Number fields
*************

Ramification
============
How do you compute the number fields with given discriminant and
ramification in Sage?

Sage can access the Jones database of number fields with bounded
ramification and degree less than or equal to 6. It must be
installed separately (``database_jones_numfield``).

.. index::
   pair: number field; database

First load the database:

::

    sage: J = JonesDatabase()            [1]
    sage: J                              [2]
    John Jones's table of number fields with bounded ramification and degree <= 6

.. index::
   pair: number field; discriminant

List the degree and discriminant of all fields in the database that
have ramification at most at 2:
.. [1] This initializes access to the Jones database of number fields.
.. [2] Displays the contents of the Jones database
.. link

::

    sage: [(k.degree(), k.disc()) for k in J.unramified_outside([2])]  - database
    [(4, -2048), (2, 8), (4, -1024), (1, 1), (4, 256), (2, -4), (4, 2048), (4, 512), (4, 2048), (2, -8), (4, 2048)]

List the discriminants of the fields of degree exactly 2 unramified
outside 2:

.. link

::

    sage: [k.disc() for k in J.unramified_outside([2],2)] [3]
    [8, -4, -8]

.. [3] Displays the discriminants of degree 2 fields unramified outside 2.

List the discriminants of cubic field in the database ramified
exactly at 3 and 5:

.. link

::

    sage: [k.disc() for k in J.ramified_at([3,5],3)] [4]
    [-6075, -6075, -675, -135]
    sage: factor(6075)
    3^5 * 5^2
    sage: factor(675)
    3^3 * 5^2
    sage: factor(135)
    3^3 * 5


.. [4] Displays the discriminants of cubic fields in the database that are ramified exactly at 3 and 5.

List all fields in the database ramified at 101:

.. link

::

    sage: J.ramified_at(101)                     [5]
    [Number Field in a with defining polynomial x^2 - 101,
     Number Field in a with defining polynomial x^4 - x^3 + 13*x^2 - 19*x + 361,
     Number Field in a with defining polynomial x^5 - x^4 - 40*x^3 - 93*x^2 - 21*x + 17,
     Number Field in a with defining polynomial x^5 + x^4 - 6*x^3 - x^2 + 18*x + 4,
     Number Field in a with defining polynomial x^5 + 2*x^4 + 7*x^3 + 4*x^2 + 11*x - 6]

.. [5] Displays all fields in the database that are ramified at the prime number 101.

.. index::
   pair: number field; class_number

Class numbers
=============

How do you compute the class number of a number field in Sage?

The ``class_number`` is a method associated to a QuadraticField
object:

::

    sage: K = QuadraticField(29, 'x')
    sage: K.class_number()
    1
    sage: K = QuadraticField(65, 'x')
    sage: K.class_number()
    2
    sage: K = QuadraticField(-11, 'x')
    sage: K.class_number()
    1
    sage: K = QuadraticField(-15, 'x')
    sage: K.class_number()
    2
    sage: K.class_group()
    Class group of order 2 with structure C2 of Number Field in x with defining polynomial x^2 + 15 with x = 3.872983346207417?*I
    sage: K = QuadraticField(401, 'x')
    sage: K.class_group()
    Class group of order 5 with structure C5 of Number Field in x with defining polynomial x^2 - 401 with x = 20.02498439450079?
    sage: K.class_number()
    5
    sage: K.discriminant()
    401
    sage: K = QuadraticField(-479, 'x')
    sage: K.class_group()
    Class group of order 25 with structure C25 of Number Field in x with defining polynomial x^2 + 479 with x = 21.88606862823929?*I
    sage: K.class_number()
    25
    sage: K.pari_polynomial()
    x^2 + 479
    sage: K.degree()
    2

Here's an example involving a more general type of number field:

::

    sage: x = PolynomialRing(QQ, 'x').gen()
    sage: K = NumberField(x^5+10*x+1, 'a')
    sage: K
    Number Field in a with defining polynomial x^5 + 10*x + 1
    sage: K.degree()
    5
    sage: K.pari_polynomial()
    x^5 + 10*x + 1
    sage: K.discriminant()
    25603125
    sage: K.class_group()
    Class group of order 1 of Number Field in a with defining
    polynomial x^5 + 10*x + 1
    sage: K.class_number()
    1


-  See also the link for class numbers at
   http://mathworld.wolfram.com/ClassNumber.html at the Math World
   site for tables, formulas, and background information.

.. index::
   pair: number field; cyclotomic

-  For cyclotomic fields, try:

   ::

       sage: K = CyclotomicField(19)
       sage: K.class_number()    # long time
       1


For further details, see the documentation strings in the
``ring/number_field.py`` file.

.. index::
   pair: number field; integral basis

Integral basis
==============

How do you compute an integral basis of a number field in Sage?

Sage can compute a list of elements of this number field that are a
basis for the full ring of integers of a number field.

::

    sage: x = PolynomialRing(QQ, 'x').gen()
    sage: K = NumberField(x^5+10*x+1, 'a')
    sage: K.integral_basis()
    [1, a, a^2, a^3, a^4]

Next we compute the ring of integers of a cubic field in which 2 is
an "essential discriminant divisor", so the ring of integers is not
generated by a single element.

::

    sage: x = PolynomialRing(QQ, 'x').gen()
    sage: K = NumberField(x^3 + x^2 - 2*x + 8, 'a')
    sage: K.integral_basis()
    [1, 1/2*a^2 + 1/2*a, a^2]
