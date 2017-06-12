Python Interpreter & Scripts
============================

Running Python Interpreter
--------------------------

Python comes with an interactive interpreter. When you type ``python`` in your
shell or command prompt, the python interpreter becomes active with a ``>>>``
prompt and waits for your commands.

.. code-block:: python

    $ python
    Python 3.6.1 |Anaconda custom (x86_64)| (default, May 11 2017, 13:04:09)
    [GCC 4.2.1 Compatible Apple LLVM 6.0 (clang-600.0.57)] on darwin
    Type "help", "copyright", "credits" or "license" for more information
    >>>

Now you can type any valid python expression at the prompt. python reads the
typed expression, evaluates it and prints the result.

.. code-block:: python

    >>> 42
    42
    >>> 4 + 2
    6

.. problem :: Open a new Python interpreter and use it to find the value of ``2 + 3``.

Running Python Scripts
----------------------

Open your text editor, type the following text and save it as ``hello.py``.

.. code-block:: python

    print("hello, world!")

And run this program by calling ``python hello.py``. Make sure you change to
the directory where you saved the file before doing it.

.. code-block:: python

    gauss:~ heberto$ python hello.py
    hello, world!
    gauss:~ heberto$

Text after ``#`` character in any line is considered as comment.

.. code-block:: python

    # This is helloworld program
    # run this as:
    #    python hello.py
    print("hello, world!")

.. problem:: Create a python script to print  ``hello, world!`` four times, once in a row, four rows.

.. problem:: Create a python script to print  ``hello, world!`` four times in a row, separated by one space each.

.. problem:: Create a python script with the following text and see the output.

.. code-block:: python

    1 + 2

If it doesn't print anything, what changes can you make to the program to print the value?
