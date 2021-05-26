Pedestrian Risk Index (PRI)
===========================

Description
-----------

The PRI estimates the conflict probability and severity for pedestrian crossing scenarios by combining the TTZ with the impact speed [Cafiso2011].
It is defined for a scenario with a vehicle :math:`A_1` and a VRU :math:`P` both approaching a conflict area :math:`\mathit{CA}`.
The scenario shall include a unique and coherent conflict period :math:`[t_{c_\mathit{start}}, t_{c_\mathit{stop}}]` where :math:`\forall\,t \in [t_{c_\mathit{start}}, t_{c_\mathit{stop}}]:\,\mathit{TTZ}(P, \mathit{CA}, t) < \mathit{TTZ}(A_1, \mathit{CA}, t) < t_s(A_1, t)`.
Here, :math:`t_s(A_1, t)` is the time :math:`A_1` needs to come to a full stop at time :math:`t`, including its reaction time, leading to

.. math::
		\mathit{PRI}(A_1, P, \mathit{CA}) = \int_{t_\mathit{c_\mathit{start}}}^{t_{c_\mathit{stop}}}(s_{imp}(A_1, \mathit{CA}, t)^2 \cdot (t_s(A_1, t) - \mathit{TTZ}(A_1, \mathit{CA}, t))) \mathrm{dt},

where :math:`s_\mathit{imp}` is the predicted speed at the time of contact with the pedestrian crossing.
The PRI thus quantifies over two aspects of a whole scenario: the temporal difference is claimed to be a surrogate for the accident probability, whereas the impact speed is approximate for its severity.
One possibility of estimating :math:`s_\mathit{imp}` is defined by the authors as

.. math::
		s_\mathit{imp}(A_1, \mathit{CA}, t) = \sqrt{\|v_1(t)\|_2^2-2a_{1,\mathit{long,min}}(t) (d(p_1(t),p_\mathit{CA}(t)) - \|v_1(t)\|_2 t^r_1)} \text{,}

where :math:`t_i^r` is the reaction time of actor :math:`A_i`.
Note that depending on the DMM, other formulae for :math:`s_\mathit{imp}` may be employed.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Theoretically possible, but primary design goal is a-posteriori analysis

Target values
~~~~~~~~~~~~~

Faded markings: 1992, visible markings: 1623, visible markings, speed bump: 407, raised visible markings, speed bump: 161 [Cafiso2011]_

Subject type
~~~~~~~~~~~~

Pedestrian

Scenario type
~~~~~~~~~~~~~

Scenarios with a unique and coherent conflict period, where one vehicle and pedestrian both approach a pedestrian crossing

Inputs
~~~~~~

:math:`a_\mathit{1,long,min}`, :math:`t_i^r`, for each :math:`t \in [t_{c_\mathit{start}}, t_{c_\mathit{stop}}]`: :math:`v_i(t)`, :math:`v_p(t)`, :math:`t_s(A_i,t)`, :math:`d(A_i, Z)`, :math:`d(P, Z)`

Output scale
~~~~~~~~~~~~

:math:`(0,\infty)`, risk number (m²/s³), interval scale

Reliability
~~~~~~~~~~~

Depends on reliability of TTZ, but with the advantage of being robust against 'jumps' in TTZ due to integration over time

Validity
~~~~~~~~

High if all assumptions hold, due to consideration of severity and probability, but dependent on validity of TTZ and :math:`v_\mathit{imp}`; no empirical analysis available

Sensitivity
~~~~~~~~~~~

High, as constant velocity model can be considered an adverse estimation of future development at pedestrian crossings

Specificity
~~~~~~~~~~~

Medium, as prediction model does not consider reactive behavior of participants on each other

Prediction model
~~~~~~~~~~~~~~~~

Same as TTA
