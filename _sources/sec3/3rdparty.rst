Installing third-party modules
==============================

PyPI, The Python Package Index maintains the list of Python packages available. The third-party module developers usually register at PyPI and uploads their packages there.

The standard way to installing a python module is using `pip` or `easy_install`. Pip is more modern and perferred.

Lets start with installing `easy_install`.

* Download the easy_install install script `ez_setup.py <http://peak.telecommunity.com/dist/ez_setup.py>`_.
* Run it using Python.

That will install ``easy_install``, the script used to install third-party python packages.

Before installing new packages, lets understand how to manage virtual environments for installing python packages.

Earlier the only way of installing python packages was system wide. When used this way, packages installed for one project can conflict with other and create trouble. So people invented a way to create isolated Python environment to install packages. This tool is called `virtualenv <http://www.virtualenv.org/>`_.

To install ``virtualenv``:

    $ easy_install virtualenv

Installing virtualenv also installs the `pip` command, a better replace for `easy_install`.

Once it is installed, create a new virtual env by running the ``virtualenv`` command.

.. code-block:: text

    $ virtualenv testenv

Now to switch to that env.

On UNIX/Mac OS X:

.. code-block:: text

    $ source testenv/bin/activate

On Windows:

.. code-block:: text

    > testenv\Scripts\activate

Now the virtualenv `testenv` is activated.

Now all the packages installed will be limited to this virtualenv. Lets try to install a third-party package.

.. code-block:: text

    $ pip install tablib

This installs a third-party library called ``tablib``.

The ``tablib`` library is a small little library to work with tabular data and write csv and Excel files.

Here is a simple example.

.. code-block:: python

    # create a dataset
    data = tablib.Dataset()

    # Add rows
    data.append(["A", 1])
    data.append(["B", 2])
    data.append(["C", 3])

    # save as csv
    with open('test.csv', 'wb') as f:
        f.write(data.csv)

    # save as Excel
    with open('test.xls', 'wb') as f:
        f.write(data.xls)

    # save as Excel 07+
    with open('test.xlsx', 'wb') as f:
        f.write(data.xlsx)

It is even possible to create multi-sheet excel files.

.. code-block:: python

    sheet1 = tablib.Dataset()
    sheet1.append(["A1", 1])
    sheet1.append(["A2", 2])

    sheet2 = tablib.Dataset()
    sheet2.append(["B1", 1])
    sheet2.append(["B2", 2])


    book = tablib.Databook([data1, data2])
    with open('book.xlsx', 'wb') as f:
        f.write(book.xlsx)

.. problem:: Write a program ``csv2xls.py`` that reads a csv file and exports
   it as Excel file. The prigram should take two arguments. The name of the csv
   file to read as first argument and the name of the Excel file to write as the
   second argument.

.. code-block: text

    $ python csv2xls.py a.csv a.xls

.. problem:: Create a new virtualenv and install BeautifulSoup. BeautifulSoup
   is very good library for parsing HTML. Try using it to extract all HTML
   links from a webpage.
