


TorXakis
========

``TorXakis`` is a tool for Model Based Testing.

It is licensed under the `BSD3 license <LICENSE>`__.

TorXakis is written in `Haskell <https://www.haskell.org>`__ and uses
```stack`` <https://www.haskellstack.org>`__ as build tool. In addition
TorXakis needs an
`SMT <https://en.wikipedia.org/wiki/Satisfiability_modulo_theories>`__
solver, such as `cvc4 <http://cvc4.cs.stanford.edu/web/>`__ or
`Z3 <https://github.com/Z3Prover/z3>`__. The SMT Solver needs to support
`SMTLIB <http://smtlib.cs.uiowa.edu/>`__ version 2.5, `Algebraic Data
Types <https://en.wikipedia.org/wiki/Algebraic_data_type>`__ (as
proposed for version 2.6), and
`Strings <http://cvc4.cs.stanford.edu/wiki/Strings>`__. The SMT Solvers
are assumed to be located on the
`PATH <https://en.wikipedia.org/wiki/PATH_(variable)>`__. For
development acceptance tests
`javac <https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>`__
is needed.

The Haddock documentation is also available
`here <https://torxakis.github.io/TorXakis/doc/index.html>`__.



Acknowledgements
----------------

Part of the research and development of TorXakis is carried out

-  as part of the NWO-TTW project 13859: SUMBAT: Supersizing Model-Based
   Testing.
-  as part of the Enable-S3 program under the responsibility of ESI
   (TNO) with Philips as the carrying industrial partner. The Enable-S3
   research is supported by the Netherlands Ministry of Economic Affairs
   (Toeslag voor Topconsortia voor Kennis en Innovatie).

.. |TorXakis logo| image:: https://git.io/vFvfj
.. |Build Status| image:: https://semaphoreci.com/api/v1/torxakis-admin/torxakis/branches/develop/badge.svg
   :target: https://semaphoreci.com/torxakis-admin/torxakis
.. |Build status| image:: https://ci.appveyor.com/api/projects/status/ppk53o7uh7e6aie9/branch/develop?svg=true
   :target: https://ci.appveyor.com/project/torxakis-admin/torxakis/branch/develop
.. |Code Climate| image:: https://codeclimate.com/github/TorXakis/TorXakis/badges/gpa.svg
   :target: https://codeclimate.com/github/TorXakis/TorXakis
.. |License| image:: https://img.shields.io/badge/License-BSD%203--Clause-blue.svg
   :target: https://opensource.org/licenses/BSD-3-Clause
