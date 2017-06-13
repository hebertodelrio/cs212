Numbers
=======

We already know how to work with numbers.

.. code-block:: python

    >>> 42
    42
    >>> 4 + 2
    6

Python also supports decimal numbers.

.. code-block:: python

    >>> 4.2
    4.2
    >>> 4.2 + 2.3
    6.5

Python supports the following operators on numbers.

* ``+`` addition
* ``-`` subtraction
* ``*`` multiplication
* ``/`` division (floating point)
* ``//`` division (integer)
* ``**`` exponent
* ``%`` remainder

Let's try them on integers.

.. code-block:: python

    >>> 7 + 2
    9
    >>> 7 - 2
    5
    >>> 7 * 2
    14
    >>> 7 / 2
    3.5
    >>> 7 // 2
    3
    >>> 7 ** 2
    49
    >>> 7 % 2
    1

If you notice, the result ``7 / 2`` is ``3.5`` and the result ``7 // 2`` is ``3`` not ``3.5``. It is because the ``//`` operator when working on integers, produces only an integer. Lets see what happens when we try it with decimal numbers:

.. code-block:: python

    >>> 7.0 // 2.0
    3.0
    >>> 7.0 // 2
    3.0
    >>> 7 // 2.0
    3.0

The operators can be combined.

.. code-block:: python

    >>> 7 + 2 + 5 - 3
    11
    >>> 2 * 3 + 4
    10

It is important to understand how these compound expressions are evaluated. The
operators have precedence, a kind of priority that determines which operator is
applied first. Among the numerical operators, the precedence of operators is as
follows, from high precedence to low (EMDAS in PEMDAS).

* ``**``
* ``*``, ``/``, ``//``, ``%``
* ``+``, ``-``

When we compute ``2 + 3 * 4``, ``3 * 4`` is computed first as the precedence of
``*`` is higher than ``+`` and then the result is added to 2.

.. code-block:: python

    >>> 2 + 3 * 4
    14

The following is what happens when Python evaluates the expression `1 + 2 - 3 * 4 + 2 ** 4`:

.. code-block:: python

    1 + 2 - 3 * 4 + 2 ** 4
                      ↓
    1 + 2 - 3 * 4 +   16
              ↓
    1 + 2 -   12  +   16
      ↓
      3   -   12  +   16
          ↓
          -9      +   16
                  ↓
                  7

We can use parenthesis to specify the explicit groups and change the precedence order
(P in PEMDAS).

.. code-block:: python

    >>> (2 + 3) * 4
    20

All the operators except ``**`` are left-associative, that means that when two (or more)
operators with the same order of precedence are found in an expression, the application
of the operators starts from left to right (PEMDAS).

.. problem:: What will be the output of the following program? Can you explain?

.. code-block:: python

    print(2**2**3)
    print(2**(2**3))
    print((2**2)**3)

.. problem:: What is the value of the following expression: `40 // 5 * 5 - 6 // 2 * 3 + 4 + 5 * 2 // 10`? Can you explain?
