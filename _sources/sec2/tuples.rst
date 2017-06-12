Tuples
======

Tuple is a sequence type just like ``list``, but it is immutable.
A tuple consists of a number of values separated by commas.

.. code-block:: python

    >>> a = (1, 2, 3)
    >>> a[0]
    1

The enclosing braces are optional.

.. code-block:: python

    >>> a = 1, 2, 3
    >>> a[0]
    1

The built-in function ``len`` and slicing works on tuples too.

.. code-block:: python

    >>> len(a)
    3
    >>> a[1:]
    2, 3

Since parenthesis are also used for grouping, tuples with a single value are represented with an additional comma.

.. code-block:: python

    >>> a = (1)
    >> a
    1
    >>> b = (1,)
    >>> b
    (1,)
    >>> b[0]
    1
