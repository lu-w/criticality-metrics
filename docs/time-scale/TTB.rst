Time To Brake (TTB)
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

0.4 s [Tamke2011]_ (selection of a minimal risk maneuver), 1 s [Junietz2018a]_ [Huber2020]_ (threshold for critical)

Subject type
~~~~~~~~~~~~

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t, MM for maneuver 'brake'

Output scale
~~~~~~~~~~~~

:math:`\{-\infty\} \cup [0, \infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that collisions can be reliably predicted

Validity
~~~~~~~~

High for two-actor scenes, medium for more actors when TTB is evaluated under a fixed perspective, but can be increased by aggregating over all actors as at least for one of them, the TTB will be valid

Sensitivity
~~~~~~~~~~~

High, but depends on the DMM: if no collisions are predicted for critical scenarios, sensitivity is reduced

Specificity
~~~~~~~~~~~

High for humans, as braking is a key choice in human reaction [Adams1994]_; medium for AVs as non-braking maneuvers can often avoid a critical situation, even if TTB :math:`\leq0` [Adams1994]_

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
