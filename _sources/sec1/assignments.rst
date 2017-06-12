Assignments
===========

One of the building blocks of programming is associating a name to a value.
This is called assignment. The associated name is usually called a *variable*.

.. code-block:: python

    >>> x = 4
    >>> x * x
    16

In this example ``x`` is a variable and it's value is ``4``.

If you try to use a name that is not associated with any value, python gives an error message.

.. code-block:: python

    >>> foo
    Traceback (most recent call last):
      File "<stdin>", line 1, in ?
    NameError: name 'foo' is not defined
    >>> foo = 4
    >>> foo
    4

If you re-assign a different value to an existing variable, the new value
overwrites the old value.

.. code-block:: python

    >>> x = 4
    >>> x
    4
    >>> x = 'hello'
    >>> x
    'hello'

It is possible to do multiple assignments at once.

.. code-block:: python

    >>> a, b = 1, 2
    >>> a
    1
    >>> b
    2
    >>> a + b
    3

Swapping values of 2 variables in python is very simple.

.. code-block:: python

    >>> a, b = 1, 2
    >>> a, b = b, a
    >>> a
    2
    >>> b
    1

When executing assignments, python evaluates the right hand side first and then assigns those values to the variables specified in the left hand side.

.. problem:: What will be the output of the following program? Can you explain?

.. code-block:: python

    x = 1
    print(x)
    x = x + 1
    print(x)
    x = x + 1
    print(x)
    x = x + 1
    print(x)

.. problem:: What will be the output of the following program? Can you explain?

.. code-block:: python

    x = 4
    y = x + 1
    x = 2
    print(x, y)

.. problem:: What will be the the output of the following program? Can you explain?

.. code-block:: python

    x, y = 2, 6
    x, y = y, x + 2
    print(x, y)

.. problem:: What will be the output of the following program? Can you explain?

.. code-block:: python

    a, b = 2, 3
    c, b = a, c + 1
    print(a, b, c)
