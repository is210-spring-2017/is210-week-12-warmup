####################
IS 210 Assignment 12
####################
************
Warmup Tasks
************

:College: CUNY School of Professional Studies
:Course-Name: Software Application Programming I
:Course-Code: IS 210

Overview
========

This week, we learn about a pillar of the pantheon of Python programming
paradigms: exceptions. Throughout this assignment you will be challenged
to both use and consider the use of exceptions as a control mechanisms
withing your programs.

Instructions
============

The following tasks will either have you interacting with existing files in
the assignment repository or creating new ones on the fly. Don't forget to add
your interpreter directive, utf-8 encoding, and a short docstring with any new
files that you create!

.. important::

    In these exercises, you may, on occasion, come across a task that requres
    you to research or use a function or method not directly covered by the
    course text. Since Python is such a large language it would be impossible
    for the author to have included descriptions of each and every available
    function which would largely duplicate the offical Python documentation.

    A *vital* skill to successful programming is being comfortable searching
    for and using official language documentation sources like the
    `Python String Documentation`_ page. Throughout our coursework we will be
    practicing both the use of the language in practice and the search skills
    necessary to become functional programmers.

Warmup Tasks
============

Task 01
-------

In this exercise you'll be adding exception handling to a function that
already exists.

Specifications
^^^^^^^^^^^^^^

#.  On a new notebook, paste function below


.. code:: pycon

    >>> def simple_lookup(var1, var2)
            return var1[var2]

#.  Add exception handling to the ``simple_lookup()`` function so that
    attempts to access any index or key of ``var1`` that do not exist will
    print a warning message and return ``var1``

#.  Allow all other exceptions to fail normally.

.. tip::

    There is a single exception class that suits this best.
    
Expected Output
^^^^^^^

.. code:: pycon

    >>> simple_lookup([1,2], 4)
    Warning: Your index/key doesn't exist.
    [1,2]
    >>> simple_lookup({}, 'banana')
    Warning: Your index/key doesn't exist.
    {}

Task 02
-------

In this exercise, you'll raise a manual exception when a condition is not
met in a particular function. In particular, we'll be converting birth year to
age.

Specifications
^^^^^^^^^^^^^^

#.  Open ``task_02.py``

#.  Add a check that tests whether or not the person has a valid (0 or greater)

#.  If the age is invalid, raise an ``InvalidAgeError``

Examples
^^^^^^^^

.. code:: pycon

    >>> get_age(2099)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    __main__.InvalidAgeError

Task 03
-------

The ``finally`` clause is particularly useful in handling cleanup tasks such
as closing file descriptors or data streams.

Specifications
^^^^^^^^^^^^^^

#.  Open ``task_03.py``. This class represents a very simple logging class.
    Python offers much-better built-in loggers but this is a good teaching
    example.

#.  Modify ``flush()`` so that any predictable errors are caught and are,
    themselves, logged.

    #.  If the target logfile cannot be opened, log this fact then re-raise
        the error.

    #.  Upon encountering any other ``IOError``, log the error and stop loop
        loop processing (but continue with the rest of the program)

    #.  Do not allow stored messages to be removed from the ``msgs`` object if
        they cannot be written to the disk.

    #.  Allow msgs processing to continue as long as it doesn't encounter an
        ``IOError``

    #.  Upon encountering any other error, use the ``log()`` method to log the
        error encountered

#.  Ensure that the ``close()`` method is called no matter what exceptions are
    encountered.

.. note::

    Unit testing will be limited in this particular question as exception
    handling largely defeats changes in program state and, to be frank, Python
    is just really good with polymorphism. There's almost nothing that can
    trigger an exception with str()!

Executing Tests
===============

Code must be functional and pass tests before it will be eligible for credit.

Linting
-------

Lint tests check your code for syntactic or stylistic errors To execute lint
tests against a specific file, simply open a terminal in the same directory as
your code repository and type:

.. code:: console

    $ pylint filename.py

Where ``filename.py`` is the name of the file you wish to lint test.

Unit Tests
----------

Unit tests check that your code performs the tested objectives. Unit tests
may be executed individually by opening a terminal in the same directory as
your code repository and typing:

.. code:: console

    $ nosetests tests/name_of_test.py

Where ``name_of_test.py`` is the name of the testfile found in the ``tests``
directory of your source code.

Running All Tests
-----------------

All tests may be run simultaneously by executing the ``runtests.sh`` script
from the root of your assignment repository. To execute all tests, open a
terminal in the same directory as your code repository and type:

.. code:: console

    $ ./runtests.sh

Submission
==========

Code should be submitted via Blackboard.

.. _GitHub: https://github.com/
.. _Python String Documentation: https://docs.python.org/2/library/stdtypes.html
