Time To Kickdown (TTK)
======================

Description
-----------

Please refer to the :doc:`TTM<TTM>`.

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

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t, MM for maneuver 'kickdown'

Output scale
~~~~~~~~~~~~

:math:`\{-\infty\} \cup [0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that collisions can be reliably predicted

Validity
~~~~~~~~

High if used in combination with other criticality metrics, unclear if used exclusively; no sources were found on the validity of examining kickdown maneuvers for threat mitigation

Sensitivity
~~~~~~~~~~~

Medium, due to kickdown not always being an actually realizable maneuver, thus high TTK values can be measured in effectively critical scenarios

Specificity
~~~~~~~~~~~

Medium, as potentially other feasible threat mitigation maneuvers exist (e.g. braking) even for scenes where TTK :math:`\leq 0`

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
