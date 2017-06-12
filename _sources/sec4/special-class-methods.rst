Special Class Methods
=====================

In Python, a class can implement certain operations that are invoked by special syntax (such as arithmetic operations or subscripting and slicing) by defining methods with special names.
This is Python's approach to operator overloading, allowing classes to define their own behavior with respect to language operators.

For example, the ``+`` operator invokes ``__add__`` method.

.. code-block:: python

    >>> a, b = 1, 2
    >>> a + b
    3
    >>> a.__add__(b)
    3

Just like ``__add__`` is called for ``+`` operator, ``__sub__``, ``__mul__`` and ``__div__`` methods are called for ``-``, ``*``, and ``/`` operators.

**Example: Rational Numbers**

Suppose we want to do arithmetic with rational numbers. We want to be able to add, subtract, multiply, and divide them and to test whether two rational numbers are equal.

We can add, subtract, multiply, divide, and test equality by using the following relations::

    n1/d1 + n2/d2 = (n1*d2 + n2*d1)/(d1*d2)
    n1/d1 - n2/d2 = (n1*d2 - n2*d1)/(d1*d2)
    n1/d1 * n2/d2 = (n1*n2)/(d1*d2)
    (n1/d1) / (n2/d2) = (n1*d2)/(d1*n2)

    n1/d1 == n2/d2 if and only if n1*d2 == n2*d1

Lets write the rational number class.

.. code-block:: python

    class RationalNumber:
        """
        Rational Numbers with support for arthmetic operations.

            >>> a = RationalNumber(1, 2)
            >>> b = RationalNumber(1, 3)
            >>> a + b
            5/6
            >>> a - b
            1/6
            >>> a * b
            1/6
            >>> a/b
            3/2
        """
        def __init__(self, numerator, denominator=1):
            self.n = numerator
            self.d = denominator

        def __add__(self, other):
            if not isinstance(other, RationalNumber):
                other = RationalNumber(other)

            n = self.n * other.d + self.d * other.n
            d = self.d * other.d
            return RationalNumber(n, d)

        def __sub__(self, other):
            if not isinstance(other, RationalNumber):
                other = RationalNumber(other)

            n1, d1 = self.n, self.d
            n2, d2 = other.n, other.d
            return RationalNumber(n1*d2 - n2*d1, d1*d2)

        def __mul__(self, other):
            if not isinstance(other, RationalNumber):
                other = RationalNumber(other)

            n1, d1 = self.n, self.d
            n2, d2 = other.n, other.d
            return RationalNumber(n1*n2, d1*d2)

        def __div__(self, other):
            if not isinstance(other, RationalNumber):
                other = RationalNumber(other)

            n1, d1 = self.n, self.d
            n2, d2 = other.n, other.d
            return RationalNumber(n1*d2, d1*n2)

        def __str__(self):
            return "%s/%s" % (self.n, self.d)

        __repr__ = __str__
