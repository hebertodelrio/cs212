Lists
=====

We've already seen quick introduction to lists in the previous chapter.

.. code-block:: python

    >>> [1, 2, 3, 4]
    [1, 2, 3, 4]
    >>> ["hello", "world"]
    ["hello", "world"]
    >>> [0, 1.5, "hello"]
    [0, 1.5, "hello"]
    >>> [0, 1.5, "hello"]
    [0, 1.5, "hello"]

A List can contain another list as member.

.. code-block:: python

    >>> a = [1, 2]
    >>> b = [1.5, 2, a]
    >>> b
    [1.5, 2, [1, 2]]

The built-in function ``range`` can be used to create a list of integers.

.. code-block:: python

    >>> range(4)
    [0, 1, 2, 3]
    >>> range(3, 6)
    [3, 4, 5]
    >>> range(2, 10, 3)
    [2, 5, 8]

The built-in function ``len`` can be used to find the length of a list.

.. code-block:: python

    >>> a = [1, 2, 3, 4]
    >>> len(a)
    4

The ``+`` and ``*`` operators work even on lists.

.. code-block:: python

    >>> a = [1, 2, 3]
    >>> b = [4, 5]
    >>> a + b
    [1, 2, 3, 4, 5]
    >>> b * 3
    [4, 5, 4, 5, 4, 5]

List can be indexed to get individual entries. Value of index can go from 0 to (length of list - 1).

.. code-block:: python

    >>> x = [1, 2]
    >>> x[0]
    1
    >>> x[1]
    2

When a wrong index is used, python gives an error.

.. code-block:: python

    >>> x = [1, 2, 3, 4]
    >>> x[6]
    Traceback (most recent call last):
      File "<stdin>", line 1, in ?
    IndexError: list index out of range

Negative indices can be used to index the list from right.

.. code-block:: python

    >>> x = [1, 2, 3, 4]
    >>> x[-1]
    4
    >>> x [-2]
    3

We can use list slicing to get part of a list.

.. code-block:: python

    >>> x = [1, 2, 3, 4]
    >>> x[0:2]
    [1, 2]
    >>> x[1:4]
    [2, 3, 4]

Even negative indices can be used in slicing. For example, the following examples strips the last element from the list.

.. code-block:: python

    >>> x[0:-1]
    [1, 2, 3]

Slice indices have useful defaults; an omitted first index defaults to zero, an omitted second index defaults to the size of the list being sliced.

.. code-block:: python

    >>> x = [1, 2, 3, 4]
    >>> a[:2]
    [1, 2]
    >>> a[2:]
    [3, 4]
    >>> a[:]
    [1, 2, 3, 4]

An optional third index can be used to specify the increment, which defaults to 1.

.. code-block:: python

    >>> x = range(10)
    >>> x
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    >>> x[0:6:2]
    [0, 2, 4]

We can reverse a list, just by providing -1 for increment.

.. code-block:: python

    >>> x[::-1]
    [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]

List members can be modified by assignment.

.. code-block:: python

    >>> x = [1, 2, 3, 4]
    >>> x[1] = 5
    >>> x
    [1, 5, 3, 4]

Presence of a key in a list can be tested using ``in`` operator.

.. code-block:: python

    >>> x = [1, 2, 3, 4]
    >>> 2 in x
    True
    >>> 10 in x
    False

Values can be appended to a list by calling ``append`` method on list. A method is just like a function, but it is associated with an object and can access that object when it is called. We will learn more about methods when we study classes.

.. code-block:: python

    >>> a = [1, 2]
    >>> a.append(3)
    >>> a
    [1, 2, 3]

.. problem:: What will be the output of the following program?

.. code-block:: python

	x = [0, 1, [2]]
	x[2][0] = 3
	print x
	x[2].append(4)
	print x
	x[2] = 2
	print x

The for Statement
^^^^^^^^^^^^^^^^^

Python provides ``for`` statement to iterate over a list. A ``for`` statement executes the specified block of code for every element in a list.

.. code-block:: python

    for x in [1, 2, 3, 4]:
        print x

    for i  in range(10):
       print i, i*i, i*i*i

The built-in function ``zip`` takes two lists and returns list of pairs. ::

    >>> zip(["a", "b", "c"], [1, 2, 3])
    [('a', 1), ('b', 2), ('c', 3)]

It is handy when we want to iterate over two lists together. ::

    names = ["a", "b", "c"]
    values = [1, 2, 3]
    for name, value in zip(names, values):
        print name, value


.. problem:: Python has a built-in function ``sum`` to find sum of all elements of a list. Provide an implementation for ``sum``.

.. code-block:: python

    >>> sum([1, 2, 3])
    >>> 6

.. problem:: What happens when the above ``sum`` function is called with a list of strings? Can you make your ``sum`` function work for a list of strings as well.

.. code-block:: python

    >>> sum(["hello", "world"])
    "helloworld"
    >>> sum(["aa", "bb", "cc"])
    "aabbcc"

.. problem:: Implement a function ``product``, to compute product of a list of numbers.

.. code-block:: python

    >>> product([1, 2, 3])
    6

.. problem:: Write a function ``factorial`` to compute factorial of a number.
   Can you use the ``product`` function defined in the previous example to
   compute factorial?

.. code-block:: python

    >>> factorial(4)
    24

.. problem:: Write a function ``reverse`` to reverse a list. Can you do this
   without using list slicing?

.. code-block:: python

    >>> reverse([1, 2, 3, 4])
    [4, 3, 2, 1]
    >>> reverse(reverse([1, 2, 3, 4]))
    [1, 2, 3, 4]

.. problem:: Python has built-in functions ``min`` and ``max`` to compute
   minimum and maximum of a given list. Provide an implementation for these
   functions. What happens when you call your ``min`` and ``max`` functions with a
   list of strings?

.. problem:: Cumulative sum of a list ``[a, b, c, ...]`` is defined as ``[a,
   a+b, a+b+c, ...]``. Write a function ``cumulative_sum`` to compute
   cumulative sum of a list. Does your implementation work for a list of strings?

.. code-block:: python

    >>> cumulative_sum([1, 2, 3, 4])
    [1, 3, 6, 10]
    >>> cumulative_sum([4, 3, 2, 1])
    [4, 7, 9, 10]

.. problem:: Write a function ``cumulative_product`` to compute cumulative
   product of a list of numbers.

.. code-block:: python

    >>> cumulative_product([1, 2, 3, 4])
    [1, 2, 6, 24]
    >>> cumulative_product([4, 3, 2, 1])
    [4, 12, 24, 24]

.. problem:: Write a function `unique` to find all the unique elements of a list.

.. code-block:: python

	>>> unique([1, 2, 1, 3, 2, 5])
	[1, 2, 3, 5]

.. problem:: Write a function `dups` to find all duplicates in the list.

.. code-block:: python

	>>> dups([1, 2, 1, 3, 2, 5])
	[1, 2]

.. problem:: Write a function `group(list, size)` that take a list and splits
   into smaller lists of given size.

.. code-block:: python

    >>> group([1, 2, 3, 4, 5, 6, 7, 8, 9], 3)
    [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
    >>> group([1, 2, 3, 4, 5, 6, 7, 8, 9], 4)
    [[1, 2, 3, 4], [5, 6, 7, 8], [9]]

Sorting Lists
^^^^^^^^^^^^^

The ``sort`` method sorts a list in place.

.. code-block:: python

    >>> a = [2, 10, 4, 3, 7]
    >>> a.sort()
    >>> a
    [2, 3, 4, 7 10]

The built-in function ``sorted`` returns a new sorted list without modifying
the source list.

.. code-block:: python

    >>> a = [4, 3, 5, 9, 2]
    >>> sorted(a)
    [2, 3, 4, 5, 9]
    >>> a
    [4, 3, 5, 9, 2]

The behavior of ``sort`` method and ``sorted`` function is exactly same except that sorted returns a new list instead of modifying the given list.

The ``sort`` method works even when the list has different types of objects and even lists.

.. code-block:: python

    >>> a = ["hello", 1, "world", 45, 2]
    >>> a.sort()
    >>> a
    [1, 2, 45, 'hello', 'world']
    >>> a = [[2, 3], [1, 6]]
    >>> a.sort()
    >>> a
    [[1, 6], [2, 3]]

We can optionally specify a function as sort key.

.. code-block:: python

    >>> a = [[2, 3], [4, 6], [6, 1]]
    >>> a.sort(key=lambda x: x[1])
    >>> a
    [[6, 1], [2, 3],  [4 6]]

This sorts all the elements of the list based on the value of second element of each entry.

.. problem:: Write a function ``lensort`` to sort a list of strings based on length.

.. code-block:: python

    >>> lensort(['python', 'perl', 'java', 'c', 'haskell', 'ruby'])
    ['c', 'perl', 'java', 'ruby', 'python', 'haskell']


.. problem:: Improve the `unique` function written in previous problems to take
   an optional `key` function as argument and use the return value of the key
   function to check for uniqueness.

.. code-block:: python

	>>> unique(["python", "java", "Python", "Java"], key=lambda s: s.lower())
	["python", "java"]
