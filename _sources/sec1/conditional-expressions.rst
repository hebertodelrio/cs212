Conditional Expressions
=======================

Python provides various operators for comparing values. The result of a comparison is a boolean value, either ``True`` or ``False``.

.. code-block:: python

    >>> 2 < 3
    False
    >>> 2 > 3
    True

Here is the list of available conditional operators.

* ``==`` equal to
* ``!=`` not equal to
* ``<`` less than
* ``>`` greater than
* ``<=`` less than or equal to
* ``>=`` greater than or equal to

It is even possible to combine these operators.

.. code-block:: python

    >>> x = 5
    >>> 2 < x < 10
    True
    >>> 2 < 3 < 4 < 5 < 6
    True

The conditional operators work even on strings - the ordering being the lexical order.

.. code-block:: python

    >>> "python" > "perl"
    True
    >>> "python" > "java"
    True

There are few logical operators to combine boolean values.

* ``a and b`` is ``True`` only if both ``a`` and ``b`` are True.
* ``a or b`` is True if either ``a`` or ``b`` is True.
* ``not a`` is True only if ``a`` is False.

.. code-block:: python

    >>> True and True
    True
    >>> True and False
    False
    >>> 2 < 3 and 5 < 4
    False
    >>> 2 < 3 or 5 < 4
    True

.. problem:: What will be output of the following program?

.. code-block:: python

    print(2 < 3 and 3 > 1)
    print(2 < 3 or 3 > 1)
    print(2 < 3 or not 3 > 1)
    print(2 < 3 and not 3 > 1)

.. problem:: What will be output of the following program?

.. code-block:: python

    x = 4
    y = 5
    p = x < y or x < z
    print(p)

.. problem:: What will be output of the following program?

.. code-block:: python

    True, False = False, True
    print(True, False)
    print(2 < 3)

The if statement
^^^^^^^^^^^^^^^^

The ``if`` statement is used to execute a piece of code only when a boolean expression is true.

.. code-block:: python

    >>> x = 42
    >>> if x % 2 == 0: print('even')
    even
    >>>

In this example, ``print()'even')`` is executed only when ``x % 2 == 0`` is ``True``.

The code associated with ``if`` can be written as a separate indented block of code, which is often the case when there is more than one statement to be executed.

.. code-block:: python

    >>> if x % 2 == 0:
    ...     print('even')
    ...
    even
    >>>


The ``if`` statement can have optional ``else`` clause, which is executed when the boolean expression is ``False``.

.. code-block:: python

    >>> x = 3
    >>> if x % 2 == 0:
    ...     print('even')
    ... else:
    ...     print('odd')
    ...
    odd
    >>>

The ``if`` statement can have optional ``elif`` clauses when there are more
conditions to be checked. The ``elif`` keyword is short for ``else if``, and is
useful to avoid excessive indentation.

.. code-block:: python

    >>> x = 42
    >>> if x < 10:
    ...        print('one digit number')
    ... elif x < 100:
    ...     print('two digit number')
    ... else:
    ...     print('big number')
    ...
    two digit number
    >>>

.. problem:: What happens when the following code is executed? Will it give any
   error? Explain the reasons.

.. code-block:: python

    x = 2
    if x == 2:
        print(x)
    else:
        print(y)

.. problem:: What happens the following code is executed? Will it give any error? Explain the reasons.

.. code-block:: python

    x = 2
    if x == 2:
        print(x)
    else:
        x +
