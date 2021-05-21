Testing
========

When submitting a pull request, our continuous integration process will
run a series of tests. There are two levels of tests that we use in
``TorXakis``: unit-tests and integration tests. Unit-tests can be run
when building using ``stack`` by passing this ``--test`` flag:

.. code:: sh

   stack install --test

To run the integration tests go to the ``test/sqatt`` folder, and run:

.. code:: sh

   stack test

See the `README <test/sqatt/README.md>`__ in the ``sqatt`` folder for
more information.

