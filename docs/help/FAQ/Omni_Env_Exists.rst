.. _faq_omni_exists:

OMNI Environment Already Exists Error
=====================================

This FAQ covers what to do when running ``simp config`` outputs an
``"Unable to configure: Invalid SIMP omni-environment for 'production' exists"`` error

If installing SIMP on a system that has a pre-existing ``production`` :term:`Puppet Environment`,
you may encounter the following error when running `simp config`:

.. code-block:: bash

    Unabled to configure: Invalid SIMP omni-environment for 'production' exists:
      >> Puppet environment 'production' exists
      >> Secondary environment 'production' does not exist

or (depending on the version):

.. code-block:: bash

    Unable to configure: Invalid SIMP omni-environment for 'production' exists:
      >> Puppet environment 'production' exists
      >> Secondary environment 'production' does not exist

Resolution Options
------------------

A New Start
^^^^^^^^^^^

If you want to have a completely clean start, then just rename the production
directory ``(/var/simp/environments/production)`` to ``production.bak`` and
re-run ``simp config`` and ``simp bootstrap``.

A Different Environment
^^^^^^^^^^^^^^^^^^^^^^^

If you want to keep your existing ``production`` environment, you can use an
alternate environment during your initial configuration of the system.

To do this, see :ref:`howto-use-an-alternate-simp-config-environment`.

Remember to assign nodes to this environment using your :term:`ENC` of choice.

For a simple inbuilt solution, see :ref:`howto-simp-enc`.

Puppet Enterprise Users
-----------------------

If you are using Puppet Enterprise, we recommend you use a control repo. See the section on
:ref:`howto-setup-a-simp-control-repository`.
