Tutorial
########

To run the node,

.. code-block:: console

   ros2 run r2r_spl_7 r2r_spl

To send a message to a teammate, publish a message on ``r2r/send``:

.. code-block:: console

   ros2 topic pub r2r/send splsm_7/msg/SPLSM

To listen to messages coming from teammates, subscribe on ``r2r/recv``:

.. code-block:: console

   ros2 topic echo r2r/recv
