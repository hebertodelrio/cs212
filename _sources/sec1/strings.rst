Strings
=======

Strings are what you use to represent text.

Strings are a sequence of characters, enclosed in single quotes or double quotes.

.. code-block:: python

    >>> x = "hello"
    >>> y = 'world'
    >>> print(x, y)
    hello world

There is no difference between single quotes and double quotes, they can used interchangebly.

Multi-line strings can be written using three single quotes or three double quotes.

.. code-block:: python

    x = """This is a multi-line string
    written in
    three lines."""
    print(x)

    y = '''multi-line strings can be written
    using three single quote characters as well.
    The string can contain 'single quotes' or "double quotes"
    in side it.'''
    print(y)
