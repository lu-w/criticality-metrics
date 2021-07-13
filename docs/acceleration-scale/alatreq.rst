Required Lateral Acceleration (:math:`{a}_{\mathit{lat,req}}`)
==============================================================

Description
-----------

Similarly to the :doc:`required longitudinal acceleration<alongreq>`, the :math:`{a}_{\mathit{lat,req}}` [jansson_collision_2005]_ is defined as the minimal absolute lateral acceleration in either direction that is 
required for a steering maneuver to evade collision.
For two actors :math:`A_1, A_2` at time :math:`t`, :math:`{a}_{\mathit{lat,req}}` measures the minimum absolute lateral acceleration required, on average, by actor :math:`A_1` to avoid a collision in the future:

.. math::
	{a}_{\mathit{lat,req}}(A_1, A_2, t) = \min \{ |a_{1,\mathit{lat}}| ~|~\forall \, \tilde{t} \ge 0:   d(p_1(t+\tilde{t}),p_2(t+\tilde{t})) > 0 \}\,.


For actors :math:`A_1` and :math:`A_2` with constant acceleration where :math:`A_1` is following :math:`A_2`, the formula concretizes to

.. math::
	{a}_{\mathit{lat,req}}(A_1, A_2, t) = \min \{ |a_{1,\mathit{lat,left}}(A_1,A_2,t)|, |a_{1,\mathit{lat,right}}(A_1,A_2,t)| \}\

where

.. math::
	{a}_{1,\mathit{lat,k}}(A_1,A_2,t) =  {a}_{2,\mathit{lat,k}} + \frac{2(v_{2,\mathit{lat}}(t) - v_{1,\mathit{lat}}(t))}{\acs{TTC}(A_1,A_2,t)}
	+ \frac{2}{\acs{TTC}(A_1,A_2,t)^2} \cdot \left[ \pm \left( \frac{w_1+w_2}{2}\right) + p_{2,\mathit{lat}}(t) - p_{1,\mathit{lat}}(t)\right]


with :math:`w_i` denoting the width of :math:`A_i` and :math:`k \in \{\mathit{left}, \mathit{right}\}` depends on the sign of :math:`\frac{w_1+w_2}{2}`.


Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

:math:`[-7,-2.5]` m/s² dependent on speed [Benmimoun2011]_ (incident detection)

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

High, under the assumption that collisions can be reliably predicted in the prediction model

Validity
~~~~~~~~

High, but only lateral evasion considered, knowledge on vehicle capabilities necessary for interpretation [Zheng2019]_

Sensitivity
~~~~~~~~~~~

High, as most critical situations between two actors impose a high required acceleration at some point

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
