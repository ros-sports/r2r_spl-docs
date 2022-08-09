Versions
########

The RoboCup competition is hosted annually, with the competition usually around July.
Additionally, there are regional RoboCup competitions such as the German Open, Asia Pacific, and Japan Open.
The structure of the packets used to communicate between robots are restricted in SPL and frequently change with rule changes accompanied by a version number increment.

SPL Standard Message (SPLSM)
****************************

The structure of SPL Standard Message is defined in `GameController`_, and has an associated version number.
Every time there is a rule change for the message, the version number is incremented and a new package named ``r2r_spl_<VERSION_NUMBER>`` (eg. ``r2r_spl_7``) will be released for all active ROS2 distros.

Supported Distros
*****************

Packages will be released for all active ROS distributions at the time of competition.
The table below lists the current availability of packages under different ROS distros and competitions.

.. list-table:: Package availability
   :widths: 25 25 25 25 25
   :header-rows: 1
   :stub-columns: 1

   * -
     - Foxy
     - Galactic
     - Humble
     - Rolling
   * - r2r_spl_7
     - Yes
     - Yes
     - Yes
     - Yes
   * - r2r_spl_master
     - No
     - No
     - No
     - No

.. _GameController: https://github.com/RoboCup-SPL/GameController
