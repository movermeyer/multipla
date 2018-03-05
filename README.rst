
.. image:: https://travis-ci.org/monkeython/multipla.svg?branch=v0.3.3
    :target: https://travis-ci.org/monkeython/multipla
    :alt: Build status

.. image:: https://coveralls.io/repos/monkeython/multipla/badge.png?branch=v0.3.3
    :target: https://coveralls.io/r/monkeython/multipla?branch=master
    :alt: Test coverage

.. image:: https://readthedocs.org/projects/multipla/badge/?version=v0.3.3&style=default
    :target: http://multipla.readthedocs.org/en/latest/
    :alt: Read the Docs

.. image:: https://img.shields.io/pypi/dm/multipla.svg
    :target: https://pypi.python.org/pypi/multipla/
    :alt: Downloads

.. image:: https://img.shields.io/pypi/v/multipla.svg?label=latest
    :target: https://pypi.python.org/pypi/multipla/
    :alt: Latest Version

.. image:: https://img.shields.io/pypi/status/multipla.svg
    :target: https://pypi.python.org/pypi/multipla/
    :alt: Development Status

.. image:: https://img.shields.io/pypi/pyversions/multipla.svg
    :target: https://pypi.python.org/pypi/multipla/
    :alt: Supported Python versions

.. image:: https://img.shields.io/pypi/implementation/multipla.svg
    :target: https://pypi.python.org/pypi/multipla/
    :alt: Supported Python implementations

.. image:: https://pypip.in/egg/multipla/badge.svg
    :target: https://pypi.python.org/pypi/multipla/
    :alt: Egg Status

.. image:: https://img.shields.io/pypi/wheel/multipla.svg
    :target: https://pypi.python.org/pypi/multipla/
    :alt: Wheel Status

.. .. image:: https://img.shields.io/pypi/l/multipla.svg
..     :target: https://pypi.python.org/pypi/multipla/
..     :alt: License
.. 

(Spelled like multiplug) The purpose of this module is to provide a dead simple
plugin handler module. I wanted something:

#. Capable of handling multiple plugins (and that's pretty obvious)
#. Capable of handling multiple implementation of the same plugin
#. Capable of handling multiple ``pkg_resources.WorkingSet``-s... by itself
#. Easy to initialize in your pluggable application/framework.

I wanted somthing like:

.. code-block:: python

   content_types = multipla.power_up('scriba.content_types')

   def to_json(object):
       content_type = content_types.get('application/json')
       return content_type.format(ojbect)

   def to_user_supplied_type(object, content_type):
       return content_types.get(content_type).format(object)

or:

.. code-block:: python

   from loremipsum import generator
   import multipla

   samples = multipla.power_up('loremipsum.samples')
   vaporware = generator.Generator(samples.get('vaporware'))

You can read more on `Pythonhosted`_ or `Read the Docs`_. Since this package
has en extensive docstring documentation as well as code comments, you can
read more browsing the source code or in the python interactive shell.

.. _`Pythonhosted`: http://pythonhosted.org/multipla
.. _`Read the Docs`: http://multipla.readthedocs.org
