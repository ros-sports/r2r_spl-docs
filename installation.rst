Installation
############

.. warning::

   This package targets **ROS2 Foxy onwards**. It won't compile on all ROS1
   and older ROS2 distros.

Source Installation
*******************

Cloning repositories
====================

Source your ROS2 installation, then in your ROS2 workspace, run:

.. group-tab:: Foxy / Galactic

   .. code-block:: console

      git clone https://github.com/ros-sports/r2r_spl.git src/r2r_spl --branch=${ROS_DISTRO}

Building
========

In your ROS2 workspace, install the dependencies:

.. code-block:: console

   rosdep install --from-paths src -i

Build the package:

.. code-block:: console

   colcon build
