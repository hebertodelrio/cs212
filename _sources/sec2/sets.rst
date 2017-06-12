Sets
====

Sets are unordered collection of unique elements.

.. code-block:: python

    >>> x = set([3, 1, 2, 1])
    set([1, 2, 3])

Python 2.7 introduced a new way of writing sets.

.. code-block:: python

    >>> x = {3, 1, 2, 1}
    set([1, 2, 3])

New elements can be added to a set using the ``add`` method.

.. code-block:: python

    >>> x = set([1, 2, 3])
    >>> x.add(4)
    >>> x
    set([1, 2, 3, 4])

Just like lists, the existance of an element can be checked using the ``in``
operator. However, this operation is faster in sets compared to lists.

.. code-block:: python

    >>> x = set([1, 2, 3])
    >>> 1 in x
    True
    >>> 5 in x
    False

.. problem:: Reimplement the `unique` function implemented in the earlier
   examples using sets.
