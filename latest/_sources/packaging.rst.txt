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



