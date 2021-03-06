=========
Elm Magic
=========

Compile and render Elm code in IPython and Jupyter notebooks

.. image:: https://raw.github.com/ali--/elm_magic/master/docs/screenshot1.png

a notebook with pure elm : https://gist.github.com/anonymous/68d36f1b6026893bc08b22b053e2f42e

a notebook with elm and python : https://gist.github.com/anonymous/60261d86af6ab9b4a0a398f39cf40cc1

.. image:: https://img.shields.io/pypi/v/elm_magic.svg
        :target: https://pypi.python.org/pypi/elm_magic

.. image:: https://img.shields.io/travis/ali--/elm_magic.svg
        :target: https://travis-ci.org/ali--/elm_magic

.. image:: https://readthedocs.org/projects/elm-magic/badge/?version=latest
        :target: https://elm-magic.readthedocs.io/en/latest/?badge=latest
        :alt: Documentation Status

.. image:: https://pyup.io/repos/github/ali--/elm_magic/shield.svg
     :target: https://pyup.io/repos/github/ali--/elm_magic/
     :alt: Updates

Elm Magic provides IPython magic commands that execute elm-lang code

Usage
-----

.. code-block:: python

    In [1]: %load_ext elm_magic

    In [2]: %%elm
       ...: import Html exposing (text)
       ...: main =
       ...:   text "Hello World"
    Out[2]:
       ...: Hello World

    In [3]: %%elm -i elm-lang/http elm-lang/mouse -w /tmp/myelmdir
       ...: <elm source code>
    
This magic will::

  (1) use /tmp/myelmdir for workdir (uses new temporary dir by default)
  (2) install elm-lang/http and elm-lang/mouse with elm-package install
  (3) compile the cell input with elm-make 
  (4) display the cell output as html

The -r flag renders the cell contents with elm-static-html
The cell must look exactly like this: 

.. code-block:: python

    In [4]: %%elm -r
       ...: module Main exposing (..)
       ...: import Html exposing (text)
       ...: view = 
       ...:   text "Hello World"
    Out[4]:
       ...: Hello World


Installation
------------

Install using pip::

    pip install --upgrade elm_magic
..


If elm and nodejs are not installed, you can try::

    elm_magic install --target <install-dir>

where <install-dir> is writable by the current user.
and in the user's PATH (e.g /usr/local/ or /opt/conda)

Load the magic extension in IPython or Jupyter::
 
        %load_ext elm_magic

then start using the %%elm magic::
     
        %%elm 
          ... elm-lang code ...


Configuration
-------------

see or set configuration parameters::

        %config ElmMagic

Features
--------

* provides %%elm magic that executes elm-lang and displayes the result
* can be used with any jupyter kernel
* directory used by elm-make is configurable
* provides cli for installing nodejs and elm

Credits
---------

This package was created with Cookiecutter_ and the `audreyr/cookiecutter-pypackage`_ project template.
Started with the help of https://github.com/abingham/jupyter-elm-kernel

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage

* Free software: GNU General Public License v3
* Documentation: https://elm-magic.readthedocs.io.


