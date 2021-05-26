Time To React (TTR)
===================

Description
-----------

The TTR metric [Hillenbrand2006]_ [Tamke2011]_ approximates the latest time until a reaction is required by aggregating the maximum TTM metric over a predefined set of maneuvers :math:`M`, i.e.

.. math::
		\mathit{TTR}(A_1,A_2,t) = \max_{m \in M} \mathit{TTM}(A_1,A_2,t,m)\,.

For example, as a set of maneuvers, one might select :math:`M = \{`'brake', 'steer', 'kickdown':math:`\}`.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

Depends on maneuver set :math:`M`

Subject type
~~~~~~~~~~~~

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t, set of maneuvers :math:`M` and their MMs

Output scale
~~~~~~~~~~~~

:math:`\{-\infty\} \cup [0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that collisions can be reliably predicted

Validity
~~~~~~~~

High, claimed to be 'an adequate metric to assess the criticality [...] since it directly relates to the driver’s possible actions' [Hillenbrand2006]_, but also dependent on maneuvers and collision prediction

Sensitivity
~~~~~~~~~~~

Comparable to TTM, as, due to selection of the maneuver with the maximal TTM, the same reasoning applies

Specificity
~~~~~~~~~~~

Highly increased compared to TTM due to consideration of multiple maneuvers

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time for :math:`|M|=1`, branching time for :math:`|M|>1`
