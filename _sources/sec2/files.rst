Working With Files
==================

Python provides a built-in function ``open`` to open a file, which returns a file object.

.. code-block:: python

    f = open('foo.txt', 'r') # open a file in read mode
    f = open('foo.txt', 'w') # open a file in write mode
    f = open('foo.txt', 'a') # open a file in append mode

The second argument to ``open`` is optional, which defaults to ``'r'`` when not specified.

Unix does not distinguish binary files from text files but windows does. On windows ``'rb'``, ``'wb'``, ``'ab'`` should be used to open a binary file in read, write and append mode respectively.

Easiest way to read contents of a file is by using the ``read`` method.

.. code-block:: python

    >>> open('foo.txt').read()
    'first line\nsecond line\nlast line\n'

Contents of a file can be read line-wise using ``readline`` and ``readlines`` methods.
The ``readline`` method returns empty string when there is nothing more to read in a file.

.. code-block:: python

    >>> open('foo.txt').readlines()
    ['first line\n', 'second line\n', 'last line\n']
    >>> f = open('foo.txt')
    >>> f.readline()
    'first line\n'
    >>> f.readline()
    'second line\n'
    >>> f.readline()
    'last line\n'
    >>> f.readline()
    ''

The ``write`` method is used to write data to a file opened in write or append mode.

.. code-block:: python

    >>> f = open('foo.txt', 'w')
    >>> f.write('a\nb\nc')
    >>> f.close()

    >>> f.open('foo.txt', 'a')
    >>> f.write('d\n')
    >>> f.close()

The ``writelines`` method is convenient to use when the data is available as a list of lines.

.. code-block:: python

    >>> f = open('foo.txt')
    >>> f.writelines(['a\n', 'b\n', 'c\n'])
    >>> f.close()

Example: Word Count
^^^^^^^^^^^^^^^^^^^

Lets try to compute the number of characters, words and lines in a file.

Number of characters in a file is same as the length of its contents.

.. code-block:: python

    def charcount(filename):
        return len(open(filename).read())

Number of words in a file can be found by splitting the contents of the file.

.. code-block:: python

    def wordcount(filename):
        return len(open(filename).read().split())

Number of lines in a file can be found from ``readlines`` method.

.. code-block:: python

    def linecount(filename):
        return len(open(filename).readlines())

.. problem:: Write a program ``reverse.py`` to print lines of a file in reverse order.

.. code-block:: text

      $ cat she.txt
      She sells seashells on the seashore;
      The shells that she sells are seashells I'm sure.
      So if she sells seashells on the seashore,
      I'm sure that the shells are seashore shells.

      $ python reverse.py she.txt
      I'm sure that the shells are seashore shells.
      So if she sells seashells on the seashore,
      The shells that she sells are seashells I'm sure.
      She sells seashells on the seashore;

.. problem:: Write a program to print each line of a file in reverse order.

.. problem:: Implement unix commands ``head`` and ``tail``. The ``head`` and ``tail`` commands take a file as argument and prints its first and last 10 lines of the file respectively.

.. problem:: Implement unix command ``grep``. The ``grep`` command takes a string and a file as arguments and prints all lines in the file which contain the specified string.

.. code-block:: text

    $ python grep.py she.txt sure
    The shells that she sells are seashells I'm sure.
    I'm sure that the shells are seashore shells.

.. problem:: Write a program `wrap.py` that takes filename and width as aruguments and wraps the lines longer than `width`.

.. code-block:: text

    $ python wrap.py she.txt 30
    I'm sure that the shells are s
    eashore shells.
    So if she sells seashells on t
    he seashore,
    The shells that she sells are
    seashells I'm sure.
    She sells seashells on the sea
    shore;

.. problem:: The above wrap program is not so nice because it is breaking the line at middle of any word. Can you write a new program `wordwrap.py` that works like `wrap.py`, but breaks the line only at the word boundaries?

.. code-block:: text

    $ python wordwrap.py she.txt 30
    I'm sure that the shells are
    seashore shells.
    So if she sells seashells on
    the seashore,
    The shells that she sells are
    seashells I'm sure.
    She sells seashells on the
    seashore;

.. problem:: Write a program `center_align.py` to center align all lines in the given file.

.. code-block:: text

    $ python center_align.py she.txt
      I'm sure that the shells are seashore shells.
        So if she sells seashells on the seashore,
    The shells that she sells are seashells I'm sure.
           She sells seashells on the seashore;
