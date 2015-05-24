============
formula-docs
============

.. image:: https://img.shields.io/badge/flattr-donate-red.svg
    :alt: Donate via flattr
    :target: https://flattr.com/profile/bechtoldt

.. image:: https://img.shields.io/gratipay/bechtoldt.svg
    :alt: Donate via Gratipay
    :target: https://www.gratipay.com/bechtoldt/

.. image:: https://img.shields.io/badge/license-CC--BY--SA--4.0-blue.svg
    :alt: CC-BY-SA-4.0
    :target: http://creativecommons.org/licenses/by-sa/4.0/

.. image:: https://img.shields.io/badge/gitter-chat-brightgreen.svg
    :alt: Join Chat
    :target: https://gitter.im/bechtoldt/formula-docs?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge

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

Directory listing of https://github.com/bechtoldt/saltstack-skeleton-formula:

::

    $ tree -I '.git|.vagrant|.*\.swp' --matchdirs -L 2
    .
    |-- .gitignore
    |-- .gitmodules
    |-- CHANGELOG.rst
    |-- LICENSE
    |-- README.rst
    |-- _grains/
    |-- _modules/
    |-- _states/
    |-- contrib/
    |   |-- LICENSE
    |   `-- states/
    |-- meta.yaml
    |-- pillar_examples/
    |   |-- client.sls
    |   |-- minimal.sls
    |   |-- server.sls
    |   `-- special.sls
    |-- states/
    |   |-- defaults.yaml
    |   |-- py.sls
    |   `-- yaml_jinja.sls
    `-- test/
        |-- nodes.yaml
        |-- nodes.yaml.dist
        |-- shared/
        `-- vagrant/

Explanation
'''''''''''

``CHANGELOG.rst``: Contains a brief change log about important changes that are part of new releases.

``LICENSE``: Contains license information and terms & conditions how you are allowed to use and distribute the files of the underlying directories.

``README.rst``: May contain instructions how to use the formula, compatiblity information, dependencies, TODOs, a list of contributors and links for further information. Adding a list of available states or code documentaiton tend to date out. Better spend some time making your code easy to read and add some comments for complex statements.

``_grains/``: Contains custom grain modules that are used by Salt.

``_modules/``: Contains custom execution modules that are used by Salt.

``_states/``: Contains custom state modules that are used by Salt.

``contrib/``: Contains files that are contributed by users that aren't maintained by the formulas' author(s)/ maintainer.

``pillar_examples/``: Contains pillar examples that can be used for formula testing. This directory will be read by Salt master and minions for configuration management. Do *NEVER* store *ANY* sensitive data in this directory since it's meant to become published when submitting a pull request.

``states/``: Contains the actual Salt state files. This directory will be read by Salt master and minions for configuration management.

``test/``: Contains a Vagrant-based or any other development and test environment. The Vagrant subdirectory is a Git submodule (repository) that holds a generic `Vagrant box & provision scripts <https://github.com/bechtoldt/iac-vagrant>`_. The local file ``test/nodes.yaml`` can be used to configure your Vagrant box.


Version Control & Release Management
------------------------------------

FIXME: branches


Security Considerations
-----------------------

FIXME


Contributing
------------

FIXME


Using Formulas
--------------

FIXME (TODO: git clone git@github.com:bechtoldt/saltstack-skeleton-formula.git vagrant --recursive, vcs-gather)


LICENSE
-------

This document is published under the terms of `CC-BY-SA-4.0 <http://creativecommons.org/licenses/by-sa/4.0/>`_.

todo: pillar naming
