.. dscheck documentation master file, created by
   sphinx-quickstart on Tue Sep 16 23:07:06 2025.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

dscheck documentation
=====================

**dscheck** is a utility to add, remove, view and process recorded commands of other utility programs in Research Data Archive Management System (RDAMS). For delayed execution or submitted batch process of the utility programs **dsarch**, **dsupdt**, and **dsrqst**, the command information and the directories where the commands are initiated are saved into RDADB as check records. For any other specialist-defined commands, they can be also put in delayed mode if the commands are added to **dscheck** control via Action -AC (-AddCheck).

.. note::

   This documentation is for version 1.0 of **dscheck**.

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   introduction/introduction
   usage/usage
   actions/action-options
   modes/mode-options
   information/information-options
