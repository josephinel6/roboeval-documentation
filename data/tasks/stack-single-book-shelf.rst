Stack Single Book Shelf
========================

Success
-----------
Place one book onto either the upper or lower shelf board so that the book touches the shelf and is released by all grippers.


Stages
~~~~~~~~~~~

.. glossary::
    Stage 1
        Book is being held

    Stage 2
        Book is being held above the table

    Stage 3
        Book is touching a shelf

    Stage 4
        Complete success

Variations
------------

.. glossary::

    Static
        .. image:: /_static/env_images/stack_single_book_shelf.png
            :height: 200

        The book appears in the same spot with the same orientation every time.

    Position Randomization
        .. image:: /_static/env_images/stack_single_book_shelf_p.png
            :height: 200
        Position of the book will vary by up to 0.1m in the X-direction and up to 0.25m in the Y-direction.

    Position and Orientation Randomization
        .. image:: /_static/env_images/stack_single_book_shelf_p_o.png
            :height: 200
        Position will vary as specified above, and the orientation of the book will vary by up to 30 degrees in either direction about the Z-axis.