Creating a New Task
====================

1. Create a Python file under ``taskverse/envs`` that will hold your task and all variations of it
2. Some basic imports:

.. code-block:: python

    from abc import ABC

    from bigym.bigym_env import BiGymEnv
    from bigym.const import PRESETS_PATH

    # Any prop imports you have

3. Your base environment class will always have to inherit from BiGymEnv and ABC, ex. ``class MyEnv(BiGymEnv, ABC):``
4. The methods that are most commonly needed to be overridden are:

   * ``_initialize_env(self)``: Set up the environment. Props can be spawned as shown in the example below, or they can be created from the preset file (see point 5).
   
   .. code-block:: python
        # Create multiple props
        self.cubes = [Cube(self._mojo) for _ in range(self._CUBE_COUNT)]

        # Create a single item
        self.kitchenpot = KitchenPot(self._mojo)


   * ``_on_reset(self)``
   * ``_success(self)``
   * ``_fail(self)``

5. (Optional) You can create a preset file if desired. This should be a YAML file under ``taskverse/envs/presets`` and can include information about the environment or robot setup. An example is:

.. code-block:: yaml

    props:
    - type: BaseCabinet
        position: [1.1, 0.3, 0]
        euler: [0, 0, -90]
    - type: BaseCabinet
        position: [1.1, -0.3, 0]
        euler: [0, 0, -90]
    robot:
    - name: Bimanual Panda
        position: [0.1, 0, 0]
    - name: h1
        position: [0, 0, 0]

If you wish to use a preset, your class should include the line:
   
.. code-block:: python

    _PRESET_PATH = PRESETS_PATH / "your_preset.yaml"

To assign props declared in the preset to a variable,

.. code-block:: python


    self.cabinet_2 = self._preset.get_props(BaseCabinet)[1]