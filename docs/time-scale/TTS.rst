Time To Steer (TTS)
===================

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

0.47 s [Junietz2018a]_ (threshold for critical), 1 s [Huber2020]_ (ADF testing)

Subject type
~~~~~~~~~~~~

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t, MM for maneuver 'steer'

Output scale
~~~~~~~~~~~~

:math:`\{-\infty\} \cup [0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that collisions can be reliably predicted

Validity
~~~~~~~~

High for two-actor scenes, medium for more actors when TTS is evaluated under a fixed perspective, but can be increased by aggregating over all actors as at least for one of them, the TTS will be valid

Sensitivity
~~~~~~~~~~~

High for non-humans, as steering is often optimal for threat mitigation than braking [Adams1994]_; medium for humans as steering maneuvers are seldomly preferred [Adams1994]_

Specificity
~~~~~~~~~~~

High under the assumption that the DMM has a low ratio of spurious collision among all predicted collision

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
linear time
