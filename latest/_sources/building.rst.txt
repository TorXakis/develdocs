Building
========

Make sure that
```stack`` <https://docs.haskellstack.org/en/stable/install_and_upgrade/>`__
is installed, then clone this repository. ``TorXakis`` requires a
``stack`` version ``1.6.1`` or greater. To build and install
``TorXakis`` locally, if you are on a Windows system run:

.. code:: sh

   stack setup
   stack install

On Linux, the following libraries should be installed:

-  libgmp-dev

For Unix systems a different stack configuration is used:

.. code:: sh

   stack setup --stack-yaml stack_linux.yaml
   stack install --stack-yaml stack_linux.yaml

The reason for having two configuration files is that on Windows systems
the libraries are linked statically, and thus we cannot use the
``integer-gmp`` library, since ``TorXakis`` is licensed under the `BSD3
license <LICENSE>`__.

In the instructions that follow we will omit the
``--stack-yaml stack-linux.yaml`` flag, but bear in mind that if you're
in an Unix system you need to add it (or set the ``STACK_YAML``
environment variable to "stack-linux.yaml")

If you experience problems when building from source, sometimes this
could be due to Makefiles which do not handle parallel builds well. If
problems appear while building, try setting the ``MAKEFLAGS`` variable
to ``" -j1 "`` before running the build commands. For instance on Unix
systems this can be achieved by running:

.. code:: sh

   export MAKEFLAGS=" -j1 "
   stack setup
   stack install

Note that the ``MAKEFLAGS`` variable does not affect the parallelism
within ``stack`` itself.

Compiler warnings are treated as errors
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

By default, several compiler warnings are treated as errors. While
developing we'd like to avoid this: removing warnings requires some
extra time. Some parts of the code might not make it when submitting a
pull request. Therefore, before a new feature or fix is ready, it
doesn't make sense to try to remove warnings on code that will be
deleted in the end. So to have the build system avoid treating warnings
as errors use the flag ``develop`` as follows:

.. code:: sh

   stack <STACK ARGS> --flag '*:develop'

For instance:

.. code:: sh

   stack test --stack-yaml stack_linux.yaml --file-watch txs-compiler  --ta "-m wrong" --flag '*:develop'

Note that currently only the package ``txs-compiler`` supports this
flag. If you find yourself needing this flag for other packages feel
free to submit an issue or pull request.
