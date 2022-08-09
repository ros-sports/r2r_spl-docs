.. Robot2Robot SPL documentation master file, created by
   sphinx-quickstart on Wed Jun  8 18:18:58 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Robot2Robot SPL
===============

Robot2Robot SPL, abreviated as R2R_SPL is a ROS2 package that handles Intra-Team Communication
for the RoboCup Standard Platform League.

In RoboCup Standard Platform League, communication between teammates have strict rules.
They must adhere to a specific data structure and be broadcasted on the field network via UDP on
a port designated to the team.

This package provides a ROS2 topic interface for team communication, such that teams can
simply publish to ``r2r/send`` to broadcast a message, and subscribe to ``r2r/recv`` to listen
to messages from teammates. The UDP connection and conversion to and from raw bytes are handled
in this package.

The project is hosted on `Github`_ by ROS Sports. **Issues and Pull Requests are welcome!**

.. toctree::
   :hidden:

   installation
   tutorial
   versions

.. _Github: https://github.com/ros-sports/r2r_spl
