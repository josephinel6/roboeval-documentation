Pack Box
=================

Success
-----------
Have each arm interact with the two-flap packing box and close both flaps until the opening is fully covered.


Stages
~~~~~~~~~~~

.. glossary::
    Stage 1
        Left flap is being held by a gripper

    Stage 2
        Right flap is being held by a gripper

    Stage 3
        Right flap is closed

    Stage 4
        Left flap is closed

    Stage 5
        Complete success

Variations
------------

.. glossary::

    Static
        .. image:: /_static/env_images/pack_box.png
            :height: 200
        Box appears in the same spot with the same orientation every time. The position of the box will be slightly closer to the robot than in other variations.

    Position Randomization
        .. image:: /_static/env_images/pack_box_p.png
            :height: 200
        Position of the packing box will vary by up to 0.1m in the X-direction and up to 0.14m in the Y-direction.

    Orientation Randomization
        .. image:: /_static/env_images/pack_box_o.png
            :height: 200
        Orientation of the packing box will vary by up to 90 degrees in either direction, with respect to the Z-axis.

    Position and Orientation Randomization
        .. image:: /_static/env_images/pack_box_p_o.png
            :height: 200
        The position and orientation of the packing box will both vary by the amounts listed above.