Brake Threat Number (BTN)
=========================

Description
-----------
For actor :math:`A_1`, the BTN [Jansson2005]_ is defined as the required longitudinal acceleration imposed on actor :math:`A_1` by actor :math:`A_2` at time :math:`t`, divided by the longitudinal acceleration that is at most available to :math:`A_1` in that scene, i.e.

.. math::
		\mathit{BTN}(A_1,A_2,t) = \frac{{a}_{\mathit{long,req}}(A_1,A_2,t)}{a_{1,\mathit{long,min}}(t)}\,.

By definition, a BTN :math:`\ge 1` indicates that a braking maneuver performed by the actor cannot avoid an impeding accident under the assumed DMM.
An extension of BTN to multiple actors is proposed by Eidehall [Eidehall2011]_.

A special case of the BTN is known as the Deceleration-based Surrogate Safety Measure (DSSM).
Here, for car-following scenarios, a worst case assumption of maximum braking of the lead vehicle is combined with an acceleration-dependent estimation of the following driver's time to perceive the threat and transition to emergency braking, thus incorporating human factors into the model [Tak2015].

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

Same as :math:`a_{\mathit{long,min}}`

Inputs
~~~~~~

:math:`a_{\mathit{long,req}}`, :math:`a_{\mathit{long,min}}`

Output scale
~~~~~~~~~~~~

:math:`(-\infty,\infty)`, number, ratio scale

Reliability
~~~~~~~~~~~

Comparable to :math:`a_{\mathit{long,req}}`

Validity
~~~~~~~~

Better than :math:`a_{\mathit{long,req}}` [Zheng2019]_, depends on :math:`a_{\mathit{long,req}}` and :math:`a_{\mathit{long,min}}` estimate; suited for inter-vehicle comparisons; no empirical analysis available

Sensitivity
~~~~~~~~~~~

High, but strongly depends on :math:`a_{\mathit{long,req}}` and direction of :math:`a_{\mathit{long,min}}` estimation

Specificity
~~~~~~~~~~~

High for humans, as braking is often preferred by human drivers [Adams1994]_; strongly depends on :math:`a_{\mathit{long,req}}` and direction of :math:`a_{\mathit{long,min}}` estimation

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time
