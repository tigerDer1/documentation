================================
Chapter 1: Architecture overview
================================

Before we start building our app, let's take a high level glance at the architecture of Odoo.

Multitier application
=====================

Odoo leverages a `multitier architecture <https://en.wikipedia.org/wiki/Multitier_architecture>`_,
meaning that the presentation, the business logic, and the data storage are separated. More
specifically, it uses a three-tier architecture (image from Wikipedia):

.. image:: 01_architecture_overview/three-tier-architecture.svg
    :align: center
    :alt: Overview of a three-tier application

The presentation tier of Odoo is a combination of HTML5, JavaScript, and CSS. The logic tier is
exclusively written in Python, while the data tier only supports PostgreSQL as an :abbr:`RDBMS
(Relational Database Management System Software)`.

Depending on the scope of your module, Odoo development can be done in any of these tiers.
Therefore, before going any further, it may be a good idea to refresh your memory if you don't have
an intermediate level in these topics. In order to go through this tutorial, you will need a very
basic knowledge of HTML and an intermediate level of Python. There are plenty of tutorials freely
accessible, so we cannot recommend one over another since it depends on your background. For
reference this is the official `Python tutorial <https://docs.python.org/3/tutorial/>`_.

Odoo modules
============

Odoo relies on modular components called **modules** to extend its functionality. These modules are
essentially self-contained packages of code and data that serve a specific purpose within the
system. You can think of them as building blocks.

Modules offer two main ways to customize Odoo:

- Adding new functionality: You can create entirely new features with modules, such as a real-time
  bus fleet visualization module.
- Extending existing functionality: Modules can also be used to modify or enhance existing Odoo
  features, like adding your country's accounting rules to the generic accounting support.

Terminology:

- Developers group their business features in Odoo *modules*.
- The main user-facing modules are flagged and exposed as *Apps*, but a majority of the modules are
  not Apps.
- *Modules* may also be referred to as *addons*.

----

Ready to start? Let's now :doc:`start building our first Odoo app <02_newapp>`!
