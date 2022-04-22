Packaging
=========

Approach
~~~~~~~~~

``TorXakis`` depends on ``cvc4`` or ``z3`` tools. If such a depending tool gets upgraded it can break ``TorXakis``.
We therefore bundle these depending tools in the ``TorXakis`` package so that it always works. When installed only
``TorXakis`` can run these specific versions of the tools.  The system can have a different versions of these tools
installed, which however are not used by ``TorXakis`` which uses its own versions.

When using separate install of these dependency tools, we could more easily update them in case of security leaks, but
at the cost of possible breaking ``TorXakis``. However we prefer to have  ``TorXakis`` with fixed dependencies versions which will not break, because that is more
important for us then  the security risk.


Windows
~~~~~~~

Macos
~~~~~

homebrew package includes  ``cvc4`` or ``z3`` tools
torxakis is wrapper script which

Linux
~~~~~



Packaging: building binary packages for easy installation
=========================================================

Introduction
~~~~~~~~~~~~

In this chapter we describe how we build packages for ``TorXakis`` for the different operating systems it supports.


Linux
~~~~~


MacOs
~~~~~

For ``MacOS`` we use the homebrew packaging tool to install and distribute the ``TorXakis`` package.


The different brew packages and the urls where they install there bottles:

* torxakis:
**  browse: https://github.com/TorXakis/TorXakis/releases/tag/v0.9.0/ 
**  root_url:  https://github.com/TorXakis/TorXakis/releases/download/v0.9.0/ 
**  example bottle: https://github.com/TorXakis/TorXakis/releases/download/v0.9.0/torxakis-0.9.0.arm64_monterey.bottle.tar.gz
* z3: 
**  browse: https://github.com/TorXakis/Dependencies/releases/tag/z3-4.8.7/
**  root_url: https://github.com/TorXakis/Dependencies/releases/download/z3-4.8.7/
**  example bottle: https://github.com/TorXakis/Dependencies/releases/download/z3-4.8.7/z3@4.8.7-4.8.7.arm64_monterey.bottle.tar.gz
* cvc4: https://github.com/TorXakis/Dependencies/releases/tag/cvc4_1.7/ 
**  browse: https://github.com/TorXakis/Dependencies/releases/tag/cvc4_1.7/
**  root_url:  https://github.com/TorXakis/Dependencies/releases/download/cvc4_1.7/
**  example bottle:  https://github.com/TorXakis/Dependencies/releases/download/cvc4_1.7/cvc4@1.7-1.7.arm64_monterey.bottle.tar.gz


  brew install --build-bottle   torxakis/torxakis/cvc4\&1.7 
  brew bottle   harcokuppens/torxakis/cvc4\&1.7  
  
It generates a bottle file ``cvc4@1.7--1.7.arm64_monterey.bottle.1.tar.gz``. Rename the file to ``cvc4@1.7-1.7.arm64_monterey.bottle.tar.gz``  by removing the 
rebuild number '.1.' and the double '--', and the upload this file to the  `cvc4_1.7` release section of the ``Dependencies`` github project at ``https://github.com/TorXakis/Dependencies/``. 
Homebrew will use the ``root_url`` of ``https://github.com/TorXakis/Dependencies/cvc4_1.7/` in the ``cvc4@1.7.rb`` Formula to find a bottle file for you MacOS version. If it cannot find one for your
version of MacOS it will take the bottle of an older MacOS version closest to your current version. 

