Rotate Valve
=================

Success
-----------
Rotate each valve handle by at least 90◦ (joint value ≥ 0.10) about its axis. The robot may still touch the handle once the target angle is achieved.


Stages
~~~~~~~~~~~

.. glossary::
    Stage 1
        Left valve is being held by a gripper

    Stage 2
        Left valve is rotated by ???

    Stage 3
        Right valve is being held by a gripper

    Stage 4
        Right valve is rotated by ???

    Stage 5
        Complete success

Variations
------------

.. glossary::

    Static
        .. image:: /_static/env_images/rotate_valve.png
            :height: 200
        Valves appear in the same spot with the same orientation every time.

    Position Randomization
        .. image:: /_static/env_images/rotate_valve_p.png
            :height: 200
        Position of each valve will vary by up to 0.35m in the X-direction and up to 0.6cm in the Y-direction.

    Position and Orientation Randomization
        .. image:: /_static/env_images/rotate_valve_p_o.png
            :height: 200
        Position of each valve will vary as specified above, and orientation of each valve will vary by up to 30 degrees in either direction about the Z-axis.

    Obstacle
        .. image:: /_static/env_images/rotate_valve_obstacle.png
            :height: 200
        Position and orientation of each valve will vary as specified above, and an obstacle will be randomly generated beteween the edge of the table and the valves.