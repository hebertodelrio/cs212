Modules
=======

Modules are libraries in Python. Python ships with many standard library modules.

A module can be imported using the ``import`` statement.

Lets look at ``time`` module for example:

.. code-block:: python

    >>> import time
    >>> time.asctime()
    'Tue Sep 11 21:42:06 2012'

The ``asctime`` function from the ``time`` module returns the current time of
the system as a string.

The ``sys`` module provides access to the list of arguments passed to the
program, among the other things.

The ``sys.argv`` variable contains the list of arguments passed to the program.
As a convention, the first element of that list is the name of the program.

Lets look at the following program ``echo.py`` that prints the first argument
passed to it.

.. code-block:: python

    import sys
    print(sys.argv[1])

Lets try running it.

.. code-block:: python

    $ python echo.py hello
    hello
    $ python echo.py hello world
    hello

There are many more interesting modules in the standard library. We'll learn
more about them in the coming chapters.

.. problem:: Write a program ``add.py`` that takes 2 numbers as command line
   arguments and prints its sum.

.. code-block:: python

    $ python add.py 3 5
    8
    $ python add.py 2 9
    11
