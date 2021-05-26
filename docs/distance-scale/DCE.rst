Distance of Closest Encounter (DCE)
===================================

Description
-----------

Please refer to the :doc:`TTCE</time-scale/TTCE>`.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Any scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, distance (m), ratio scale

Reliability
~~~~~~~~~~~

Medium, often, changes in criticality will not be reflected in a change in spatial proximity, e.g. reductions of velocity

Validity
~~~~~~~~

Medium, as the interpretation of the spatial proximity depends on other factors such as angles, velocities, and relative positioning; no empirical analysis available

Sensitivity
~~~~~~~~~~~

High, as many critical scenes exhibit a spatially close encounter

Specificity
~~~~~~~~~~~

Low, as a not all close encounters, specifically in unstructured or urban settings at low velocities, are directly critical

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
