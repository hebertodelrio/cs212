Modules
=======

Modules are reusable libraries of code in Python. Python comes with many standard library modules.

A module is imported using the `import` statement.

.. code-block:: python

    >>> import time
    >>> print time.asctime()
    'Fri Mar 30 12:59:21 2012'

In this example, we've imported the `time` module and called the `asctime`
function from that module, which returns current time as a string.

There is also another way to use the import statement.

.. code-block:: python

    >>> from time import asctime
    >>> asctime()
    'Fri Mar 30 13:01:37 2012'

Here were imported just the `asctime` function from the `time` module.

The `pydoc` command provides help on any module or a function.

.. code-block:: text

    $ pydoc time
    Help on module time:

    NAME
        time - This module provides various functions to manipulate time values.
    ...

    $ pydoc time.asctime
    Help on built-in function asctime in time:

    time.asctime = asctime(...)
        asctime([tuple]) -> string
    ...

On Windows, the `pydoc` command is not available. The work-around is to use, the built-in `help` function.

.. code-block:: text

    >>> help('time')
    Help on module time:

    NAME
        time - This module provides various functions to manipulate time values.
    ...

Writing our own modules is very simple.

For example, create a file called `num.py` with the following content.

.. code-block:: python

    def square(x):
        return x * x

    def cube(x):
        return x * x * x

Now open Python interterter:

    >>> import num
    >>> num.square(3)
    9
    >>> num.cube(3)
    27

Thats all we've written a python library.

Try `pydoc num` (`pydoc.bat numbers` on Windows) to see documentation for this numbers modules. It won't have any documentation as we haven't providied anything yet.

In Python, it is possible to associate documentation for each module, function using docstrings. Docstrings are strings written at the top of the module or at the beginning of a function.

Lets try to document our `num` module by changing the contents of `num.py`

.. code-block:: python

    """The num module provides utilties to work on numbers.

    Current it provides square and cube.
    """

    def square(x):
        """Computes square of a number."""
        return x * x

    def cube(x):
        """Computes cube of a number."""
        return x * x

The pydoc command will now show us the doumentation nicely formatted.

.. code-block:: text

    Help on module num:

    NAME
        num - The num module provides utilties to work on numbers.

    FILE
        /Users/anand/num.py

    DESCRIPTION
        Current it provides square and cube.

    FUNCTIONS
        cube(x)
            Computes cube of a number.

        square(x)
            Computes square of a number.

Under the hood, python stores the documentation as a special field called `__doc__`.

.. code-block:: python

    >>> import os
    >>> print os.getcwd.__doc__
    getcwd() -> path

    Return a string representing the current working directory.
