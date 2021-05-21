Repository structure
=====================

There are several folders in this repository, which serve different
purposes:

-  ```bin`` <bin/>`__: utility scripts to start ``TorXakis`` UI and
   server.
-  ```ci`` <ci/>`__: scripts used in our continuous integration process.
-  ```ci/mk-package`` <ci/mk-package>`__: files needed to create Linux
   packages.
-  ```docs`` <docs/>`__: documentation files for ``TorXakis``.
-  ```examps`` <examps/>`__: example models and systems-under-test
   (SUT's) to play around with. This folder also contains some binary
   (.jpg and .pptx) files, which are used for documentation. Such files
   are tracked with `Git-LFS <https://git-lfs.github.com/>`__\ (*).
-  ```sys`` <sys/>`__: packages that make up ``TorXakis`` this is where
   the source code resides.
-  ```test`` <test/>`__: utilities for quality assurance tests
   (integration-tests, license-checking, etc).

See the README files in each folders to get a more detailed explanation.

(*): Git-LFS is installed by default along with official git client, so
you should be able to access these files without extra effort. If, for
some reason, you don't have Git-LFS, then you can `install the official
Git-LFS extension <https://git-lfs.github.com/>`__.

