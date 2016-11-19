Getting Started
===============

The following setup steps have been tested on Ubuntu 16.04.

Prerequisites
+++++++++++++

#. Install various packages that are required for the development of this project:

   ::

     sudo apt install git-buildpackage python3-setuptools python3-setuptools-scm python3-sphinx python3-argcomplete python3-pytest pep8 python3-pip python3-gnupg python3-yaml ansible lxd debootstrap debhelper

#. Initialize lxd:

   ::

     sudo lxd init

   The default settings are ok.
   Use the storage backend "dir" if there is no zfs setup on your computer.

Working with the edi Source Code
++++++++++++++++++++++++++++++++

#. Clone the source code:

   ::

     git clone https://gitlab.com/lueschem/edi.git

#. Change into the edi subfolder:

   ::

     cd edi

#. Build the edi Debian package (just to verify that everything works):

   ::

     debuild -us -uc

#. Make the development setup convenient by adding some environment variables:

   ::

     source local_setup

#. Change into the examples directory:

   ::

     cd examples/advanced/

#. Build your first lxd container using edi:

   ::

     sudo edi -v lxc launch my-first-edi-container advanced_test.yml