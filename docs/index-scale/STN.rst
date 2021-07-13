Steer Threat Number (STN)
=========================

Description
-----------

Similar to the BTN, for two actors at time :math: `t`, the STN [Jansson2005]_ [Eidehall2011]_ is defined as the required lateral acceleration divided by the lateral acceleration that is at most available to 
:math:`A_1` in that direction in that scene, i.e.

.. math::
		\mathit{STN}(A_1,A_2,t) = \frac{{a}_{\mathit{lat,req}}(A_1,A_2,t)}{a_{1,\mathit{lat,min}}(t)}.

By definition, an STN :math:`\ge 1` indicates that a lateral maneuver performed by the actor cannot avoid an impeding accident.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

:math:`\ge 1` (point of no return)

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Same as :math:`{a}_{\mathit{lat,req}}`

Inputs
~~~~~~

:math:`{a}_{\mathit{lat,req}}`, :math:`a_{\mathit{lat,min}}`

Output scale
~~~~~~~~~~~~

:math:`(-\infty,\infty)`, number, ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that the non-collision condition can be reliably predicted

Validity
~~~~~~~~

Strongly depends on :math:`{a}_{\mathit{lat,req}}` and :math:`a_{\text{lat,min}}` estimate; suited for inter-vehicle comparisons; no empirical analysis available

Sensitivity
~~~~~~~~~~~

High for non-humans, as steering is often optimal, but seldomly executed by humans [Adams1994]_; strongly depends on :math:`{a}_{\mathit{lat,req}}` and direction of :math:`a_{\mathit{lat,min}}` estimation

Specificity
~~~~~~~~~~~

High, but strongly depends on :math:`{a}_{\mathit{lat,req}}` and direction of :math:`a_{\mathit{lat,min}}` estimation

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
