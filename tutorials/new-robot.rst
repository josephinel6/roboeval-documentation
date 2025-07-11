Adding a New Robot to RoboEval
==============================

To integrate a new robot into RoboEval, you'll need to define its configuration
and register it within the system. This guide walks through the necessary steps
using the **Franka Panda** robot as an example.

Step 1: Create a Robot Configuration File
-----------------------------------------

Navigate to:

::

    roboeval/robots/configs/

Create a new Python file (e.g., ``panda.py``) where you define the robot’s configuration.

Required Components
~~~~~~~~~~~~~~~~~~~

Each robot should include:

- **ArmConfig** – MuJoCo model path, joint and actuator definitions
- **GripperConfig** – model path, control range, and finger pad bodies
- **FloatingBaseConfig** – defines fixed or floating base behavior
- **CameraConfig** – (optional) cameras on base or wrists
- **RobotConfig** – wraps all robot components
- **RobotIKConfig** – IK settings used by CuRobo or similar planners
- **Robot subclass** – inherits from ``roboeval.robots.robot.Robot`` and returns ``config`` and ``ik_config``

Example: Define the Robot Class
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python

    class BimanualPanda(Robot):
        @property
        def config(self) -> RobotConfig:
            return PANDA_CONFIG_WITH_PANDA_GRIPPER

        @property
        def ik_config(self) -> RobotIKConfig:
            return create_bimanual_panda_config()

Example: ArmConfig Definition
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python

    PANDA_ARM = ArmConfig(
        site="attachment_site",
        model=...,
        joints=[...],
        actuators=[...],
        links=[...],
    )

Step 2: Register the Robot
--------------------------

To make the robot available for use in RoboEval experiments, register it in:

::

    tools/shared/utils.py

Add your robot class to the ``ROBOTS`` dictionary:

.. code-block:: python

    from roboeval.robots.configs.panda import BimanualPanda, SinglePanda

    ROBOTS: dict[str, Optional[Type[Robot]]] = {
        "Default": None,
        "Bimanual Panda": BimanualPanda,
        "Single Panda": SinglePanda,
        # Add your custom robots here
    }

.. note::
   The dictionary key (e.g., ``"Bimanual Panda"``) is the name used in config files or CLI commands.

Step 3: Tips and Best Practices
-------------------------------

- **Modular Configs**: Use shared variables (e.g., ``PANDA_ARM``) for reusable parts across multiple robot configs.
- **Camera Support**: Use ``CAMERA_CONFIG`` to define wrist and head cameras. Set ``manual=True`` and specify pose manually.
- **Floating Base**: Use ``FloatingBaseConfig`` if the robot has a movable base (e.g., mobile or virtual pelvis).
- **Joint Limits**: Ensure joint limits in ``RobotIKConfig`` are precise to enable proper inverse kinematics.

Final Checklist
---------------

.. list-table::
   :header-rows: 1

   * - Task
     - Done?
   * - Added ``ArmConfig``, ``GripperConfig``, ``FloatingBaseConfig``, ``RobotConfig``
     - [ ]
   * - Defined ``RobotIKConfig`` for motion planning
     - [ ]
   * - Created a subclass of ``Robot`` with ``config`` and ``ik_config`` properties
     - [ ]
   * - Registered the robot in ``tools/shared/utils.py``
     - [ ]

Once registered, your robot is fully compatible with RoboEval, and can be used for
benchmarking, evaluation, and policy testing.