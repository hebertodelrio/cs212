Standard Library
================

Python comes with many standard library modules. Lets look at some of the most commonly used ones.

os module
^^^^^^^^^

The `os` and `os.path` modules provides functionality to work with files, directories etc.


.. problem:: Write a program to list all files in the given directory.


.. problem:: Write a program `extcount.py` to count number of files for each
   extension in the given directory. The program should take a directory name
    as argument and print count and extension for each available file extension.

.. code-block:: text

    $ python extcount.py src/
    14 py
    4 txt
    1 csv

.. problem:: Write a program to list all the files in the given directory along
   with their length and last modification time. The output should contain one
   line for each file containing filename, length and modification date separated
   by tabs.

   Hint: see help for ``os.stat``.

.. problem:: Write a program to print directory tree. The program should take
   path of a directory as argument and print all the files in it recursively as
   a tree.

.. code-block:: text

    $ python dirtree.py foo
    foo
    |-- a.txt
    |-- b.txt
    |-- code
    |   |-- a.py
    |   |-- b.py
    |   |-- docs
    |   |   |-- a.txt
    |   |   \-- b.txt
    |   \-- x.py
    \-- z.txt


urllib module
^^^^^^^^^^^^^

The `urllib` module provides functionality to download webpages.

.. code-block:: python

    >>> import urllib
    >>> response = urllib.urlopen("http://python.org/")
    >>> print response.headers
    Date: Fri, 30 Mar 2012 09:24:55 GMT
    Server: Apache/2.2.16 (Debian)
    Last-Modified: Fri, 30 Mar 2012 08:42:25 GMT
    ETag: "105800d-4b7b-4bc71d1db9e40"
    Accept-Ranges: bytes
    Content-Length: 19323
    Connection: close
    Content-Type: text/html
    X-Pad: avoid browser bug

    >>> response.header['Content-Type']
    'text/html'

    >>> content = request.read()

.. problem:: Write a program wget.py to download a given URL. The program should accept a URL as argument, download it and save it with the basename of the URL. If the URL ends with a /, consider the basename as index.html.

.. code-block:: text

     $ python wget.py http://docs.python.org/tutorial/interpreter.html
     saving http://docs.python.org/tutorial/interpreter.html as interpreter.html.

     $ python wget.py http://docs.python.org/tutorial/
     saving http://docs.python.org/tutorial/ as index.html.

re module
^^^^^^^^^

.. problem:: Write a program antihtml.py that takes a URL as argument, downloads the html from web and print it after stripping html tags.

.. code-block:: text

    $ python antihtml.py index.html
    ...
    The Python interpreter is usually installed as /usr/local/bin/python on
    those machines where it is available; putting /usr/local/bin in your
    ...

.. problem:: Write a function `make_slug` that takes a name converts it into a slug. A slug is a string where spaces and special characters are replaced by a hyphen, typically used to create blog post URL from post title. It should also make sure there are no more than one hyphen in any place and there are no hyphens at the biginning and end of the slug.

.. code-block:: python

    >>> make_slug("hello world")
    'hello-world'
    >>> make_slug("hello  world!")
    'hello-world'
    >>> make_slug(" --hello-  world--")
    'hello-world'

.. problem:: Write a program `links.py` that takes URL of a webpage as argument
   and prints all the URLs linked from that webpage.

.. problem:: Write a regular expression to validate a phone number.

json module
^^^^^^^^^^^

.. problem:: Write a program myip.py to print the external IP address of the
   machine. Use the response from ``http://httpbin.org/get`` and read the IP
   address from there. The program should print only the IP address and nothing
   else.

zipfile module
^^^^^^^^^^^^^^

The `zipfile` module provides interface to read and write zip files.

Here are some examples to demonstate the power of zipfile module.

The following example prints names of all the files in a zip archive.

.. code-block:: python

    import zipfile
    z = zipfile.ZipFile("a.zip")
    for name in z.namelist():
        print name

The following example prints each file in the zip archive.

.. code-block:: python

    import zipfile
    z = zipfile.ZipFile("a.zip")
    for name in z.namelist():
        print
        print "FILE:", name
        print
        print z.read(name)

.. problem:: Write a python program `zip.py` to create a zip file. The program should take name of zip file as first argument and files to add as rest of the arguments.

.. code-block:: text

    $ python zip.py foo.zip file1.txt file2.txt


.. problem:: Write a program `mydoc.py` to implement the functionality of pydoc. The program should take the module name as argument and print documentation for the module and each of the functions defined in that module.

.. code-block:: text

    $ python mydoc.py os
    Help on module os:

    DESCRIPTION

    os - OS routines for Mac, NT, or Posix depending on what system we're on.
    ...

    FUNCTIONS

    getcwd()
        ...

Hints:
    * The `dir` function to get all entries of a module
    * The `inspect.isfunction` function can be used to test if given object is a function
    * `x.__doc__` gives the docstring for x.
    * The `__import__` function can be used to import a module by name
