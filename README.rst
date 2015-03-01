============
formula-docs
============

.. image:: http://img.shields.io/github/tag/bechtoldt/formula-docs.svg
    :target: https://github.com/bechtoldt/formula-docs/tags

.. image:: https://api.flattr.com/button/flattr-badge-large.png
    :target: https://flattr.com/submit/auto?user_id=bechtoldt&url=https%3A%2F%2Fgithub.com%2Fbechtoldt%2Fformula-docs

Documentation and Standardisation of SaltStack formulas

.. contents::
    :backlinks: none
    :local:


Baseline
--------

There are -more or less- official `conventions <http://docs.saltstack.com/en/latest/topics/development/conventions/formulas.html>`_ and
`best practices <http://docs.saltstack.com/en/latest/topics/best_practices.html>`_ described in the SaltStack documentation. However in my
humble opinion (IMHO) some of those suggestions and conventions are, based on my long-time experiences with Salt, not suitable for practical use.

This document describes my formula standardisation that have proven to be useful for me. Everyone is invited to discuss about it.

Most of the formulas at https://github.com/search?q=user%3Abechtoldt+-formula are created based on the guidelines of this document.


Files & Directories
-------------------

Example
'''''''

Directory listing of https://github.com/bechtoldt/saltstack-template-formula:

::

    $ tree -I '.git|.vagrant|.*\.swp|\.env' --matchdirs
    .
    |-- .gitignore
    |-- AUTHORS
    |-- LICENSE
    |-- README.rst
    |-- _grains/
    |-- _modules/
    |-- contrib/
    |   |-- LICENSE
    |   `-- states/
    |       `-- files/
    |           `-- template.conf
    |-- pillar/
    |   |-- init.sls
    |   `-- minimal.sls
    |-- states/
    |   |-- defaults.yaml
    |   |-- py.sls
    |   `-- yaml_jinja.sls
    |-- update-docs*
    `-- vagrant/
        |-- .env.dist
        |-- Vagrantfile
        `-- setenv.sh

Explanation
'''''''''''

Files:

``AUTHORS``: Contains an auto-generated list of contributors

``LICENSE``: Contains license information and terms & conditions how you are allowed to use and distribute the files of the underlying directories.

``update-docs``: A shell script that auto-generates formula metadata files and more

Directories:

``_grains``: Contains custom grain modules that are used by Salt minions

``_modules``: Contains custom execution modules that are used by Salt minions

``contrib``: Contains files that are contributed by users that aren't maintained by the formulas' author.

``pillar``: Contains pillar example files that could be used for formula testing, too. This directory will be read by Salt master and minions for configuration management.

``states``: Contains the actual Salt state files. This directory will be read by Salt master and minions for configuration management.

``vagrant``: Contains an example Vagrant environment


Version Control & Release Management
------------------------------------

FIXME


Security Considerations
-----------------------

FIXME


Contributing
------------

FIXME


Using Formulas
--------------

FIXME
