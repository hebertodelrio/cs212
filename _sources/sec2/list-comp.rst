List Comprehensions
===================

List Comprehensions provide a concise way of creating lists.
Many times a complex task can be modelled in a single line.

Here are some simple examples for transforming a list.

.. code-block:: python

    >>> a = range(10)
    >>> a
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    >>> [x for x in a]
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    >>> [x*x for x in a]
    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
    >>> [x+1 for x in a]
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

It is also possible to filter a list using ``if`` inside a list comprehension.

.. code-block:: python

    >>> a = range(10)
    >>> [x for x in a if x % 2 == 0]
    [0, 2, 4, 6, 8]
    >>> [x*x for x in a if x%2 == 0]
    [0, 4, 8, 36, 64]

It is possible to iterate over multiple lists using the built-in function ``zip``.

.. code-block:: python

    >>> a = [1, 2, 3, 4]
    >>> b = [2, 3, 5, 7]
    >>> zip(a, b)
    [(1, 2), (2, 3), (3, 5), (4, 7)]
    >>> [x+y for x, y in zip(a, b)]
    [3, 5, 8, 11]

we can use multiple ``for`` clauses in single list comprehension.

.. code-block:: python

   >>> [(x, y) for x in range(5) for y in range(5) if (x+y)%2 == 0]
   [(0, 0), (0, 2), (0, 4), (1, 1), (1, 3), (2, 0), (2, 2), (2, 4), (3, 1), (3, 3), (4, 0), (4, 2), (4, 4)]

   >>> [(x, y) for x in range(5) for y in range(5) if (x+y)%2 == 0 and x != y]
   [(0, 2), (0, 4), (1, 3), (2, 0), (2, 4), (3, 1), (4, 0), (4, 2)]

   >>> [(x, y) for x in range(5) for y in range(x) if (x+y)%2 == 0]
   [(2, 0), (3, 1), (4, 0), (4, 2)]

The following example finds all Pythagorean triplets using numbers below 25. ``(x, y, z)`` is a called pythagorean triplet if ``x*x + y*y == z*z``.

.. code-block:: python

    >>> n = 25
    >>> [(x, y, z) for x in range(1, n) for y in range(x, n) for z in range(y, n) if x*x + y*y == z*z]
    [(3, 4, 5), (5, 12, 13), (6, 8, 10), (8, 15, 17), (9, 12, 15), (12, 16, 20)]

.. problem:: Provide an implementation for ``zip`` function using list comprehensions.

.. code-block:: python

    >>> zip([1, 2, 3], ["a", "b", "c"])
    [(1, "a"), (2, "b"), (3, "c")]

.. problem:: Python provides a built-in function ``map`` that applies a function to each element of a list. Provide an implementation for ``map`` using list comprehensions.

.. code-block:: python

    >>> def square(x): return x * x
    ...
    >>> map(square, range(5))
    [0, 1, 4, 9, 16]

.. problem:: Python provides a built-in function ``filter(f, a)`` that returns items of the list ``a`` for which ``f(item)`` returns true. Provide an implementation for ``filter`` using list comprehensions.

.. code-block:: python

    >>> def even(x): return x %2 == 0
    ...
    >>> filter(even, range(10))
    [0, 2, 4, 6, 8]

.. problem:: Write a function ``triplets`` that takes a number ``n`` as argument and returns a list of triplets such that sum of first two elements of the triplet equals the third element using numbers below n. Please note that ``(a, b, c)`` and ``(b, a, c)`` represent same triplet.

.. code-block:: python

    >>> triplets(5)
    [(1, 1, 2), (1, 2, 3), (1, 3, 4), (2, 2, 4)]

.. problem:: Write a function ``enumerate`` that takes a list and returns a list of tuples containing ``(index,item)`` for each item in the list.

.. code-block:: python

    >>> enumerate(["a", "b", "c"])
    [(0, "a"), (1, "b"), (2, "c")]
    >>> for index, value in enumerate(["a", "b", "c"]):
    ...     print index, value
    0 a
    1 b
    2 c

.. problem:: Write a function ``array`` to create an 2-dimensional array. The function should take both dimensions as arguments. Value of each element can be initialized to None:

.. code-block:: python

    >>> a = array(2, 3)
    >>> a
    [[None, None, None], [None, None, None]]
    >>> a[0][0] = 5
    [[5, None, None], [None, None, None]]

.. problem:: Write a python function ``parse_csv`` to parse csv (comma separated values) files.

.. code-block:: python

    >>> print open('a.csv').read()
    a,b,c
    1,2,3
    2,3,4
    3,4,5
    >>> parse_csv('a.csv')
    [['a', 'b', 'c'], ['1', '2', '3'], ['2', '3', '4'], ['3', '4', '5']]

.. problem:: Generalize the above implementation of csv parser to support any delimiter and comments.

.. code-block:: python

    >>> print open('a.txt').read()
    # elements are separated by ! and comment indicator is #
    a!b!c
    1!2!3
    2!3!4
    3!4!5
    >>> parse('a.txt', '!', '#')
    [['a', 'b', 'c'], ['1', '2', '3'], ['2', '3', '4'], ['3', '4', '5']]

.. problem:: Write a function ``mutate`` to compute all words generated by a single mutation on a given word. A mutation is defined as inserting a character, deleting a character, replacing a character, or swapping 2 consecutive characters in a string. For simplicity consider only letters from ``a`` to ``z``.

.. code-block:: python

    >>> words = mutate('hello')
    >>> 'helo' in words
    True
    >>> 'cello' in words
    True
    >>> 'helol' in words
    True

.. problem:: Write a function ``nearly_equal`` to test whether two strings are nearly equal. Two strings ``a`` and ``b`` are nearly equal when ``a`` can be generated by a single mutation on ``b``.

.. code-block:: python

    >>> nearly_equal('python', 'perl')
    False
    >>> nearly_equal('perl', 'pearl')
    True
    >>> nearly_equal('python', 'jython')
    True
    >>> nearly_equal('man', 'woman')
    False
