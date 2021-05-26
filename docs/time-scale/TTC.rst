Time To Collision (TTC)
=======================

Description
-----------

For two actors :math:`A_1`, :math:`A_2` at time :math:`t`, the TTC metric returns the minimal time until :math:`A_1` and :math:`A_2` collide using an underlying one-track prediction model for both actors, or infinity if the predicted trajectories do not intersect.
It is defined by

.. math::
		\mathit{TTC}(A_1,A_2,t)  = \min \; (\{ \tilde{t} \ge 0 \,\mid\,  d(p_1(t+ \tilde{t}), p_2(t+ \tilde{t})) = 0 \} \cup \{ \infty \}).

While the TTC delivers quality results at cheap computational cost for car following scenarios, its validity is greatly reduced for intersection scenarios.
A modified version of the TTC, called MTTC, is extended under the name of CrI, where the MTT} is multiplied with a velocity-based accident severity factor to reflect a risk surrogate.

The TTC metric can be extended to multi-actor scenes by pairwise aggregation over actors and to scenarios by discrete aggregation over time.
For example, the scenario-level TTA metric is defined as :math:`\mathit{TTA}(A_1, A_2) = \mathit{TTC}(A_1, A_2, t_\mathit{evasive})` with :math:`t_\mathit{evasive}` being the first time where one of the actors conducts an evasive maneuver.

Note that for an implementation of the  TTC, one might want to limit the output to a time horizon :math:`t_H`, i.e. :math:`\tilde{t} \in [0,t_H]`.
The same can be said for all time-scale metrics in this section.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

1 s [Hayward1972]_ [Huber2020]_, 1.5 s, [Sacchi2016]_, [ElBasyouny2013]_, 3 s [Autey2012]_ (all data separation), 1.22 s [Junietz2018a]_ (threshold for critical)

Subject type
~~~~~~~~~~~~

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t

Output scale
~~~~~~~~~~~~

:math:`[0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Highly depending on the reliability of the predicted collision, for most DMMs reliability is reduced [Allen1978]_

Validity
~~~~~~~~

Medium, depending on the length of time interval with collision prediction in the scenario, as well as the validity of the DMM [StAubin2015]_

Sensitivity
~~~~~~~~~~~

Medium, as, due to the linear-time DMM, critical scenes may not have a predicted collision in the DMM [Allen1978]_

Specificity
~~~~~~~~~~~

High, as, due to the linear-time  DMM, only few uncritical situations have a predicted collision in the DMM [Zheng2019]_

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^

Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^

Linear time
