Deceleration to Safety Time (DST)
=================================

Description
-----------

For an actor :math:`A_1` following another actor :math:`A_2`, the DST metric calculates the deceleration (i.e. negative acceleration) required by :math:`A_1` in order to maintain a safety time of :math:`t_s \ge 0` seconds under the assumption of constant velocity :math:`v_2` of actor :math:`A_2` [Hupfer1997]_ [Schubert2010]_.
The corresponding formula can be written as

.. math::
		\mathit{DST}(A_1,A_2,t,t_s)  = \frac{3(v_{1,\mathit{long}}(t) - v_{2,\mathit{long}}(t))^2}{2(d(p_1(t),p_2(t)) - v_{2,\mathit{long}}(t) \cdot t_s)}

and extends the concept of the :math:`{a}_{\mathit{long,req}}` by requiring deceleration to a safety distance :math:`v_{2,\mathit{long}}(t) \cdot t_s`, under the assumptions of constant velocity of :math:`A_2`, i.e. :math:`a_2=0`.
In particular, for :math:`t_s = 0`, the DST agrees with the constant acceleration version of the :math:`{a}_{\mathit{long,req}}` metric.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

- :math:`<1` m/s² (adaption)
- :math:`<2` m/s² (reaction)
- :math:`<4` m/s² (considerable reaction)
- :math:`<6` m/s² (heavy reaction)
- :math:`\geq 6` m/s² (emergency braking) for :math:`t_s = 0` [Hupfer1997]_

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Designed for car following, but can be extended to any scenario that potentially necessitates a braking maneuver

Inputs
~~~~~~

Positions :math:`p_i` and velocities :math:`v_i` for :math:`i \in \{1, 2\}` and a safety time :math:`t_s`

Output scale
~~~~~~~~~~~~

:math:`(-\infty, \infty)`, acceleration (m/s²), ratio scale

Reliability
~~~~~~~~~~~

Comparable to :math:`{a}_{\mathit{long,req}}`

Validity
~~~~~~~~

Comparable to :math:`{a}_{\mathit{long,req}}`, but depends on the validity of chosen value of :math:`t_s` under the given circumstances, and assumption of constant velocity; was exemplarily shown to have improvements over TTC and PET [Hupfer1997]_

Sensitivity
~~~~~~~~~~~

Comparable to :math:`{a}_{\mathit{long,req}}`, large :math:`t_s` increases sensitivity

Specificity
~~~~~~~~~~~

Comparable to :math:`{a}_{\mathit{long,req}}`, large :math:`t_s` decreases specificity

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Limited, due to assumption of constant velocity

Time mode
^^^^^^^^^
Linear time
