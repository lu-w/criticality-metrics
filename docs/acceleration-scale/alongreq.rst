Required Longitudinal Acceleration (:math:`{a}_{\mathit{long,req}}`)
====================================================================

Description
-----------

For two actors :math:`A_1`, :math:`A_2` at time :math:`t`, :math:`{a}_{\mathit{long,req}}` measures the average negative longitudinal acceleration required by actor :math:`A_1` to avoid a collision in the future.
It can be formalized as

.. math::
		{a}_{\mathit{long,req}}(A_1, A_2, t) = \max \{ a_{1,\mathit{long}} \le 0 ~|~\forall \, \tilde{t} \ge 0: d(p_1(t+\tilde{t}),p_2(t+\tilde{t})) > 0\}\,.

The :math:`{a}_{\mathit{long,req}}` can be adapted for the situation where the acceleration of :math:`A_1` needs to be positive in order to avoid a collision by taking the minimum :math:`a_{1,\mathit{long}} \ge 0` instead.
An interesting special case, cf. [Jansson2005]_, is exhibited when constant acceleration of the actors is assumed, resulting in

.. math::
		{a}_{\mathit{long,req}}(A_1, A_2, t) = \min\Big(a_{2,\mathit{long}} + \frac{(v_{1,\mathit{long}}(t)-v_{2,\mathit{long}}(t))^2}{2d(p_1(t),p_2(t))}, 0\Big)\,.

For constant acceleration, the concept of :math:`{a}_{\mathit{long,req}}` is also known under the term Deceleration Rate To Avoid Crash (DRAC) [Archer2005]_.
Similarly, the :math:`{a}_{\mathit{lat,req}}` metric [Jansson2005]_ is defined as the minimal absolute lateral acceleration required for a steering maneuver to evade collision.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

-6 m/s² [Stellet2016]_ (AEB), :math:`\mu \cdot g` [Jeppsson2018]_ (point of no return), -3.4 m/s² [Huber2020]_ (scenario classification), :math:`[-8,-4]` m/s², dependent on speed [Benmimoun2011]_ (incident detection)

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Intersecting predicted paths for a significant time span in the scenario

Inputs
~~~~~~

:math:`v_i, a_i, p_i` for :math:`i \in \{1,2\}` assuming the constant acceleration motion model

Output scale
~~~~~~~~~~~~

:math:`(-\infty, \infty)`,  acceleration (m/s²), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that the non-collision condition can be reliably predicted

Validity
~~~~~~~~

High, but only longitudinal evasion considered, knowledge on vehicle capabilities necessary for interpretation [Zheng2019]_

Sensitivity
~~~~~~~~~~~

High, as most critical situations between two actors impose a high required acceleration at some point, more sensitive than CPI [Guido2011]_

Specificity
~~~~~~~~~~~

Medium, as there exists situations with intersecting paths of actors, but planned trajectory is deviating (e.g. turning maneuvers)

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
