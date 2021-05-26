Time To Zebra (TTZ)
===================

Description
-----------

Defined by Várhelyi et al., TTZ measures the time until an actor :math:`A_1` reaches a zebra crossing :math:`\mathit{CA}` [Varhelyi1998], hence

.. math::
		\mathit{TTZ}(A_1,\mathit{CA},t)  = \min \; (\{ \tilde{t} \ge 0 \,\mid\, d(p_1(t+\tilde{t}), p_{\mathit{CA}}(t+\tilde{t})) = 0 \} \cup\ \{ \infty \}).

Note that this concept can be further generalized to a Time To Object (TTO) metric for arbitrary moving or non-moving objects and conflict areas.
For moving objects, this generalization coincides with the TTC.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

:math:`[2,4]` s [Varhelyi1998]_ (critical interval at time of arrival of VRU)

Subject type
~~~~~~~~~~~~

One road vehicle

Scenario type
~~~~~~~~~~~~~

Any scenario where a road vehicle is approaching a pedestrian crossing

Inputs
~~~~~~

State of the approaching road vehicle, position of pedestrian crossing

Output scale
~~~~~~~~~~~~

:math:`[0,\infty]``, time (s), ratio scale

Reliability
~~~~~~~~~~~

Low, as changes in criticality are likely not reflected in TTZ, e.g. changes in walking directions of pedestrians

Validity
~~~~~~~~

Low, as only the pedestrian crossing is regarded to be safety-relevant, and impact of other road users is not considered; no empirical analysis available

Sensitivity
~~~~~~~~~~~

Low, as VRUs can potentially cross in front of a pedestrian crossing, leading to critical scenarios with high TTZ values

Specificity
~~~~~~~~~~~

Low, if no VRU is present and the vehicle is close to the crossing, the scenario is uncritical, but TTZ approaches 0

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
linear time
