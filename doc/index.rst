|discord|_
|test|_
|stars|_

About
=====

The `semantic versioning`_ package in the `Mys programming language`_.

Project: https://github.com/mys-lang/package-semver

Application
===========

The ``semver`` application can increment version numbers as seen
below.

.. code-block:: myscon

   ❯ mys install semver
   ...
    ✔ Building (0.28 seconds)
    ✔ Installing semver in /Users/erik/.local/bin (0 seconds)
   ❯ semver increment major 2.1.3
   3.0.0
   ❯ semver increment minor 2.1.3-rc4
   2.2.0

Example
=======

An application comparing two versions:

.. code-block:: mys

   from semver import Version
   from argparse import Parser

   def main(argv: [string]):
       parser = Parser("compare")
       parser.add_positional("version-1")
       parser.add_positional("version-2")
       args = parser.parse(argv)

       version_1 = Version(args.value_of("version-1"))
       version_2 = Version(args.value_of("version-2"))

       if version_1 > version_2:
           print(f"{version_1} is newer than {version_2}.")
       elif version_1 == version_2:
           print(f"{version_1} and {version_2} are the same.")
       else:
           print(f"{version_2} is newer than {version_1}.")

Build and run:

.. code-block:: myscon

   ❯ mys run -- 1.0.0 2.0.0
    ✔ Reading package configuration (0 seconds)
    ✔ Building (0.01 seconds)
   2.0.0 is newer than 1.0.0.

API
===

.. mysfile:: src/lib.mys

.. |discord| image:: https://img.shields.io/discord/777073391320170507?label=Discord&logo=discord&logoColor=white
.. _discord: https://discord.gg/GFDN7JvWKS

.. |test| image:: https://github.com/mys-lang/package-semver/actions/workflows/pythonpackage.yml/badge.svg
.. _test: https://github.com/mys-lang/package-semver/actions/workflows/pythonpackage.yml

.. |stars| image:: https://img.shields.io/github/stars/mys-lang/package-semver?style=social
.. _stars: https://github.com/mys-lang/package-semver

.. _semantic versioning: https://semver.org/

.. _Mys programming language: https://mys-lang.org
