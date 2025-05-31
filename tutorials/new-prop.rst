Creating a New Prop
======================
1. Load your XML file(s) under ``taskverse/envs/xmls``
2. Create a file Python file under ``taskverse/envs/props``
3. Necessary imports:

.. code-block:: python
    
    from pathlib import Path
    from taskverse.const import ASSETS_PATH
    from taskverse.envs.props.prop import Prop, CollidableProp, KinematicProp


4. Each prop should be a class with the following form:

.. code-block:: python

    class Prop(PropType):
        @property
        def _model_path(self) -> Path:
            return ASSETS_PATH / "your/path/here"

* Where prop type specifies which Prop class to inherit from