Strings
=======

Strings also behave like lists in many ways.
Length of a string can be found using built-in function ``len``.

.. code-block:: python

    >>> len("abrakadabra")
    11

Indexing and slicing on strings behave similar to that of lists.

.. code-block:: python

    >>> a = "helloworld"
    >>> a[1]
    'e'
    >>> a[-2]
    'l'
    >>> a[1:5]
    "ello"
    >>> a[:5]
    "hello"
    >>> a[5:]
    "world"
    >>> a[-2:]
    'ld'
    >>> a[:-2]
    'hellowor'
    >>> a[::-1]
    'dlrowolleh'

The ``in`` operator can be used to check if a string is present in another string.

    >>> 'hell' in 'hello'
    True
    >>> 'full' in 'hello'
    False
    >>> 'el' in 'hello'
    True

There are many useful methods on strings.

The ``split`` method splits a string using a delimiter. If no delimiter is specified, it uses any whitespace char as delimiter.

.. code-block:: python

    >>> "hello world".split()
    ['hello', 'world']
    >>> "a,b,c".split(',')
    ['a', 'b', 'c']

The ``join`` method joins a list of strings.

.. code-block:: python

    >>> " ".join(['hello', 'world'])
    'hello world'
    >>> ','.join(['a', 'b', 'c'])

The ``strip`` method returns a copy of the given string with leading and trailing whitespace removed. Optionally a string can be passed as argument to remove characters from that string instead of whitespace.

.. code-block:: python

    >>> ' hello world\n'.strip()
    'hello world'
    >>> 'abcdefgh'.strip('abdh')
    'cdefg'

Python supports formatting values into strings. Although this can include very complicated expressions, the most basic usage is to insert values into a string with the %s placeholder.

.. code-block:: python

    >>> a = 'hello'
    >>> b = 'python'
    >>> "%s %s" % (a, b)
    'hello python'
    >>> 'Chapter %d: %s' % (2, 'Data Structures')
    'Chapter 2: Data Structures'

.. problem:: Write a function ``extsort`` to sort a list of files based on extension.

.. code-block:: python

    >>> extsort(['a.c', 'a.py', 'b.py', 'bar.txt', 'foo.txt', 'x.c'])
    ['a.c', 'x.c', 'a.py', 'b.py', 'bar.txt', 'foo.txt']
