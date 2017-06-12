Lists
=====

Lists are one of the great datastructures in Python. We are going to learn a
little bit about lists now. Basic knowledge of lists is requrired to be able to
solve some problems that we want to solve in this chapter.

Here is a list of numbers.

.. code-block:: python

    >>> x = [1, 2, 3]

And here is a list of strings.

.. code-block:: python

    >>> x = ["hello", "world"]

List can be heterogeneous. Here is a list containings integers, strings and another list.

.. code-block:: python

    >>> x = [1, 2, "hello", "world", ["another", "list"]]

The built-in function ``len`` works for lists as well.

.. code-block:: python

    >>> x = [1, 2, 3]
    >>> len(x)
    3

The ``[]`` operator is used to access individual elements of a list.

.. code-block:: python

    >>> x = [1, 2, 3]
    >>> x[1]
    2
    >>> x[1] = 4
    >>> x[1]
    4

The first element is indexed with ``0``, second with ``1`` and so on.

We'll learn more about lists in the next chapter.
