State
=====

Suppose we want to model a bank account with support for ``deposit`` and ``withdraw`` operations. One way to do that is by using global state as shown in the following example.

.. code-block:: python

    balance = 0

    def deposit(amount):
        global balance
        balance += amount
        return balance

    def withdraw(amount):
        global balance
        balance -= amount
        return balance

The above example is good enough only if we want to have just a single account. Things start getting complicated if want to model multiple accounts.

We can solve the problem by making the state local, probably by using a dictionary to store the state.

.. code-block:: python

    def make_account():
        return {'balance': 0}

    def deposit(account, amount):
        account['balance'] += amount
        return account['balance']

    def withdraw(account, amount):
        account['balance'] -= amount
        return account['balance']

With this it is possible to work with multiple accounts at the same time.

.. code-block:: python

    >>> a = make_account()
    >>> b = make_account()
    >>> deposit(a, 100)
    100
    >>> deposit(b, 50)
    50
    >>> withdraw(b, 10)
    40
    >>> withdraw(a, 10)
    90
