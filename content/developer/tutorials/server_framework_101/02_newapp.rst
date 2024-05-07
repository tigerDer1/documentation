.. todo: merge with chap 3?
.. todo: update title?

==============================
Chapter 2: Lay the foundations
==============================

.. todo introduction text

Install the app
===============

If you followed the :doc:`generic tutorial setup guide <../setup_guide>` carefully, you should now
have a running Odoo server with the `odoo/tutorials` repository in the `addons-path`, and be logged
in as an administrator.

**Let's install our real estate app!** On your browser, open Odoo and navigate to
:menuselection:`Apps`. Search for :guilabel:`Real Estate` and click :guilabel:`Activate`.

Nothing has changed? That's normal; the `real_estate` module we just installed is currently an empty
shell. It only contains two files:

- An empty :file:`__init__.py` file to make Python treat the :file:`real_estate` directory as a
  package.
- The :file:`__manifest__.py` file that declares the :file:`real_estate` Python package as an Odoo
  module.

Those two files are the minimum requirements for a directory to be considered as an Odoo module.

.. exercise::
   Search for each key of our :file:`__manifest__.py` file in the :ref:`reference documentation
   <reference/module/manifest>` and understand the base metadata that defines our module.

.. seealso::
   `The manifest of the Sales app <{GITHUB_PATH}/addons/sale/__manifest__.py>`_

----

All good? If yes, then let's :doc:`create our first model <03_basicmodel>`!
