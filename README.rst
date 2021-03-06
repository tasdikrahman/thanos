thanos
======

|Build Status| |percentagecov| |grade| |Requirements Status| |License| 

.. image :: http://imgs.xkcd.com/comics/exploits_of_a_mom.png
    :target: https://xkcd.com/327/

:Author: `Tasdik Rahman <http://tasdikrahman.me>`__

.. contents::
    :backlinks: none

.. sectnum::

About
=====

`[Back to top] <https://github.com/prodicus/thanos#thanos>`__

A little taste of what can happen when you pass parameterized
arguments in your query strings.

Will be using a GUI as an interface between the user and the database and try out
different vulnerable strings and see if we can acess the database

**NOTE**: 

+---------------------------------------------------------------------------+------------------------------------------------------------------------------------------+
| **Vulnerabilities (demo)**                                                | **mitigated version**                                                                    |
+===========================================================================+==========================================================================================+
| `thanos/vulnerable <https://github.com/prodicus/thanos/tree/develop>`__   | `thanos/input-validation <https://github.com/prodicus/thanos/tree/input-validation>`__   |
+---------------------------------------------------------------------------+------------------------------------------------------------------------------------------+

Plan of action
~~~~~~~~~~~~~~

- [✓] Test for ``SQL Injection`` vulnerabilities
- [✓] Test for ``Input validation`` techniques
- [✓] Suggest fixes to the vulnerabilities found(if any)
- [✓] making the GUI using tkinter
- [ ] **Writing testcases**

Mitigation techniques
~~~~~~~~~~~~~~~~~~~~~

- [✓] Validating email entered by using custom `regex`
- [✓] Replacing the parameterized ``SQL constructs`` in the code and replace it with pythonic API

DEMO
====

**NOTE** This is the secure version of the demo. Refer the `vulnerable one here <https://github.com/prodicus/thanos/tree/develop#3show-me-what-you-have-done-so-far>`__

The database has the following user credentials in it

.. code:: bash

    tasdik at Acer in ~/Dropbox/projects/thanos on input-validation
    $ sqlite3 sare_log.db 
    -- Loading resources from /home/tasdik/.sqliterc

    SQLite version 3.9.2 2015-11-02 18:31:45
    Enter ".help" for usage hints.
    sqlite> select * from users;
    email            name        serial_no   password  
    ---------------  ----------  ----------  ----------
    admin@gmail.com  Admin       1           admin123  
    foo@outlook.com  bar         2           foo123    
    john@yahoo.com   doe         3           john123   
    sqlite> 


**When you enter correct user credentials which are there in the database**. 

.. image:: http://i.imgur.com/DwClAPm.jpg
   :alt:


**If a wrong user details are entered**. Notice that the SQL statements don't get executed


.. image:: http://i.imgur.com/wVOG85S.jpg
   :alt:


**SQL injection anybody?**


.. image:: http://i.imgur.com/42YhmpU.jpg
   :alt:


**The threat was mitigated as the malicious SQL query was not executed**

Running it
==========
`[Back to top] <https://github.com/prodicus/thanos#thanos>`__

*Urm. So how do I run it?*

Installing the dependencies
~~~~~~~~~~~~~~~~~~~~~~~~~~~

I prefer to use `virtual environments <http://docs.python-guide.org/en/latest/dev/virtualenvs/>`__ for keeping the global ``python`` interpreter clutter free. But you are free to do a system wide install for the dependencies.

**You should have `make` installed on your system.**

.. code:: bash

    $ git clone https://github.com/prodicus/thanos && cd thanos
    $ make install

If ``make install`` gives you an error. Try this

.. code:: bash

    $ pip install -r requirements.txt


Running it!
~~~~~~~~~~~

.. code:: bash

    $ make run

Cleaning it up

.. code:: bash

    $ make clean

When in doubt
~~~~~~~~~~~~~

.. code:: bash

    $ make help

FAQ
===
`[Back to top] <https://github.com/prodicus/thanos#thanos>`__

Okay, But what does it do?
~~~~~~~~~~~~~~~~~~~~~~~~~~

- So there's this database called ``sare_log.db``, (which translates to ``all_people`` in english). We have some users details stored inside this database.

- We try to exploit the database testing for some common vulnerabilities like
  - SQL injection
  - input validation

- **More to come**

Will I be able to run it on my PC?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

I have tested this on MAC and Linux based systems currently

What's with the name?
~~~~~~~~~~~~~~~~~~~~~

Nothing! It's just that I read a lot of Marvel comics.

The code looks messy!
~~~~~~~~~~~~~~~~~~~~~

*Well, so does your mom!*

Jokes apart. As I said, this is still a  work in progress.

Contributing
============
`[Back to top] <https://github.com/prodicus/thanos#thanos>`__

Refer `CONTRIBUTING.rst <https://github.com/prodicus/thanos/blob/input-validation/CONTRIBUTING.rst>`__

Issues
~~~~~~

`[Back to top] <https://github.com/prodicus/thanos#thanos>`__

This project is still work in progress so feel free to make PR or give
suggestions by `creating an issue <https://github.com/prodicus/thanos/issues>`__

Contributers
~~~~~~~~~~~~
`[Back to top] <https://github.com/prodicus/thanos#thanos>`__

Built with ♥ and after a lot of marshmellows by

-  `Tasdik Rahman <http://tasdikrahman.me>`__ `(@tasdikrahman) <https://twitter.com/tasdikrahman>`__
-  `Nitesh Sharma <https://github/com/sinscary>`__
-  `Gaurab Chakraborty <https://github.com/GaurabChakraborty>`__
-  `Keerthika Shekhar <https://github.com/kirthishekhar95>`__

Legal Stuff
===========
`[Back to top] <https://github.com/prodicus/thanos#thanos>`__

Built and maintained by `Tasdik Rahman <http://tasdikrahman.me>`__ released under the `MIT License <http://prodicus.mit-license.com>`__. See the bundled `LICENSE <https://github.com/prodicus/thanos/blob/master/LICENSE>`_ file for more details.

.. |Build Status| image:: https://travis-ci.org/prodicus/thanos.svg?branch=input-validation
    :target: https://travis-ci.org/prodicus/thanos
.. |Requirements Status| image:: https://requires.io/github/prodicus/thanos/requirements.svg?branch=input-validation
    :target: https://requires.io/github/prodicus/thanos/requirements/?branch=input-validation
    :alt: Requirements Status
.. |License| image:: https://img.shields.io/pypi/l/pyzipcode-cli.svg
.. |grade| image:: https://api.codacy.com/project/badge/grade/e2cb32eae16242f795f498d40d0d8984
    :target: https://www.codacy.com/app/tasdik95/thanos
.. |percentagecov| image:: https://api.codacy.com/project/badge/coverage/e2cb32eae16242f795f498d40d0d8984
    :target: https://www.codacy.com/app/tasdik95/thanos