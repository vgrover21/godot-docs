:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the AnimatedSprite2D.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_AnimatedSprite2D:

AnimatedSprite2D
================

**Inherits:** :ref:`Node2D<class_Node2D>` **<** :ref:`CanvasItem<class_CanvasItem>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

Sprite node that can use multiple textures for animation.

Description
-----------

Animations are created using a :ref:`SpriteFrames<class_SpriteFrames>` resource, which can be configured in the editor via the SpriteFrames panel.

**Note:** You can associate a set of normal or specular maps by creating additional :ref:`SpriteFrames<class_SpriteFrames>` resources with a ``_normal`` or ``_specular`` suffix. For example, having 3 :ref:`SpriteFrames<class_SpriteFrames>` resources ``run``, ``run_normal``, and ``run_specular`` will make it so the ``run`` animation uses normal and specular maps.

Tutorials
---------

- :doc:`2D Sprite animation <../tutorials/2d/2d_sprite_animation>`

- `2D Dodge The Creeps Demo <https://godotengine.org/asset-library/asset/515>`__

Properties
----------

+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`StringName<class_StringName>`     | :ref:`animation<class_AnimatedSprite2D_property_animation>`     | ``&"default"``    |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`bool<class_bool>`                 | :ref:`centered<class_AnimatedSprite2D_property_centered>`       | ``true``          |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`bool<class_bool>`                 | :ref:`flip_h<class_AnimatedSprite2D_property_flip_h>`           | ``false``         |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`bool<class_bool>`                 | :ref:`flip_v<class_AnimatedSprite2D_property_flip_v>`           | ``false``         |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`int<class_int>`                   | :ref:`frame<class_AnimatedSprite2D_property_frame>`             | ``0``             |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`SpriteFrames<class_SpriteFrames>` | :ref:`frames<class_AnimatedSprite2D_property_frames>`           |                   |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`Vector2<class_Vector2>`           | :ref:`offset<class_AnimatedSprite2D_property_offset>`           | ``Vector2(0, 0)`` |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`bool<class_bool>`                 | :ref:`playing<class_AnimatedSprite2D_property_playing>`         | ``false``         |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+
| :ref:`float<class_float>`               | :ref:`speed_scale<class_AnimatedSprite2D_property_speed_scale>` | ``1.0``           |
+-----------------------------------------+-----------------------------------------------------------------+-------------------+

Methods
-------

+-------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>` | :ref:`is_playing<class_AnimatedSprite2D_method_is_playing>` **(** **)** |const|                                                                   |
+-------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
| void                    | :ref:`play<class_AnimatedSprite2D_method_play>` **(** :ref:`StringName<class_StringName>` anim=&"", :ref:`bool<class_bool>` backwards=false **)** |
+-------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
| void                    | :ref:`stop<class_AnimatedSprite2D_method_stop>` **(** **)**                                                                                       |
+-------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+

Signals
-------

.. _class_AnimatedSprite2D_signal_animation_finished:

- **animation_finished** **(** **)**

Emitted when the animation is finished (when it plays the last frame). If the animation is looping, this signal is emitted every time the last frame is drawn.

----

.. _class_AnimatedSprite2D_signal_frame_changed:

- **frame_changed** **(** **)**

Emitted when :ref:`frame<class_AnimatedSprite2D_property_frame>` changed.

Property Descriptions
---------------------

.. _class_AnimatedSprite2D_property_animation:

- :ref:`StringName<class_StringName>` **animation**

+-----------+----------------------+
| *Default* | ``&"default"``       |
+-----------+----------------------+
| *Setter*  | set_animation(value) |
+-----------+----------------------+
| *Getter*  | get_animation()      |
+-----------+----------------------+

The current animation from the ``frames`` resource. If this value changes, the ``frame`` counter is reset.

----

.. _class_AnimatedSprite2D_property_centered:

- :ref:`bool<class_bool>` **centered**

+-----------+---------------------+
| *Default* | ``true``            |
+-----------+---------------------+
| *Setter*  | set_centered(value) |
+-----------+---------------------+
| *Getter*  | is_centered()       |
+-----------+---------------------+

If ``true``, texture will be centered.

----

.. _class_AnimatedSprite2D_property_flip_h:

- :ref:`bool<class_bool>` **flip_h**

+-----------+-------------------+
| *Default* | ``false``         |
+-----------+-------------------+
| *Setter*  | set_flip_h(value) |
+-----------+-------------------+
| *Getter*  | is_flipped_h()    |
+-----------+-------------------+

If ``true``, texture is flipped horizontally.

----

.. _class_AnimatedSprite2D_property_flip_v:

- :ref:`bool<class_bool>` **flip_v**

+-----------+-------------------+
| *Default* | ``false``         |
+-----------+-------------------+
| *Setter*  | set_flip_v(value) |
+-----------+-------------------+
| *Getter*  | is_flipped_v()    |
+-----------+-------------------+

If ``true``, texture is flipped vertically.

----

.. _class_AnimatedSprite2D_property_frame:

- :ref:`int<class_int>` **frame**

+-----------+------------------+
| *Default* | ``0``            |
+-----------+------------------+
| *Setter*  | set_frame(value) |
+-----------+------------------+
| *Getter*  | get_frame()      |
+-----------+------------------+

The displayed animation frame's index.

----

.. _class_AnimatedSprite2D_property_frames:

- :ref:`SpriteFrames<class_SpriteFrames>` **frames**

+----------+--------------------------+
| *Setter* | set_sprite_frames(value) |
+----------+--------------------------+
| *Getter* | get_sprite_frames()      |
+----------+--------------------------+

The :ref:`SpriteFrames<class_SpriteFrames>` resource containing the animation(s).

----

.. _class_AnimatedSprite2D_property_offset:

- :ref:`Vector2<class_Vector2>` **offset**

+-----------+-------------------+
| *Default* | ``Vector2(0, 0)`` |
+-----------+-------------------+
| *Setter*  | set_offset(value) |
+-----------+-------------------+
| *Getter*  | get_offset()      |
+-----------+-------------------+

The texture's drawing offset.

----

.. _class_AnimatedSprite2D_property_playing:

- :ref:`bool<class_bool>` **playing**

+-----------+-----------+
| *Default* | ``false`` |
+-----------+-----------+

If ``true``, the :ref:`animation<class_AnimatedSprite2D_property_animation>` is currently playing.

----

.. _class_AnimatedSprite2D_property_speed_scale:

- :ref:`float<class_float>` **speed_scale**

+-----------+------------------------+
| *Default* | ``1.0``                |
+-----------+------------------------+
| *Setter*  | set_speed_scale(value) |
+-----------+------------------------+
| *Getter*  | get_speed_scale()      |
+-----------+------------------------+

The animation speed is multiplied by this value.

Method Descriptions
-------------------

.. _class_AnimatedSprite2D_method_is_playing:

- :ref:`bool<class_bool>` **is_playing** **(** **)** |const|

Returns ``true`` if an animation is currently being played.

----

.. _class_AnimatedSprite2D_method_play:

- void **play** **(** :ref:`StringName<class_StringName>` anim=&"", :ref:`bool<class_bool>` backwards=false **)**

Plays the animation named ``anim``. If no ``anim`` is provided, the current animation is played. If ``backwards`` is ``true``, the animation will be played in reverse.

----

.. _class_AnimatedSprite2D_method_stop:

- void **stop** **(** **)**

Stops the current animation (does not reset the frame counter).

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
