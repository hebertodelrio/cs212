Errors and Exceptions
=====================

We've already seen exceptions in various places. Python gives ``NameError``
when we try to use a variable that is not defined.

.. code-block:: python

    >>> foo
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    NameError: name 'foo' is not defined

try adding a string to an integer:

.. code-block:: python

    >>> "foo" + 2
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: cannot concatenate 'str' and 'int' objects

try dividing a number by 0:

.. code-block:: python

    >>> 2/0
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ZeroDivisionError: integer division or modulo by zero

or, try opening a file that is not there:

.. code-block:: python

    >>> open("not-there.txt")
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    IOError: [Errno 2] No such file or directory: 'not-there.txt'

Python raises exception in case errors. We can write programs to handle such
errors. We too can raise exceptions when an error case in encountered.

Exceptions are handled by using the try-except statements.

.. code-block:: python

    def main():
        filename = sys.argv[1]
        try:
            for row in parse_csv(filename):
                print row
        except IOError:
            print >> sys.stderr, "The given file doesn't exist: ", filename
            sys.exit(1)

This above example prints an error message and exits with an error status when an IOError is encountered.

The `except` statement can be written in multiple ways:

.. code-block:: python

    # catch all exceptions
    try:
        ...
    except:

    # catch just one exception
    try:
        ...
    except IOError:
        ...

    # catch one exception, but provide the exception object
    try:
        ...
    except IOError, e:
        ...

    # catch more than one exception
    try:
        ...
    except (IOError, ValueError), e:
        ...

It is possible to have more than one `except` statements with one `try`.

.. code-block:: python

    try:
        ...
    except IOError, e:
        print >> sys.stderr, "Unable to open the file (%s): %s" % (str(e), filename)
        sys.exit(1)
    except FormatError, e:
        print >> sys.stderr, "File is badly formatted (%s): %s" % (str(e), filename)

The `try` statement can have an optional `else` clause, which is
executed only if no exception is raised in the try-block.

.. code-block:: python

    try:
        ...
    except IOError, e:
        print >> sys.stderr, "Unable to open the file (%s): %s" % (str(e), filename)
        sys.exit(1)
    else:
        print "successfully opened the file", filename

There can be an optional `else` clause with a `try` statement, which is executed
irrespective of whether or not exception has occured.

.. code-block:: python

    try:
        ...
    except IOError, e:
        print >> sys.stderr, "Unable to open the file (%s): %s" % (str(e), filename)
        sys.exit(1)
    finally:
        delete_temp_files()

Exception is raised using the raised keyword.

.. code-block:: python

    raise Exception("error message")

All the exceptions are extended from the built-in `Exception` class.

    class ParseError(Exception):
        pass

.. problem:: What will be the output of the following program?

.. code-block:: python

    try:
        print "a"
    except:
        print "b"
    else:
        print "c"
    finally:
        print "d"

.. problem:: What will be the output of the following program?

.. code-block:: python

    try:
        print "a"
        raise Exception("doom")
    except:
        print "b"
    else:
        print "c"
    finally:
        print "d"


.. problem:: What will be the output of the following program?

.. code-block:: python

    def f():
        try:
            print "a"
            return
        except:
            print "b"
        else:
            print "c"
        finally:
            print "d"

    f()
