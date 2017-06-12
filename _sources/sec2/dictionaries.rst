Dictionaries
============

Dictionaries are like lists, but they can be indexed with non integer keys also. Unlike lists, dictionaries are not ordered.

.. code-block:: python

    >>> a = {'x': 1, 'y': 2, 'z': 3}
    >>> a['x']
    1
    >>> a['z']
    3
    >>> b = {}
    >>> b['x'] = 2
    >>> b[2] = 'foo'
    >>> b[(1, 2)] = 3
    >>> b
    {(1, 2): 3, 'x': 2, 2: 'foo'}

The ``del`` keyword can be used to delete an item from a dictionary.

.. code-block:: python

    >>> a = {'x': 1, 'y': 2, 'z': 3}
    >>> del a['x']
    >>> a
    {'y': 2, 'z': 3}

The ``keys`` method returns all keys in a dictionary, the ``values`` method returns all values in a dictionary and ``items`` method returns all key-value pairs in a dictionary.

.. code-block:: python

    >>> a.keys()
    ['x', 'y', 'z']
    >>> a.values()
    [1, 2, 3]
    >>> a.items()
    [('x', 1), ('y', 2), ('z', 3)]

The ``for`` statement can be used to iterate over a dictionary.

.. code-block:: python

    >>> for key in a: print key
    ...
    x
    y
    z
    >>> for key, value in a.items(): print key, value
    ...
    x 1
    y 2
    z 3

Presence of a key in a dictionary can be tested using ``in`` operator or ``has_key`` method.

.. code-block:: python

    >>> 'x' in a
    True
    >>> 'p' in a
    False
    >>> a.has_key('x')
    True
    >>> a.has_key('p')
    False

Other useful methods on dictionaries are ``get`` and ``setdefault``.

.. code-block:: python

    >>> d = {'x': 1, 'y': 2, 'z': 3}
    >>> d.get('x', 5)
    1
    >>> d.get('p', 5)
    5
    >>> d.setdefault('x', 0)
    1
    >>> d
    {'x': 1, 'y': 2, 'z': 3}
    >>> d.setdefault('p', 0)
    0
    >>> d
    {'y': 2, 'x': 1, 'z': 3, 'p': 0}

Dictionaries can be used in string formatting to specify named parameters.

.. code-block:: python

    >>> 'hello %(name)s' % {'name': 'python'}
    'hello python'
    >>> 'Chapter %(index)d: %(name)s' % {'index': 2, 'name': 'Data Structures'}
    'Chapter 2: Data Structures'

Example: Word Frequency
^^^^^^^^^^^^^^^^^^^^^^^

Suppose we want to find number of occurrences of each word in a file.
Dictionary can be used to store the number of occurrences for each word.

Lets first write a function to count frequency of words, given a list of words.

.. code-block:: python

    def word_frequency(words):
        """Returns frequency of each word given a list of words.

            >>> word_frequency(['a', 'b', 'a'])
            {'a': 2, 'b': 1}
        """
        frequency = {}
        for w in words:
            frequency[w] = frequency.get(w, 0) + 1
        return frequency

Getting words from a file is very trivial.

.. code-block:: python

    def read_words(filename):
        return open(filename).read().split()

We can combine these two functions to find frequency of all words in a file.

.. code-block:: python

    def main(filename):
        frequency = word_frequency(read_words(filename))
        for word, count in frequency.items():
            print word, count

    if __name__ == "__main__":
        import sys
        main(sys.argv[1])

.. problem:: Improve the above program to print the words in the descending order of the number of occurrences.

.. problem:: Write a program to count frequency of characters in a given file. Can you use character frequency to tell whether the given file is a Python program file, C program file or a text file?

.. problem:: Write a program to find anagrams in a given list of words. Two words are called anagrams if one word can be formed by rearranging letters of another. For example 'eat', 'ate' and 'tea' are anagrams.

.. code-block:: python

    >>> anagrams(['eat', 'ate', 'done', 'tea', 'soup', 'node'])
    [['eat', 'ate', 'tea], ['done', 'node'], ['soup']]

.. problem:: Write a function ``valuesort`` to sort values of a dictionary based on the key.

.. code-block:: python

    >>> valuesort({'x': 1, 'y': 2, 'a': 3})
    [3, 1, 2]

.. problem:: Write a function ``invertdict`` to interchange keys and values in a dictionary. For simplicity, assume that all values are unique.

.. code-block:: python

    >>> invertdict({'x': 1, 'y': 2, 'z': 3})
    {1: 'x', 2: 'y', 3: 'z'}

Understanding Python Execution Environment (optional)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Python stores the variables we use as a dictionary. The ``globals()`` function returns all the globals variables in the current environment.

.. code-block:: python

    >>> globals()
    {'__builtins__': <module '__builtin__' (built-in)>, '__name__': '__main__', '__doc__': None}
    >>> x = 1
    >>> globals()
    {'__builtins__': <module '__builtin__' (built-in)>, '__name__': '__main__', '__doc__': None, 'x': 1}
    >>> x = 2
    >>> globals()
    {'__builtins__': <module '__builtin__' (built-in)>, '__name__': '__main__', '__doc__': None, 'x': 2}
    >>> globals()['x'] = 3
    >>> x
    3

Just like ``globals`` python also provides a function ``locals`` which gives all the local variables in a function.

.. code-block:: python

    >>> def f(a, b): print locals()
    ...
    >>> f(1, 2)
    {'a': 1, 'b': 2}

One more example:

.. code-block:: python

    >>> def f(name):
    ...     return "Hello %(name)s!" % locals()
    ...
    >>> f("Guido")
    Hello Guido!
