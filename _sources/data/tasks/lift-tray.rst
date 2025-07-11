Lift Tray
=================

Success
-----------
Grasp the breakfast tray with the two grippers and lift it clear of the source table without the tray touching either the table or the floor.


Stages
~~~~~~~~~~~

.. glossary::
    Stage 1
        Left gripper is grasping the tray

    Stage 2
        Right gripper is grasping the tray

    Stage 3
        Complete success

Variations
------------

.. glossary::

    Static
        .. image:: /_static/env_images/lift_tray.png
            :height: 200
        Tray appears in the same spot with the same orientation every time.

    Position Randomization
        .. image:: /_static/env_images/lift_tray_p.png
            :height: 200
        Position of the tray will vary by up to 0.1cm in the X-direction and up to 0.25m in the Y-direction.

    Orientation Randomization
        .. image:: /_static/env_images/lift_tray_o.png
            :height: 200
        Orientation of the tray will vary by up to 30 degrees in either direction about the Z-axis.

    Position and Orientation Randomization
        .. image:: /_static/env_images/lift_tray_p_o.png
            :height: 200
        Position and orientation will both vary as specified above.

    Drag Over and Lift Tray
        Tray appears on the adjacent table, with static position and orientation, and must be dragged over to the primary table and raised.