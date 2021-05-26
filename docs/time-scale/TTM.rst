Time To Maneuver (TTM)
======================

Description
-----------

The TTM metric returns the latest possible time in the interval :math:`[0,\mathit{TTC}]` such that a distinguished actor :math:`A_1` performing the considered avoidance maneuver would lead to collision avoidance with all other objects in the scene [Hillenbrand2006]_ [Tamke2011]_.
If :math:`-\infty` is returned, a collision cannot be avoided.
Therefore,

.. math::
		\mathit{TTM}(A_1,A_2,t,m)  = \max \; (\{ \tilde{t} \in [0,\mathit{TTC}(A_1,A_2,t)] \,\mid\, d(p_{1,m}(t+s),p_2(t+s)) > 0  \; \forall\, s \ge \tilde{t} \} \cup \{-\infty\}).

The TTM can be extended to scenarios by aggregating over time and actors. For analytic purposes, an extension of the output scale to negative values is possible.
Various special cases of the TTM metric have been considered [Tamke2011]_ [Wagner2018]_ [Junietz2018a]_, including Time To Brake (TTB) [Mages2009]_ (i.e.\ m = 'brake'), Time To Steer (TTS) [Hillenbrand2006]_ (i.e.\ m = 'steer'), and Time To Kickdown (TTK) (i.e.\ m = 'kickdown').

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

Depends on maneuver

Subject type
~~~~~~~~~~~~

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t, MM for the considered maneuver

Output scale
~~~~~~~~~~~~

:math:`\{-\infty\} \cup [0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that collisions can be reliably predicted

Validity
~~~~~~~~

High, but depends on validity of the threat mitigation maneuver as well as the collision prediction of the DMM

Sensitivity
~~~~~~~~~~~

High, but depends on feasibility of the threat mitigation maneuver; if :math:`m` is not feasible in actually critical scenarios, sensitivity is reduced

Specificity
~~~~~~~~~~~

High, but depends on maneuver :math:`m`: if for a scene with :math:`\mathit{TTM} \leq 0` feasible threat mitigation maneuvers :math:`\neq m` exist, specificity is reduced

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
