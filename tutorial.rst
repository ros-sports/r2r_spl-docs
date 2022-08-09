Tutorial
########

In this tutorial, you'll learn to make two robots on the same network communicate with each other.
Different `ROS_DOMAIN_ID <https://docs.ros.org/en/rolling/Concepts/About-Domain-ID.html>`__ will be used to isolate communication between ROS nodes running on the two robots on the same network.

.. note::

   This tutorial does not require two robots, you can run it on your PC.

Sending from Robot 1
********************

First, we'll look at sending a message from the first robot to other robots on the network.

Open a new terminal window. This window will imitate robot 1.

Start the r2r_spl node, specifying the team number (0) and player number (1) of robot 1.
Select the tab from below corresponding to the SPL Standard Message version you are using:

.. tabs::

   .. group-tab:: 7

      .. code-block:: sh

         # Set ROS_DOMAIN_ID to 1
         export ROS_DOMAIN_ID=1

         # Run the node
         ros2 run r2r_spl_7 r2r_spl --ros-args -p team_num:=0 -p player_num:=1

   .. group-tab:: master

      .. code-block:: sh

         # Set ROS_DOMAIN_ID to 1
         export ROS_DOMAIN_ID=1

         # Run the node
         ros2 run r2r_spl_master r2r_spl --ros-args -p team_num:=0 -p player_num:=1

Open a new tab and publish an example SPLSM message on the ``r2r/send`` topic, using the command below:

.. tabs::

   .. group-tab:: 7

      .. code-block:: sh

         # Set ROS_DOMAIN_ID to 1
         export ROS_DOMAIN_ID=1

         # Publish the message
         ros2 topic pub r2r/send splsm_7/msg/SPLSM "
         player_num: 1
         team_num: 0
         fallen: 0
         pose:
         - 1000.0
         - 2000.0
         - 1.5
         ball_age: 10.0
         ball:
         - 200.0
         - 0.0
         data:
         - 0
         - 100
         - 255
         "

   .. group-tab:: master

      .. code-block:: sh

         # Set ROS_DOMAIN_ID to 1
         export ROS_DOMAIN_ID=1

         # Publish the message
         ros2 topic pub r2r/send splsm_master/msg/SPLSM "
         player_num: 1
         team_num: 0
         fallen: 0
         pose:
         - 1000.0
         - 2000.0
         - 1.5
         ball_age: 10.0
         ball:
         - 200.0
         - 0.0
         data:
         - 0
         - 100
         - 255
         "

Receiving on Robot 2
********************

Open a second terminal window. This window will imitate the robot 2.

Start the r2r_spl node, specifying the team number (0) and player number (2) of robot 2.

.. tabs::

   .. group-tab:: 7

      .. code-block:: sh

         # Set ROS_DOMAIN_ID to 2
         export ROS_DOMAIN_ID=2

         # Run the node
         ros2 run r2r_spl_7 r2r_spl --ros-args -p team_num:=0 -p player_num:=2

   .. group-tab:: master

      .. code-block:: sh

         # Set ROS_DOMAIN_ID to 2
         export ROS_DOMAIN_ID=2

         # Run the node
         ros2 run r2r_spl_master r2r_spl --ros-args -p team_num:=0 -p player_num:=2

Open a new tab, and echo messages on the ``r2r/recv`` topic, using the command below:

.. code-block:: sh

   # Set ROS_DOMAIN_ID to 2
   export ROS_DOMAIN_ID=2

   # Echo the messages
   ros2 topic echo r2r/recv

In the second terminal, you should see a message being received at 1Hz from the first robot.

This indicates that the first robot is sending messages to the other robot, not using ROS topics, but over UDP packets as specified in the SPL rules!
