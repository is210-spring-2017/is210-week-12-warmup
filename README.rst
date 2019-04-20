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

#.  One a new cell in your notebook, type the following function

.. code:: pycon

    >>> import datetime
    
    >>> class InvalidAgeError(Exception):
        pass
    
    >>> def get_age(birthyear):
            age = datetime.datetime.now().year - birthyear
            return age

#.  Add a check that tests whether or not the person has a valid (0 or greater)

#.  If the age is invalid, raise an ``InvalidAgeError``

Expected Output
^^^^^^^^

.. code:: pycon

    >>> get_age(2099)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    __main__.InvalidAgeError



Submission
==========

Code should be submitted via Blackboard.

.. _GitHub: https://github.com/
.. _Python String Documentation: https://docs.python.org/2/library/stdtypes.html
