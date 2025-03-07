:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the Sky.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Sky:

Sky
===

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`RefCounted<class_RefCounted>` **<** :ref:`Object<class_Object>`

Background that uses a :ref:`Material<class_Material>` to draw a sky.

Description
-----------

The ``Sky`` class uses a :ref:`Material<class_Material>` to draw the background and update the reflection/radiance cubemaps.

Properties
----------

+--------------------------------------------+--------------------------------------------------------+-------+
| :ref:`ProcessMode<enum_Sky_ProcessMode>`   | :ref:`process_mode<class_Sky_property_process_mode>`   | ``0`` |
+--------------------------------------------+--------------------------------------------------------+-------+
| :ref:`RadianceSize<enum_Sky_RadianceSize>` | :ref:`radiance_size<class_Sky_property_radiance_size>` | ``3`` |
+--------------------------------------------+--------------------------------------------------------+-------+
| :ref:`Material<class_Material>`            | :ref:`sky_material<class_Sky_property_sky_material>`   |       |
+--------------------------------------------+--------------------------------------------------------+-------+

Enumerations
------------

.. _enum_Sky_RadianceSize:

.. _class_Sky_constant_RADIANCE_SIZE_32:

.. _class_Sky_constant_RADIANCE_SIZE_64:

.. _class_Sky_constant_RADIANCE_SIZE_128:

.. _class_Sky_constant_RADIANCE_SIZE_256:

.. _class_Sky_constant_RADIANCE_SIZE_512:

.. _class_Sky_constant_RADIANCE_SIZE_1024:

.. _class_Sky_constant_RADIANCE_SIZE_2048:

.. _class_Sky_constant_RADIANCE_SIZE_MAX:

enum **RadianceSize**:

- **RADIANCE_SIZE_32** = **0** --- Radiance texture size is 32×32 pixels.

- **RADIANCE_SIZE_64** = **1** --- Radiance texture size is 64×64 pixels.

- **RADIANCE_SIZE_128** = **2** --- Radiance texture size is 128×128 pixels.

- **RADIANCE_SIZE_256** = **3** --- Radiance texture size is 256×256 pixels.

- **RADIANCE_SIZE_512** = **4** --- Radiance texture size is 512×512 pixels.

- **RADIANCE_SIZE_1024** = **5** --- Radiance texture size is 1024×1024 pixels.

- **RADIANCE_SIZE_2048** = **6** --- Radiance texture size is 2048×2048 pixels.

- **RADIANCE_SIZE_MAX** = **7** --- Represents the size of the :ref:`RadianceSize<enum_Sky_RadianceSize>` enum.

----

.. _enum_Sky_ProcessMode:

.. _class_Sky_constant_PROCESS_MODE_AUTOMATIC:

.. _class_Sky_constant_PROCESS_MODE_QUALITY:

.. _class_Sky_constant_PROCESS_MODE_INCREMENTAL:

.. _class_Sky_constant_PROCESS_MODE_REALTIME:

enum **ProcessMode**:

- **PROCESS_MODE_AUTOMATIC** = **0** --- Automatically selects the appropriate process mode based on your sky shader. If your shader uses ``TIME`` or ``POSITION``, this will use :ref:`PROCESS_MODE_REALTIME<class_Sky_constant_PROCESS_MODE_REALTIME>`. If your shader uses any of the ``LIGHT_*`` variables or any custom uniforms, this uses :ref:`PROCESS_MODE_INCREMENTAL<class_Sky_constant_PROCESS_MODE_INCREMENTAL>`. Otherwise, this defaults to :ref:`PROCESS_MODE_QUALITY<class_Sky_constant_PROCESS_MODE_QUALITY>`.

- **PROCESS_MODE_QUALITY** = **1** --- Uses high quality importance sampling to process the radiance map. In general, this results in much higher quality than :ref:`PROCESS_MODE_REALTIME<class_Sky_constant_PROCESS_MODE_REALTIME>` but takes much longer to generate. This should not be used if you plan on changing the sky at runtime. If you are finding that the reflection is not blurry enough and is showing sparkles or fireflies, try increasing :ref:`ProjectSettings.rendering/reflections/sky_reflections/ggx_samples<class_ProjectSettings_property_rendering/reflections/sky_reflections/ggx_samples>`.

- **PROCESS_MODE_INCREMENTAL** = **2** --- Uses the same high quality importance sampling to process the radiance map as :ref:`PROCESS_MODE_QUALITY<class_Sky_constant_PROCESS_MODE_QUALITY>`, but updates over several frames. The number of frames is determined by :ref:`ProjectSettings.rendering/reflections/sky_reflections/roughness_layers<class_ProjectSettings_property_rendering/reflections/sky_reflections/roughness_layers>`. Use this when you need highest quality radiance maps, but have a sky that updates slowly.

- **PROCESS_MODE_REALTIME** = **3** --- Uses the fast filtering algorithm to process the radiance map. In general this results in lower quality, but substantially faster run times. If you need better quality, but still need to update the sky every frame, consider turning on :ref:`ProjectSettings.rendering/reflections/sky_reflections/fast_filter_high_quality<class_ProjectSettings_property_rendering/reflections/sky_reflections/fast_filter_high_quality>`.

**Note:** The fast filtering algorithm is limited to 256x256 cubemaps, so :ref:`radiance_size<class_Sky_property_radiance_size>` must be set to :ref:`RADIANCE_SIZE_256<class_Sky_constant_RADIANCE_SIZE_256>`.

Property Descriptions
---------------------

.. _class_Sky_property_process_mode:

- :ref:`ProcessMode<enum_Sky_ProcessMode>` **process_mode**

+-----------+-------------------------+
| *Default* | ``0``                   |
+-----------+-------------------------+
| *Setter*  | set_process_mode(value) |
+-----------+-------------------------+
| *Getter*  | get_process_mode()      |
+-----------+-------------------------+

Sets the method for generating the radiance map from the sky. The radiance map is a cubemap with increasingly blurry versions of the sky corresponding to different levels of roughness. Radiance maps can be expensive to calculate. See :ref:`ProcessMode<enum_Sky_ProcessMode>` for options.

----

.. _class_Sky_property_radiance_size:

- :ref:`RadianceSize<enum_Sky_RadianceSize>` **radiance_size**

+-----------+--------------------------+
| *Default* | ``3``                    |
+-----------+--------------------------+
| *Setter*  | set_radiance_size(value) |
+-----------+--------------------------+
| *Getter*  | get_radiance_size()      |
+-----------+--------------------------+

The ``Sky``'s radiance map size. The higher the radiance map size, the more detailed the lighting from the ``Sky`` will be.

See :ref:`RadianceSize<enum_Sky_RadianceSize>` constants for values.

**Note:** Some hardware will have trouble with higher radiance sizes, especially :ref:`RADIANCE_SIZE_512<class_Sky_constant_RADIANCE_SIZE_512>` and above. Only use such high values on high-end hardware.

----

.. _class_Sky_property_sky_material:

- :ref:`Material<class_Material>` **sky_material**

+----------+---------------------+
| *Setter* | set_material(value) |
+----------+---------------------+
| *Getter* | get_material()      |
+----------+---------------------+

:ref:`Material<class_Material>` used to draw the background. Can be :ref:`PanoramaSkyMaterial<class_PanoramaSkyMaterial>`, :ref:`ProceduralSkyMaterial<class_ProceduralSkyMaterial>`, :ref:`PhysicalSkyMaterial<class_PhysicalSkyMaterial>`, or even a :ref:`ShaderMaterial<class_ShaderMaterial>` if you want to use your own custom shader.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
