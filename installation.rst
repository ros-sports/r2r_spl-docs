Installation
############

.. warning::

   This package targets **ROS2 Foxy onwards**. It won't compile on all ROS1 and older ROS2 distros.

To install the packages, do one of the following:

* a `Binary Installation`_
* a `Source Installation`_

Binary Installation
*******************

Binary installation is available for all active distros.

Source your ROS installation, then run:

.. code-block:: console

  sudo apt update
  sudo apt install ros-${ROS_DISTRO}-r2r-spl-7

The most recent version of the SPL Standard Message is version 7, as defined in the SPL rulebook.
If you intend on using an older SPL Standard Message format, replace ``7`` with the version you want to use.
Currently the only available version is ``7``.
In the future, packages will be added to all available distros to cover future competitions.

If this method does not work for your platform, perform the `Source Installation`_ instead.

Source Installation
*******************

Cloning repositories
====================

Source your ROS2 installation, then in your ROS2 workspace, run:

.. code-block:: sh

   git clone https://github.com/ros-sports/r2r_spl.git src/r2r_spl --branch ${ROS_DISTRO}

Building
========

In your ROS2 workspace, install the dependencies:

.. code-block:: console

   rosdep install --from-paths src -i

Build the package:

.. code-block:: console

   colcon build
