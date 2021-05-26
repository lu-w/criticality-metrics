Time To Closest Encounter (TTCE)
================================

Description
-----------

The TTCE is a distance-dependent risk indicator, which generalizes the concept of the TTC to the non-collision case [Eggert2014]_.
At time :math:`t`, the TTCE measures the time :math:`\tilde{t}>0` for which the distance to other actors in a scenario becomes minimal.
The corresponding minimal distance is called the DCE. The formulae are

.. math::
		\mathit{DCE}(A_1,A_2,t) = \min_{\tilde{t} \ge 0} d(p_1(t+\tilde{t}),p_2(t+\tilde{t}))\,,

.. math::
		\mathit{TTCE}(A_1,A_2,t)  = \text{arg}\,\text{min}_{\tilde{t} \ge 0} d(p_1(t+\tilde{t}),p_2(t+\tilde{t}))\,.

In particular, as :math:`\mathit{DCE} \rightarrow 0`, :math:`\mathit{TTCE} \rightarrow \mathit{TTC}` which implies :math:`\mathit{DCE} = 0` if and only if :math:`\mathit{TTCE} = \mathit{TTC}`.
Building on the TTCE and DCE, Eggert uses an exponential transform together with a survival function in order to estimate the future event probability of a collision for the distance-dependent risk [Eggert2014]_.
For simplicity, we omit further technical details here.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Any scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Higher than TTC as the DMM is not constraint to a predict a collision

Validity
~~~~~~~~

Low, as the closest encounter is not necessarily a critical event, increased when used with a DCE threshold to delineate critical from non-critical encounters

Sensitivity
~~~~~~~~~~~

High, as many critical scenes exhibit temporal proximity to a close encounter

Specificity
~~~~~~~~~~~

Low, as a closest encounter is not always a critical event

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
